
# Draneka Aquarium Breeder v1.0 — Production Implementation Plan

Date: 2026-09-15
Status: **CORRECTED IMPLEMENTATION PLANNING / FRESH INDEPENDENT REVIEW REQUIRED / NO PRODUCTION MUTATION / NO PRODUCTION SOURCE IMPLEMENTATION**

This is a bounded planning-authority correction. The prior planning review is stale after this exact-head change; it is not evidence for the corrected candidate.

### Current authority rebind at correction start

~~~text
BREEDER_MAIN = 1baee0e1b2a57f056dccc3c6db834b78f88cfede
PR12_BASE = 1baee0e1b2a57f056dccc3c6db834b78f88cfede
PR12_HEAD_BEFORE_CORRECTION = 65c0f90194aa9857a25b5e66865551ce63919c8c
PR12_CORRECTION_COMMIT = EXACT SHA RECORDED IN THE DURABLE OWNER RESULT; THIS PLAN DOES NOT SELF-EMBED ITS OWN COMMIT HASH
FINAL_PR12_HEAD_READBACK_RULE = RE-READ THE GITHUB PR #12 HEAD IMMEDIATELY BEFORE INDEPENDENT REVIEW; REVIEW ONLY THAT EXACT REMOTE SHA
PR12_STATE = OPEN / DRAFT / UNMERGED

JOURNAL_MAIN = 897ce087d0d42dac25eabe23b05b00a605f23644
JOURNAL_LOCAL_MIGRATION_TAIL = 028-core-journal-pr5-refresh-token-replacement-index-convergence.sql
JOURNAL_PROVIDER_APPLIED_COUNT_AT_READBACK = 34
JOURNAL_PROVIDER_LATEST_VERSION_AT_READBACK = 20260915093928
JOURNAL_PROVIDER_LATEST_NAME_AT_READBACK = af_pr5_temp_target_recovery_read_20260915_001

JOURNAL_REPOSITORY_MIGRATION = 029-journal-breeder-foundation.js + 029-journal-breeder-foundation.sql
JOURNAL_REPOSITORY_MIGRATION_STATUS = PLANNED / UNAPPLIED
JOURNAL_MIGRATION_FILE_LOCATION = JOURNAL PR CREATED FROM EXACT CURRENT JOURNAL MAIN
BREEDER_MIGRATION_RUNNER = NONE
BREEDER_PHYSICAL_SCHEMA_AUTHORITY = NONE
BREEDER_PROVIDER_MIGRATION_VERSION = ASSIGN FRESH TIMESTAMP AT JOURNAL IMPLEMENTATION TIME / UNAPPLIED
~~~

The provider readback above is the parent-supplied live readback at this execution point. It does not apply or qualify the planned Journal-owned migration. The exact correction commit SHA is recorded in the durable owner result after push; no self-hashing commit claim is made in this plan. GitHub PR #12 head must be re-read immediately before independent review, and review must bind to that exact remote readback.

This plan is the execution contract for implementing the exact canonical holistic v1.0 product. It freezes the boundaries below so implementation can proceed without reopening foundational architecture.

## 1. Exact product authority

~~~text
ARTIFACT =
DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html

DRIVE_ID =
1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0

BYTES = 458038
SHA256 = 4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d

CANONICAL_REPOSITORY = nickdevph/draneka-breeder
CANONICAL_MERGE = 1baee0e1b2a57f056dccc3c6db834b78f88cfede
HOLISTIC_V1_0_CANONICAL = YES
~~~

The exact artifact behavior is product authority. This plan does not redesign it.

The independent v1.0 product review established the following implementation-facing behavior:

- primary navigation is exactly Today / Programs / Log / Grow-out / More;
- Program search has deterministic recovery;
- quantity is singular and does not double-count scalar and structured hatch observations;
- historical/materialized reproductive outputs cannot regain positive commerce authority;
- split, merge, move, stage, loss and count semantics preserve quantity and provenance;
- phenotype is observation, not genotype;
- suggestions, scheduled actions, completed actions, observations and derived state remain distinct;
- public/private media selection is explicit, including explicit zero-public-media;
- commerce reconciliation never rewrites biological history;
- representative Betta, Medaka, Neocaridina and annual-killifish workflows are evidence-bounded.

## 2. Founder-locked database and repository boundary

~~~text
BREEDER_PRODUCTION_DATABASE_PROJECT = EXISTING_JOURNAL_SUPABASE
JOURNAL_SUPABASE_PROJECT_REF = sjodccpuyaasljcunmug
NEW_SUPABASE_PROJECT = NO
CORE_SUPABASE_PROJECT = UNCHANGED

PHYSICAL_DATABASE_MIGRATION_AUTHORITY = nickdevph/aquaticfinder-journal
BREEDER_PRODUCT_APPLICATION_AUTHORITY = nickdevph/draneka-breeder
~~~

Core remains a separate persistence boundary for account, profile, identity and session authority. Journal remains the physical PostgreSQL home for Journal-owned data and future Breeder-owned data. No cross-database foreign keys or cross-database transactions are introduced.

Decision 0008 is the locked architecture decision. Breeder must not add a second production migration runner, migration registry or bootstrap path against the Journal database.

Detailed records:

- implementation/v1.0/SCHEMA-DOMAIN-MODEL.md
- implementation/v1.0/RUNTIME-SECURITY-MODEL.md
- implementation/v1.0/API-SERVICE-CONTRACT.md
- implementation/v1.0/WEB-ARCHITECTURE.md
- implementation/v1.0/QUALIFICATION-MATRIX.md
- implementation/v1.0/IMPLEMENTATION-ADMISSION.md

## 3. Final system shape

~~~mermaid
flowchart TD
  Core["AquaticFinder Core identity/session authority"] --> Auth["server-side Core session adapter"]
  Auth --> Web["Draneka Breeder web client"]
  Web --> API["Breeder API/domain service"]
  API --> BRole["restricted breeder runtime role"]
  BRole --> JS["existing Journal Supabase Journal + breeder_* tables"]
  API --> JAPI["Journal-owned service/API for Journal writes and admitted reads"]
  API --> Handoff["structured commerce handoff"]
  Handoff --> Commerce["AquaticFinder commerce allocation/listing/order authority"]
~~~

The browser and Android clients never receive PostgreSQL credentials. The Breeder service resolves the authenticated Core subject server-side, then performs owner-scoped domain operations against the shared Journal database.

## 4. Frozen ownership matrix

| Domain fact or capability | Authority | Breeder rule |
| --- | --- | --- |
| Account, profile, identity, session | Core | consume verified Core session; no duplicate identity authority |
| Tank identity and location | Journal | reference Journal tank; never duplicate tanks |
| Ordinary livestock identity | Journal | reference Journal livestock where applicable |
| Water, feeding, maintenance, ordinary observations | Journal | use Journal service/API; no direct Breeder table writes |
| Journal media and private storage | Journal | reuse through an admitted media adapter |
| FollowUp/Schedule infrastructure | Journal | bind only where semantics match; do not duplicate scheduler |
| Breeding Programs | Breeder | Breeder-owned durable record |
| Breeder-stock membership/context | Breeder | Breeder-owned; Journal livestock is a reference |
| Parentage/source context | Breeder | evidence-bounded; unknown remains unknown |
| Reproductive outputs and hatches | Breeder | Breeder-owned biological authority |
| Offspring/grow-out groups | Breeder | Breeder-owned; current tank is a Journal reference |
| Quantity and operation ledger | Breeder | one biological quantity authority |
| Provenance/lineage | Breeder | append-only evidence links and source snapshots |
| Phenotype/evaluations | Breeder | observation only; never genotype inference |
| Selection/disposition | Breeder | current eligibility is derived from current history |
| Lifecycle suggestions/Breeder Round | Breeder | projection/attention; never a biological fact |
| Commerce handoff evidence | Breeder | explicit evidence-bounded handoff; no biological rewrite |
| Commercial allocation/outcome receipts | AquaticFinder commerce | authoritative commercial receipt stream; Breeder accepts a validated immutable boundary receipt only |
| Listings, channels, orders, payment, shipping, commercial allocation | AquaticFinder commerce | outside Breeder v1.0 |

A foreign key to a Journal row does not transfer ownership of that Journal row.

## 5. Required invariants

The following are implementation contracts, not UI suggestions.

### Quantity

- one biological quantity authority per reproductive output and offspring group;
- scalar/legacy and structured hatch observations are materialized once;
- remaining output is original minus removed minus materialized hatch quantity, never a second independent scalar;
- split conserves quantity across source and children;
- merge conserves quantity and preserves all source provenance;
- loss/mortality reduces only the affected current group;
- move, feeding, observation and stage change do not change quantity;
- an inactive, historical or fully materialized output cannot regain positive commerce authority;
- commerce allocation and reconciliation are separate from biological quantity.

### Provenance

- every descendant retains output and hatch source IDs;
- split adds a derivation edge without deleting parent history;
- merge preserves every source edge or fails closed;
- individual promotion preserves known source provenance;
- unknown/group/population ancestry cannot become exact sire/dam;
- generation labels require sufficient evidence;
- annual killifish hatch provenance includes the exact wetting attempt;
- historical records are immutable for biological mutation.

### Later commerce reconciliation contract — P7 only

- AquaticFinder owns commercial allocation and outcome receipts. Breeder owns the biological quantity ledger and may store only an immutable, validated acceptance record or projection of an AquaticFinder receipt.
- Allocation and outcome quantities are non-negative deltas.
- For each handoff and channel, cumulative accepted allocation must not exceed the acknowledged allocation, and cumulative accepted outcome must not exceed the acknowledged allocation or the accepted allocation available for that outcome. An exception requires an explicit approved exception reference, reason and approval receipt; without those fields the receipt is rejected.
- A duplicate `(channel, external reference)` with the same request hash returns the original accepted receipt. The same external reference with a different hash returns `IDEMPOTENCY_CONFLICT`. The same owner/idempotency key follows the same same-hash replay and different-hash conflict rule.
- Rejected, duplicate-conflicting or over-limit receipts do not write `breeder_quantity_ledger`, alter biological counts, rewrite provenance or restore eligibility.
- This contract is deferred to P7-COMMERCE-005 and is excluded from the 001A foundation and 001B service/API slices.

### Fact/action

~~~text
suggestion != scheduled action != completed action != observation != derived state
~~~

Completing a check does not assert the biological fact being checked. A suggestion may be dismissed or deferred without creating a fact.

### Selection and privacy

- phenotype remains an observation;
- current incompatible disposition removes current pairing eligibility;
- selection goals preserve history and snapshots;
- private media never becomes public implicitly;
- zero selected public media remains zero;
- only explicitly selected and Journal-authorized public evidence enters a handoff;
- commerce reconciliation cannot modify breeding history.

## 6. Migration and shared-database sequencing

Journal main is currently:

~~~text
nickdevph/aquaticfinder-journal
main = 897ce087d0d42dac25eabe23b05b00a605f23644
current local migration tail = 028-core-journal-pr5-refresh-token-replacement-index-convergence.sql
current provider readback = 34 applied; latest 20260915093928 / af_pr5_temp_target_recovery_read_20260915_001
~~~

The current Journal main is the planning base. Its local migration namespace already contains `024-core-journal-target-*`, `025-core-journal-pr4-schema-convergence.sql`, `026`, `027` and `028`; therefore historical `025` is occupied and cannot be reused.

Journal PR #873 is stale, unmerged historical work requiring a separate current-head disposition:

~~~text
PR #873
base = 5f00cf5106e3127a8dfb55ab59407d262f1e8d16
head = 829618fe2d3f20a64703021676032be429079fd3
migration claim = historical 024 runtime-role/RLS hardening
state = OPEN / NON-DRAFT / STALE AND DIVERGED / NOT MERGED
Breeder dependency = NONE
~~~

Do not copy PR #873, use its migration claim, or wait for it as a Breeder dependency. The Core→Journal consolidation and subsequent migration order are bound to current Journal main, not the stale PR #873 line. Any future #873 disposition is separate work and must be requalified at its own current head.

The next valid Journal repository migration identity for the Breeder foundation is planned as:

~~~text
029-journal-breeder-foundation.js
029-journal-breeder-foundation.sql
repository status = PLANNED / UNAPPLIED
provider version = FRESH TIMESTAMP TO BE ASSIGNED BY JOURNAL MIGRATION OWNER AT IMPLEMENTATION TIME,
                  STRICTLY AFTER 20260915093928, THEN READ BACK
~~~

The local zero-padded sequence is authoritative for repository ordering. The provider timestamp is assigned only when the Journal implementation registers/applies the migration against the then-current exact head; no provider version is claimed as applied here.

At the supplied provider readback, no Breeder foundation tables are present. The only matching public table is `public.catalogue_breeder_attributions` with RLS enabled and zero rows. Relevant Journal tables have RLS enabled. Security advisors report 16 mutable-function-search-path warnings, so this plan records no security PASS.

The migration must:

1. require the exact current Journal main marker/state and the implementation-time migration precondition;
2. execute only as journal_migrator or an explicitly admitted migration actor;
3. execute through both current Journal bootstrap entrypoints;
4. create only the minimum breeder_* foundation tables, constraints, roles, grants, RLS and account-retention hooks needed by BREEDER-FOUNDATION-001;
5. never rewrite an existing Journal migration;
6. include disposable-Postgres qualification and a pre-data rollback proof;
7. remain non-production until a separate Founder production-admission gate passes.

The Journal PR created from the exact Journal main owns the migration files and physical schema change. The Breeder repository owns no production migration file, migration runner or physical schema authority. Breeder PRs may contain contracts, domain code, UI and integration tests only.

## 7. Implementation-ready domain/service boundary

Breeder writes are intent/domain commands, not raw table CRUD. The initial versioned API is /api/v1.

Frozen initial commands:

~~~text
createProgram
recordReproductiveOutput
recordHatchObservation
createOffspringGroup
reviseGroupCount
recordMortality
moveOffspringGroup
splitOffspringGroup
mergeOffspringGroups
recordStageObservation
recordSelectionEvaluation
applyDisposition
~~~

Deferred P7 commerce commands, not part of the foundation/API slice:

~~~text
prepareCommerceHandoff
reconcileCommerceOutcome
~~~

Create commands may omit expected revision because they establish a new revision-1 record. Updates and commands against mutable existing state must provide the current expected revision; missing or stale values are rejected. Every command otherwise resolves the owner from a verified Core session, validates all same-owner references, uses an idempotency key, performs one database transaction, returns committed readback and emits an auditable command receipt.

Journal-owned writes—feeding, water tests, ordinary observations, media creation and schedule completion—call Journal's canonical service or API. Breeder may persist an explicit Breeder-to-Journal binding, but does not bypass Journal domain validation.

## 8. Web architecture decision

The initial production web app is a separate authenticated React application in nickdevph/draneka-breeder, using the existing ecosystem's proven React/Vite/Node shape:

- React 19 + TypeScript;
- Vite 8;
- server-side Node API/domain service;
- pg against the same Journal Supabase database using a restricted server-only credential;
- Playwright browser qualification;
- Vercel deployment only after implementation admission.

The canonical IA remains:

~~~text
Today
Programs
Log
Grow-out
More
~~~

No new primary navigation destination is introduced. The authenticated shell, responsive states, forms, loading/empty/error/recovery states, keyboard paths and media adapter are specified in WEB-ARCHITECTURE.md.

Core session reuse is an adapter boundary: the browser presents the existing authenticated session; the Breeder server verifies it through the existing Core session contract or an authenticated service-to-service introspection path. No endpoint accepts a caller-supplied owner_user_id as authority.

## 9. Data migration and existing users

Initial Breeder release is prospective.

- Existing Journal tanks, livestock, events and media may be referenced as existing facts after owner-scope validation.
- No Program, parentage, reproductive output, hatch, generation or breeding history is inferred from generic Journal history.
- No automatic backfill is authorized.
- Any future backfill requires a separate Founder decision, explicit evidence mapping and independent migration review.
- Account deletion/export/retention must include Breeder-owned rows through the Journal-owned lifecycle path.

## 10. Implementation packages

| Package | Owner/repository | Dependency | Completion gate |
| --- | --- | --- | --- |
| P0 / PLAN-001 | Draneka Breeder PR #12 | canonical v1.0 + current Journal main inspection | this corrected plan and fresh independent review PASS |
| BREEDER-FOUNDATION-001A | Journal PR from current exact Journal main | local migration sequence 029; fresh provider timestamp assigned at implementation | schema, role, RLS, FK, retention and disposable-DB PASS |
| BREEDER-FOUNDATION-001B | Breeder repository | 001A qualified on disposable DB | auth adapter, domain commands, idempotency and API PASS |
| BREEDER-FOUNDATION-001C | Breeder repository | 001B API | Today/Programs/output/hatch/group/tank web slice and readback PASS |
| P4-GROWOUT-002 | Breeder + Journal only where needed | foundation slice | count/move/split/merge/loss/stage/provenance PASS |
| P5-SELECTION-003 | Breeder | grow-out provenance | evaluation, goals, disposition and Pair Builder guardrails PASS |
| P6-ROUND-004 | Breeder + Journal schedule adapter | selection/domain foundation | projection/action/fact separation and schedule integration PASS |
| P7-COMMERCE-005 | Breeder + AquaticFinder contract | stable biological model | AquaticFinder-owned allocation/outcome receipts, non-negative and no-over-allocation reconciliation, external-reference/idempotency and non-mutating biological boundary PASS |
| P8-HARDENING-006 | both repositories as needed | all v1.0 surfaces | responsive/a11y/security/regression PASS |
| P9-ADMISSION-007 | Founder-gated | P8 | production migration/deployment admission PASS |
| P10-ANDROID-008 | separate Android admission | stable web/domain contract | Android convergence/review only after P9 or separate Founder admission |

Each package is one rollback unit. A package cannot silently absorb a later package or alter canonical v1.0 semantics.

## 11. First executable package — frozen mandate

~~~text
PACKAGE = BREEDER-FOUNDATION-001
SUBPACKAGES = 001A Journal foundation, 001B service/API, 001C web slice
STATUS = FROZEN FOR IMPLEMENTATION COMMISSION
~~~

### 001A — Journal database foundation

Implement only:

- breeder_programs;
- minimum owner-scoped parentage/source context;
- breeder_reproductive_outputs;
- breeder_hatch_observations;
- breeder_offspring_groups;
- breeder_group_provenance;
- breeder_group_operations;
- breeder_quantity_ledger;
- breeder_command_receipts;
- same-owner composite references to Journal tanks and optional Journal livestock;
- dedicated Breeder runtime capability/login role;
- RLS, grants, owner-scope helper, account deletion/export/retention hooks;
- migration marker/bootstrapping and tests.

Do not implement selection, Pair Builder, commerce, Android, AI, marketplace operations, or new navigation. Commerce handoff/reconciliation remains deferred to P7 and is excluded from 001A and 001B.

### 001B — service/API

Prove:

~~~text
verified Core session
  -> owner-scoped create/read Program
  -> parent/source context
  -> record reproductive output
  -> explicit hatch/recruitment
  -> create offspring group
  -> assign/reference Journal tank
  -> transaction commit
  -> committed readback
~~~

The service must reject cross-user tank/livestock UUIDs, duplicate idempotency with a different request hash, missing or stale revisions on mutable-state commands, invalid quantities and unsupported provenance claims. It does not implement the deferred P7 commerce contract.

### 001C — web

Implement only the canonical authenticated shell and the vertical slice screens needed to create and read the above records. UI work starts only after 001A disposable database and security qualification passes. The first package is not production-deployed by this planning PR.

## 12. Qualification strategy

Every package must use the matrix in QUALIFICATION-MATRIX.md. Required dimensions include:

- unit and domain invariants;
- disposable Postgres migrations and rollback;
- owner isolation/RLS and cross-user composite-FK failures;
- least-privilege runtime-role verification;
- transaction, concurrency and idempotency;
- API integration and committed readback;
- Playwright E2E at 320, 390, 768 and 1440 CSS widths;
- keyboard/focus/accessibility;
- loading, empty, error and recovery;
- canonical v1.0 and v0.5-v0.9 regression fixtures;
- Journal regression whenever shared Journal code, migration bootstrap, roles or owned tables change;
- fresh security review before production database admission.

Prototype screenshots or HTML behavior alone are not implementation evidence.

## 13. Rollback and failure strategy

- Before production data exists, planned repository migration 029 may use a tested compensating/down script on a disposable target.
- After Breeder data exists, do not drop tables or delete history to roll back code.
- Disable the server-side Breeder feature flag, stop new commands, preserve append-only data and deploy the last qualified application.
- Repair forward with a new Journal migration; never rewrite 029 or any prior Journal migration.
- A failed cross-domain write leaves no half-created biological record. Journal API calls are outside Breeder biological transactions and use explicit pending or failed receipts if a future workflow needs compensation.
- A failed media/publication handoff cannot change quantity or lineage.
- A stale or conflicting idempotency key returns a deterministic conflict and does not retry a mutation.
- A concurrency conflict returns REVISION_CONFLICT and requires fresh readback.
- Production migration/deployment is stopped on any security, rollback, regression, private-media, provenance or quantity failure.

## 14. Implementation-admission checklist

Implementation may begin only when all are true:

~~~text
CANONICAL_V1_0_BOUND = PASS
BREEDER_DATABASE_PROJECT = EXISTING_JOURNAL_SUPABASE
NEW_SUPABASE_PROJECT = NO
CORE_BOUNDARY_PRESERVED = PASS
JOURNAL_BREEDER_OWNERSHIP_MATRIX = FROZEN
DATABASE_MIGRATION_AUTHORITY = FROZEN
SCHEMA_PLAN = IMPLEMENTATION_READY
RUNTIME_SECURITY_MODEL = IMPLEMENTATION_READY
API_SERVICE_BOUNDARY = IMPLEMENTATION_READY
WEB_ARCHITECTURE = IMPLEMENTATION_READY
MIGRATION_AND_ROLLBACK_PLAN = IMPLEMENTATION_READY
TEST_AND_QUALIFICATION_PLAN = IMPLEMENTATION_READY
CURRENT_JOURNAL_AUTHORITY = REBOUND_TO_897CE087D0D42DAC25EABE23B05B00A605F23644
CURRENT_JOURNAL_PROVIDER_READBACK = RECORDED / FOUNDATION UNAPPLIED
CURRENT_JOURNAL_COLLISION_ANALYSIS = REBOUND / FRESH IMPLEMENTATION-TIME CHECK REQUIRED
FIRST_EXECUTABLE_PACKAGE = FROZEN
INDEPENDENT_PLANNING_REVIEW = PRIOR PASS SUPERSEDED / FRESH REVIEW REQUIRED
PRODUCTION_DATABASE_MUTATION = NO
PRODUCTION_SOURCE_IMPLEMENTATION = NO
BREEDER_V1_0_IMPLEMENTATION_READY = PENDING FRESH INDEPENDENT REVIEW
~~~

This corrected plan records the next Founder-gated implementation sequence but does not admit execution until fresh independent planning review and a separate bounded commission complete. It does not authorize production migration, deployment, release or Android work.

## 15. Non-effects

This planning PR does not:

- create or alter Supabase projects;
- execute migrations;
- mutate production databases;
- implement production API, UI or Android source;
- deploy services;
- change Journal runtime-role/security code;
- adopt, copy, merge or implement from stale Journal PR #873;
- infer existing Breeder history;
- add marketplace management, payments, orders, shipping, CRM, genotype inference, predictive pairing authority, hardware integration, Android execution, generic Journal redesign, new production infrastructure or other v1.1 scope.
