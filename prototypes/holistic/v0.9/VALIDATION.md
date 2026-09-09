# Draneka Aquarium Breeder — Holistic v0.9 Producer Validation

Date: 2026-09-09
Candidate: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-CANDIDATE.html`
Drive ID: `1bEJ9SeXLgL4rjk1RKHmc3VQ_6njaAVxM`
Bytes: `426330`
SHA-256: `ec434d10167bcddc8d58027d0408a73946af1d41390e419c89a93d68df10ac85`

Producer validation is not independent-review evidence.

## Exact binding

- Candidate local bytes: `426330`.
- Local SHA-256: `ec434d10167bcddc8d58027d0408a73946af1d41390e419c89a93d68df10ac85`.
- Drive raw download: `426330` bytes.
- Drive raw SHA-256: exact match.
- JavaScript syntax via `node --check`: PASS.

## Sale-ready cancellation / non-mutation

Fresh seed state began with no commerce profiles, handoffs or reconciliation records.

Opening the rendered `Mark sale-ready` sheet for Atlas and closing it without saving left commerce state unchanged.

Result: **PASS — viewing/cancelling commerce preparation is non-mutating.**

## Betta individual — public/private evidence + handoff + reconciliation

Fresh canonical Atlas state was captured before commerce actions:

- exact recorded parent IDs retained;
- historical readiness retained;
- existing selection history retained;
- Pair Builder eligibility retained according to current breeder disposition;
- biological quantity = one individual;
- biological event count captured.

Through the rendered sale-ready flow:

1. marked Atlas sale-ready;
2. explicitly left `Sex` private;
3. retained identity, provenance and quantity as public fields;
4. saved existing evidence permissions;
5. created a structured AquaticFinder handoff for quantity `1`;
6. recorded a downstream AquaticFinder reconciliation of `Allocated=1 / Outcome=1 / Sold`.

Observed:

- handoff schema = `draneka.aquaticfinder.commerce-handoff.v1`;
- private `Sex` was absent from the handoff public facts;
- private `Sex` was absent from the generated provenance report;
- biological quantity remained `1` throughout;
- ancestry remained unchanged;
- no biological event was created by sale-ready, handoff or reconciliation;
- reconciliation history remained in the separate commerce ledger.

Result: **PASS.**

## v0.7 negative-disposition authority under commerce

From fresh seed state, Atlas was explicitly recorded `Non-breeding` through the rendered selection-session flow with a breeder reason.

Observed before commerce:

- historical `ready=true` remained;
- current disposition = `Non-breeding`;
- Pair Builder eligibility = false.

Atlas was then marked sale-ready and handed off to AquaticFinder.

Observed after commerce:

- historical readiness still remained;
- Pair Builder eligibility remained false;
- commerce state did not restore breeding authority.

Result: **PASS.**

## Medaka cohort — grouped quantity and hatch/output provenance

Fresh `cm02a` state was captured before commerce:

- grouped biological count = `5`;
- source output IDs captured;
- source hatch IDs captured;
- biological event count captured.

Through rendered commerce flows:

- marked the cohort sale-ready;
- prepared an AquaticFinder handoff for quantity `3`;
- reconciled downstream allocation `3` and outcome `2`.

Observed:

- Breeder cohort count remained `5`;
- source output IDs were unchanged;
- source hatch IDs were unchanged;
- no biological event was created.

Result: **PASS — downstream commerce allocation does not own or mutate biological quantity.**

## Medaka reproductive output / batch

Fresh output `m02` egg/hatch state was captured.

The output was marked sale-ready and a commerce handoff was prepared for quantity `2` from its current remaining biological output quantity.

Observed:

- recorded original egg quantity unchanged;
- recorded hatched quantity unchanged;
- hatch records/IDs unchanged;
- no hatch or biological mutation was inferred from commerce state.

Result: **PASS.**

## Neocaridina population-derived provenance

Fresh `cs` population-derived cohort state was captured.

The cohort was marked sale-ready and a structured handoff was created for quantity `10`.

Observed:

- biological count unchanged;
- Program parentage remained `Colony provenance only; parents unknown`;
- no exact parent IDs were created;
- handoff provenance explicitly retained colony/population parentage uncertainty and source-output identity.

Result: **PASS.**

## Annual killifish provenance / lifecycle boundary

Fresh Rachovii output `k01` state was captured:

- no wetting attempts;
- no hatch;
- lifecycle wetting review unresolved.

The output was marked sale-ready and a commerce handoff was created.

Observed:

- no wetting attempt was created;
- no hatch was created;
- lifecycle prompt state was unchanged;
- commerce did not resolve operational attention.

Result: **PASS.**

## Canonical v0.8 causal-resolution regressions

### `V08-IR-001`

From fresh Betta state:

1. grow-out plan `gp-betta-1` was `Planned` for a 30-fry split;
2. rendered count revision recorded `76 → 75` with reason `Full recount; no move or split occurred`;
3. plan remained `Planned`.

From fresh state, the actual rendered canonical split `76 = 30 + 46`, with the 30-fry child in planned target `tr2`, changed the plan to `Executed` and conserved quantity.

Result: **PASS — V08-IR-001 remains closed.**

### `V08-IR-002`

From fresh state:

1. opened the Rachovii wetting lifecycle action;
2. cancelled/closed it without saving;
3. verified pending lifecycle intent cleared;
4. recorded an unrelated detailed Betta feeding.

Observed:

- Rachovii lifecycle prompt remained unresolved;
- no wetting attempt or hatch was fabricated.

Result: **PASS — V08-IR-002 remains closed.**

## Breeder Round / operational attention boundary

Representative operational-attention IDs and statuses were captured before sale-ready + handoff actions.

After commerce preparation and handoff, the exact operational-attention set/statuses remained unchanged.

Result: **PASS — commerce state cannot close or suppress breeder operational attention.**

## Contextual navigation / anti-overwhelm

The candidate exposes commerce handoff contextually. It does not add a new bottom-navigation destination.

Bottom navigation remains exactly:

`Today / Programs / Log / Grow-out / More`

Result: **PASS.**

## Responsive/runtime matrix

Browser: Chromium `144.0.7559.96` on Debian GNU/Linux 13.

The exact SHA-bound candidate bytes were loaded in a real Chromium runtime. Representative surfaces at each width included:

- Today / home;
- commerce handoff summary;
- Atlas stock detail;
- Medaka cohort detail;
- Rachovii Program context;
- selection workspace;
- Pair Builder;
- More;
- stock sale-ready sheet;
- cohort sale-ready sheet;
- output/batch sale-ready sheet.

| Width | Applied | Document/body overflow | Relevant sheet overflow | Page errors | Console errors |
|---:|---:|---:|---:|---:|---:|
| 320 | 320 | 0 | 0 | 0 | 0 |
| 390 | 390 | 0 | 0 | 0 | 0 |
| 768 | 768 | 0 | 0 | 0 | 0 |
| 1440 | 1440 | 0 | 0 | 0 | 0 |

Result: **PASS.**

## Scope discipline

Producer inspection found no admitted:

- marketplace listing-management UI;
- eBay/Etsy/etc. channel operations;
- pricing optimization;
- sales CRM;
- payment processing;
- order management;
- shipping/fulfilment;
- finance/accounting;
- public marketplace browsing;
- broad inventory ERP;
- genotype inference;
- automatic biological completion;
- backend/API/schema/database/deployment/production mutation;
- Android or web implementation authority;
- v1.0 feature expansion.

Result: **PASS.**

## Producer qualification

```text
HOLISTIC_V0_9_EXACT_BINDING = PASS
HOLISTIC_V0_9_DRIVE_ROUND_TRIP = PASS
HOLISTIC_V0_9_SALE_READY_BOUNDARY = PASS
HOLISTIC_V0_9_PUBLIC_PRIVATE_EVIDENCE = PASS
HOLISTIC_V0_9_AQUATICFINDER_HANDOFF = PASS
HOLISTIC_V0_9_PROVENANCE_REPORT = PASS
HOLISTIC_V0_9_QUANTITY_OWNERSHIP_BOUNDARY = PASS
HOLISTIC_V0_9_COMMERCE_RECONCILIATION_BOUNDARY = PASS
HOLISTIC_V0_9_V0_8_REGRESSION = PASS
HOLISTIC_V0_9_V0_7_TARGETED_REGRESSION = PASS
HOLISTIC_V0_9_V0_6_TARGETED_REGRESSION = PASS
HOLISTIC_V0_9_V0_5_TARGETED_REGRESSION = PASS
HOLISTIC_V0_9_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_9_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_9_PRODUCER_VALIDATION = PASS
HOLISTIC_V0_9_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES
HOLISTIC_V0_9_PROMOTION_ELIGIBLE = NO_PENDING_INDEPENDENT_REVIEW
HOLISTIC_V0_9_CANONICAL = NO
PR_9_MERGE = HOLD
```

The fresh independent reviewer must establish every required result independently from the exact Drive bytes. Producer validation must not be inherited as evidence.
