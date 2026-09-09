# Draneka Aquarium Breeder — Holistic v0.9 Bounded Correction Receipt

Date: 2026-09-09
Status: **BOUNDED CORRECTION PRODUCED / NON-CANONICAL / MERGE HOLD**

## Triggering independent review

The first holistic v0.9 independent review returned `CHANGES_REQUIRED` on exact pre-receipt head:

`f13d91638ef9e98ef41c4471c8f9e53a4c4bea33`

Review receipt:

`reviews/holistic-v0.9-independent-review-2026-09-09.md`

Receipt-only commit:

`8ac33bf2afcf2b4391eaa4680c9a781e02d115ed`

Promotion blockers:

- `V09-IR-001` — a historical zero-quantity cohort could create a positive commerce handoff.
- `V09-IR-002` — a reproductive-output total and its materialized descendant cohort could simultaneously own the same animals for commerce.

Additional bounded defect:

- `V09-IR-003` — the contextual `Sale / rehome` selection-workspace commerce entry did not render.

## Historical failed candidate — preserved

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-CANDIDATE.html`
- Drive ID: `1bEJ9SeXLgL4rjk1RKHmc3VQ_6njaAVxM`
- Bytes: `426330`
- SHA-256: `ec434d10167bcddc8d58027d0408a73946af1d41390e419c89a93d68df10ac85`
- Independent disposition: `CHANGES_REQUIRED`

That Drive object was not overwritten.

## New immutable bounded-correction candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `1OQqLK4aovt4RAfAdKxFnn9n-VB-nUaEX`
- Exact bytes: `437100`
- SHA-256: `21736560a33f7ab7a42b46c7691b690b9fb7336638c8fec616da30af345d4327`
- MIME: `text/html`

A fresh raw Drive re-download reproduced the same filename, exact byte count and SHA-256 above.

## V09-IR-001 correction — current positive quantity authority

Commerce handoff eligibility is now bound to a current source that owns a known positive biological quantity.

- active cohort with current count > 0: eligible;
- historical/inactive cohort: not eligible;
- zero-count cohort: not eligible;
- zero or unknown current quantity: cannot be clamped to an artificial commerce quantity of 1;
- stale sale-ready profiles cannot bypass the guard;
- historical source records remain usable for provenance/report history without becoming inventory owners.

Both the sale-ready entry and final handoff save path re-check this authority.

## V09-IR-002 correction — one current commerce quantity owner

Reproductive-output totals are no longer treated as concurrent current inventory after the underlying animals have materialized into current offspring records.

- non-egg/livebirth/population reproductive-output totals are historical reproductive evidence, not a second commerce quantity owner;
- current offspring must be handed off from the current cohort/stock record;
- discrete egg/collection outputs may own only their genuinely remaining unhatched/unmaterialized egg quantity;
- Medaka `m02` therefore owns exactly its remaining 15 eggs while the 9 hatched fish are represented through descendant cohort authority;
- Neocaridina output `s01` cannot concurrently claim its historical recruit total while descendant cohort `cs` owns the current animals.

The invariant is:

```text
COMMERCE_HANDOFF_ALLOWED
=
CURRENT_SOURCE_OWNS_DISTINCT_BIOLOGICAL_QUANTITY
AND KNOWN_POSITIVE_QUANTITY
AND NO_DUPLICATE_MATERIALIZED_SOURCE_OWNER
```

## V09-IR-003 correction — selection contextual entry

The selection-workspace wrapper now uses canonical current-disposition semantics. `Sale / rehome` renders the contextual commerce-ready handoff entry without changing selection or Pair Builder authority.

## Additional bounded hardening

Spawn/output evidence-media selection now requires source-linked media or media linked through a descendant cohort of that exact output. Arbitrary same-Program media is not offered merely because it shares Program context.

## Authority boundary

No marketplace listing/channel management, pricing optimization, CRM, payment, order, shipping, finance/accounting, public marketplace, broad inventory ERP, backend/API/schema/database/deployment/production mutation, Android/web implementation authority, genotype inference, automatic biological completion, or v1.0 scope is introduced.

Canonical v0.8 remains authoritative until this corrected candidate independently passes, receives Founder promotion and PR #9 is merged.

`V09_IR_001_CORRECTION = PRODUCED`

`V09_IR_002_CORRECTION = PRODUCED`

`V09_IR_003_CORRECTION = PRODUCED`

`HOLISTIC_V0_9_BOUNDED_CORRECTION_CANONICAL = NO`

`PR_9_MERGE = HOLD`
