
# Breeder v1.0 API and Domain Service Contract

Status: CORRECTED IMPLEMENTATION PLAN / FRESH REVIEW REQUIRED
Transport: versioned JSON HTTP under /api/v1
Authority: Breeder domain service; Journal service remains owner for Journal facts

The real Core-auth binding is the existing server-side Core session contract selected and re-read at implementation admission. Breeder must not create a parallel identity/session store, accept a caller-supplied owner identity, or treat a browser field as authorization. The corrected plan is bound to existing Journal Supabase project `sjodccpuyaasljcunmug`; it does not qualify a production runtime or migration.

## 1. Request boundary

Every request:

- verifies the existing Core session server-side;
- derives owner_user_id from verified Core identity;
- never trusts owner_user_id in the body, URL or query string;
- validates the Breeder feature admission flag server-side;
- starts an owner-scoped transaction for Breeder mutations;
- returns committed readback, not an optimistic client projection.

Clients receive stable error codes and no privileged database details.

## 2. Endpoint inventory

### Foundation read/write endpoints

~~~text
GET  /api/v1/session
GET  /api/v1/programs
POST /api/v1/programs
GET  /api/v1/programs/:programId
POST /api/v1/programs/:programId/reproductive-outputs
GET  /api/v1/reproductive-outputs/:outputId
POST /api/v1/reproductive-outputs/:outputId/hatches
POST /api/v1/programs/:programId/offspring-groups
GET  /api/v1/offspring-groups/:groupId
~~~

Later commands use dedicated intent endpoints:

~~~text
POST /api/v1/offspring-groups/:groupId/count-revisions
POST /api/v1/offspring-groups/:groupId/losses
POST /api/v1/offspring-groups/:groupId/moves
POST /api/v1/offspring-groups/:groupId/splits
POST /api/v1/offspring-groups/merge
POST /api/v1/offspring-groups/:groupId/stage-observations
POST /api/v1/selection-sessions
POST /api/v1/dispositions
POST /api/v1/commerce-handoffs
POST /api/v1/commerce-handoffs/:handoffId/reconciliations
~~~

The commerce endpoints are a deferred P7 contract and are not implemented in the 001A foundation or 001B service/API slices. AquaticFinder owns the authoritative commercial allocation and outcome receipts. Breeder accepts only a validated immutable receipt or projection and never treats it as biological quantity authority.

For a reconciliation receipt, `allocationQuantity` and `outcomeQuantity` are non-negative deltas. Accepted cumulative allocation for a handoff and channel cannot exceed the acknowledged allocation, and accepted cumulative outcome cannot exceed the acknowledged allocation or accepted allocation available for that outcome. An approved exception requires an explicit exception reference, reason and approval receipt. A duplicate `(channelKey, externalReference)` or owner/idempotency key with the same request hash returns the original accepted receipt; a different hash returns `IDEMPOTENCY_CONFLICT`. Negative, over-limit or conflicting receipts are rejected without a `breeder_quantity_ledger` write or biological-history mutation.

## 3. Mutation envelope

Every mutation requires an idempotency key and payload. Create commands establish a new revision-1 record and omit an expected revision. Updates and commands against mutable existing state require `expectedRevision`; commands that mutate one or more existing offspring groups use the per-group `expectedRevisions` vector defined below.

Create envelope:

~~~json
{
  "idempotencyKey": "client-generated stable key",
  "payload": {}
}
~~~

Mutable-state command envelope:

~~~json
{
  "idempotencyKey": "client-generated stable key",
  "expectedRevision": 3,
  "payload": {}
}
~~~

Group mutable-command envelope:

~~~json
{
  "idempotencyKey": "client-generated stable key",
  "expectedRevisions": [
    { "groupId": "affected-group-uuid-a", "revision": 3 },
    { "groupId": "affected-group-uuid-b", "revision": 7 }
  ],
  "payload": {}
}
~~~

`expectedRevisions` is required for every command that mutates an existing offspring group. It contains exactly one entry for every affected existing mutable group, including every source and destination group whose state, revision or quantity changes; a single-group command therefore has one entry. Entries are unique, contain positive integer revisions, and are canonicalized in ascending UUID order before the operation is stored. Newly created groups are not entries because create semantics establish their revision 1. The server locks that exact group set in the same order, rejects a missing vector with `EXPECTED_REVISIONS_REQUIRED`, rejects an extra, duplicate, malformed or otherwise mismatched vector with `EXPECTED_REVISIONS_INVALID`, rejects a stale value with `REVISION_CONFLICT`, and writes nothing unless every affected group's locked revision matches.

The server validates the key and request hash before business mutation.

Same owner and same idempotency key plus identical request hash returns the original committed response. Same key plus different hash returns IDEMPOTENCY_CONFLICT. A client retry after a network timeout is therefore safe.

## 4. Foundation payloads

### Create Program

~~~json
{
  "idempotencyKey": "uuid-or-stable-client-key",
  "payload": {
    "name": "Blue Jelly line",
    "speciesKey": "neocaridina-davidi",
    "speciesDisplayName": "Neocaridina",
    "reproductiveArchetype": "POPULATION"
  }
}
~~~

The server normalizes text, rejects blank names and returns the committed Program with revision 1.

### Record reproductive output

~~~json
{
  "idempotencyKey": "stable-key",
  "payload": {
    "parentageContextId": "uuid",
    "outputKind": "EGG_BATCH",
    "originalQuantity": 24,
    "quantityUnit": "EGGS",
    "collectedAt": "2026-09-09T10:00:00Z",
    "sourceLabel": "m02"
  }
}
~~~

The command creates the output, an append-only output operation/event row with `operationType = OUTPUT_CREATED`, and its `OUTPUT_CREATED` ledger entry in one transaction. The ledger row references that output operation through `output_operation_id`, has no group operation source and requires no offspring group. It cannot reference another owner's Program or parentage context.

### Record hatch/recruitment

~~~json
{
  "idempotencyKey": "stable-key",
  "expectedRevision": 1,
  "payload": {
    "observationKind": "STRUCTURED_HATCH",
    "quantity": 9,
    "quantityUnit": "FRY",
    "observedAt": "2026-09-12T10:00:00Z",
    "wettingAttemptId": "optional-for-annual-killifish",
    "cohortLabel": "m02 hatch 1"
  }
}
~~~

One accepted observation creates an append-only output operation/event row with `operationType = HATCH_MATERIALIZED` and one `HATCH_MATERIALIZED` ledger entry referencing that output operation. No offspring group is required. The command rejects a quantity greater than the remaining output quantity and rejects an attempt to materialize the same observation twice.

### Create offspring group

~~~json
{
  "idempotencyKey": "stable-key",
  "payload": {
    "groupLabel": "m02 hatch 1 fry",
    "stage": "FRY",
    "quantity": 9,
    "quantityUnit": "FRY",
    "currentTankId": "same-owner-journal-tank-uuid",
    "sourceHatchObservationId": "uuid"
  }
}
~~~

The group creation transaction verifies the hatch/output provenance, writes an append-only group operation/event row with `operationType = CREATE`, then writes `GROUP_CREATED` quantity plus provenance. The current tank is a Journal reference, not a Breeder-owned tank.

## 5. Transaction and concurrency rules

- lock all affected Breeder parent, output and group rows in deterministic UUID order;
- for output-level quantity events, insert the output operation/event source and ledger row with matching owner/output constraints; no group operation is required;
- for group commands, validate the exact `expectedRevisions` set and every locked revision before inserting operation, provenance or ledger entries;
- store the canonical `expectedRevisions` vector on the group operation as `expected_group_revisions`;
- insert command receipt and biological events in the same transaction;
- use composite owner foreign keys and owner predicates on every read;
- never call a remote Journal API while holding a biological transaction lock;
- validate Journal-owned references before the transaction, then let the composite FK reject deletion/race;
- return `EXPECTED_REVISIONS_REQUIRED` for a missing group vector, `EXPECTED_REVISIONS_INVALID` for a malformed/mismatched vector and `REVISION_CONFLICT` for a stale value;
- use deterministic lock ordering for split/merge, and reject the whole transaction if any affected group is missing or stale;
- commit before returning readback.

## 6. Journal integration

Breeder may read an admitted Journal tank/livestock/media projection. It must use the Journal-owned API/service for:

- creating or changing Journal tanks;
- generic feeding, maintenance, water tests and ordinary observations;
- Journal media creation, privacy and public-evidence authorization;
- Journal schedule/follow-up completion.

Breeder-specific Program, output, hatch, group, provenance, quantity, selection and handoff commands stay in breeder_* relations.

## 7. Error contract

Stable errors include:

~~~text
AUTH_REQUIRED
BREEDER_NOT_ADMITTED
OWNER_SCOPE_DENIED
PROGRAM_NOT_FOUND
OUTPUT_NOT_FOUND
GROUP_NOT_FOUND
JOURNAL_REFERENCE_SCOPE_DENIED
JOURNAL_REFERENCE_UNAVAILABLE
INVALID_QUANTITY
QUANTITY_EXCEEDS_REMAINING
PROVENANCE_INCOMPLETE
PROVENANCE_CONFLICT
REVISION_CONFLICT
EXPECTED_REVISIONS_REQUIRED
EXPECTED_REVISIONS_INVALID
IDEMPOTENCY_CONFLICT
COMMAND_ALREADY_COMMITTED
INVALID_STATE_TRANSITION
HISTORICAL_SOURCE_NOT_WRITABLE
PRIVATE_MEDIA_NOT_PUBLIC
PUBLIC_EVIDENCE_NOT_EXPLICIT
COMMERCE_QUANTITY_EXCEEDED
JOURNAL_WRITE_REJECTED
DEPENDENCY_UNAVAILABLE
~~~

Responses do not disclose whether an unauthorized UUID exists.

## 8. Read models

Read endpoints return:

- authority owner and record IDs;
- current status and revision;
- quantity derived from committed ledger;
- output/hatch/group provenance;
- current Journal tank context where admitted;
- fact/action classification;
- audit timestamps;
- no private media in public handoff projections.

A cached projection is disposable and rebuildable from append-only Breeder records.

## 9. API test contract

The API suite must prove happy paths, create-without-revision, required mutable-state revision, missing/stale revision rejection, retry idempotency, output creation before any offspring group with its output-operation/ledger linkage, concurrent split/merge, cross-user references, malformed provenance, quantity conservation, privacy, error recovery and committed readback. For group commands it must prove the exact per-affected-group vector, rejection of missing/extra/duplicate entries, rejection when any one affected group is stale, deterministic lock ordering and no partial operation/ledger write. The deferred P7 commerce suite must additionally prove non-negative allocation/outcome, no cumulative over-allocation or over-outcome without an approved exception, duplicate external-reference and idempotency handling, and no biological-ledger mutation on rejection. It must run against disposable Postgres and a deterministic Core-session test adapter; no production credentials are used.

## 10. Parent/source context endpoint

The foundation slice must expose the missing context creation command before an output can reference it:

~~~text
POST /api/v1/programs/:programId/parentage-contexts
POST /api/v1/programs/:programId/stock
~~~

The stock endpoint is optional for the first exact-parent path but is admitted for the minimum breeder-stock membership contract. Both are owner-scoped and idempotent.

Parentage context payload:

~~~json
{
  "idempotencyKey": "stable-key",
  "payload": {
    "contextType": "EXACT_PAIR",
    "evidenceStatus": "RECORDED",
    "label": "Ember + Lyra",
    "memberLivestockIds": ["same-owner-journal-livestock-uuid-1", "same-owner-journal-livestock-uuid-2"]
  }
}
~~~

The server rejects a claimed EXACT_PAIR when the supplied members do not resolve to the same authenticated owner or when the evidence does not support the claim. POPULATION, SOURCE_POPULATION and UNKNOWN contexts may omit exact livestock members.

The stock endpoint accepts an individual Journal livestock reference or a group/population label. It creates Breeder membership context only; it does not create or mutate Journal livestock.
