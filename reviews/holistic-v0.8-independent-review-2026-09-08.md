# Draneka Aquarium Breeder — Holistic v0.8 Independent Review

Date: 2026-09-08

Disposition: **CHANGES_REQUIRED**

This is a review-only receipt. It does not modify candidate bytes, product source, backend/API/schema/database/deployment/production state, Android, release state, or canonical authority. PR #8 remains merge-hold.

## Exact review binding

Candidate:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-CANDIDATE.html`
- Drive ID: `1SVaVXVm4DEOXyx8lxxRlMBbj8CUQsPS8`
- Independently measured bytes: `386074`
- Independently calculated SHA-256: `9dea5ada178d0814f86d2014a05ece56f8ed2c2be4f79f64ab2f34560b3f4704`

Canonical predecessor:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`
- Independently measured bytes: `334514`
- Independently calculated SHA-256: `1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`
- Canonical base independently observed on PR #8: `11f0adba6b821cd5b3c6642d6927ba25930266bb`

PR #8 exact pre-receipt head exercised:

`5fcf45b2d20a30bfa17458c9473b5664f9c8a06e`

PR state at review: open, unmerged, branch `prototype/v0.8-operational-scale`, base `main`.

## Independent method

The Drive objects were downloaded independently and byte/hash-bound before product review. The exact v0.8 HTML bytes were loaded into Chromium `144.0.7559.96` and exercised through rendered UI operations. Fresh demo state was used for independent semantic paths where isolation was required. Exact CSS widths `320`, `390`, `768`, and `1440` were applied and verified at runtime.

No producer validation or prior PASS disposition was used as review evidence.

## Promotion-blocking findings

### MAJOR V08-IR-001 — Unrelated cohort count revision falsely executes a grow-out split plan

Reproduction:

1. Start from the seeded Betta cohort `Copper fry · 04`, count `76`, with the explicit grow-out split plan `gp-betta-1` in `Planned` state for 30 fry to R2.
2. Use the canonical count-revision UI only.
3. Record `76 → 75` with reason `Independent reviewer recount; no move or split performed`.
4. Observe the cohort remains in the same tank and active state and the saved event is a `count` event whose note explicitly says the `-1` difference is an unexplained revision, not mortality.
5. Observe the grow-out plan nevertheless changes from `Planned` to `Executed` and appends history claiming the plan was executed after an explicit cohort mutation.

Impact:

A count correction, mortality, or otherwise unrelated cohort mutation can satisfy the v0.8 plan-execution hook even when the planned move/split did not occur. This violates G6: a plan must become executed only after the actual planned canonical operation occurs. It also makes operational history unreliable at scale.

Classification: **MAJOR**.

### MAJOR V08-IR-002 — Cancelled lifecycle action remains armed and an unrelated record can close the lifecycle prompt

Reproduction:

1. Open the annual-killifish lifecycle item `Review Rachovii egg-medium development`.
2. Choose `Record wetting attempt`.
3. Cancel the wetting form without saving.
4. Record an unrelated detailed Betta feeding (`Microworms · small feed · 09:30`).
5. Observe the killifish lifecycle prompt becomes `done=true`.
6. Observe lifecycle history says `Resolved by explicit record`, links the unrelated Betta feeding event, and claims the prompt closed after the related explicit record.

Impact:

The lifecycle prompt can be removed from operational attention by an unrelated record after its intended action was cancelled. No wetting or hatch is fabricated, so this is not classified as a biological-authority BLOCKER; however, lifecycle resolution and explainability/history are materially false. This violates G1, G4, and G8 and makes the operational home unreliable.

Classification: **MAJOR**.

No BLOCKER was found in the reviewed candidate. The two MAJOR findings are independently sufficient for `CHANGES_REQUIRED`.

## v0.8 gate results

| Gate | Result | Independent evidence |
|---|---|---|
| G1 Dynamic Breeder Round authority | **FAIL** | Initial attention is dynamically composed from explicit plans, schedules, lifecycle, capacity, grow-out and culture state with risk ordering and source/context; however V08-IR-002 can remove a lifecycle item after an unrelated record. |
| G2 Due does not mean done | **PASS** | Due state created no completion. Completion appended occurrence history; defer preserved original due occurrence; skip created no husbandry/biology; cadence edit preserved prior history and changed future cadence only. |
| G3 Schedule completion vs detailed husbandry | **PASS** | Betta schedule completion produced an operational `check` record, not a `feed` payload; no food/portion was invented; separate detailed feeding remained available and produced a real `feed` event only when explicitly recorded. |
| G4 Lifecycle suggestion vs biological fact | **FAIL** | Direct annual-killifish/Medaka checks do not create wetting/hatch; Betta/guppy/Apisto checks do not mutate cohort reality. Explicit killifish wet → re-dry → later wet → observed hatch provenance works. But V08-IR-002 falsely resolves lifecycle attention/history after an unrelated record. |
| G5 Capacity unknown/known semantics | **PASS** | Blank planning ceiling stays explicitly unknown; no stocking limit is invented. Known pressure derives from recorded quantity plus breeder-entered ceiling explicitly presented as planning context, not biological truth. No automatic action occurs. |
| G6 Grow-out plan vs real mutation | **FAIL** | Plan creation itself does not mutate cohort reality and real split conserves quantity/provenance, but V08-IR-001 falsely marks the split plan executed after a count revision with no move/split. |
| G7 Critical culture dependency | **PASS** | Explicit Artemia dependency elevates at-risk attention; maintenance/status update appends history; availability update creates no feeding and does not complete the linked fry husbandry schedule. |
| G8 Explainability/history | **FAIL** | Normal items expose source/reason/context/due/state and schedule history preserves occurrence reasons, but V08-IR-002 records a false lifecycle closure reason and unrelated event link. |
| G9 Anti-overwhelm/product shape | **PASS** | Breeder Round remains operational home; default ordering is At risk → Overdue → Due → Needs context → Upcoming. Top-level navigation remains Today / Programs / Log / Grow-out / More. No Kanban, Gantt, generic ERP or second commerce surface was found. |

## Canonical v0.7 regression

**PASS**.

Fresh checks established:

- initial breeding-goal history exists and goal edits append rather than rewrite;
- existing selection-session goal snapshots survive later goal edits;
- phenotype evaluation records assessment/traits/evidence context without genotype authority;
- missing evidence is rendered explicitly as missing / insufficient;
- `Non-breeding`, `Retire`, and `Sale / rehome` each preserve historical readiness while making the stock non-selectable and Pair Builder-ineligible;
- requesting an ineligible Atlas parent recovers to eligible parents; Atlas is absent from Pair Builder options and relationship rendering;
- `Holdback` leaves already-ready stock ready and does not make a non-ready candidate ready;
- Atlas × Iris retains exact recorded full-sibling evidence through Ember + Lyra;
- mixed F1 × F2 recorded parents produce `Generation not established · recorded parents F1 × F2`, not a fabricated next generation;
- Program isolation remains identity-based: an injected same-species/same-line cohort in a different Program is not admitted as a merge candidate;
- a population-derived Neocaridina selection retains `sourceStockIds=['blue-colony']`, source output `s01`, empty exact `parentIds`, and `Generation not established · source population/group recorded`.

The former stale Pair Builder parent-authority defect is not reopened.

## Canonical v0.6 species/provenance regression

**PASS**.

Fresh checks established:

- Betta controlled ancestry / full-sibling relatedness remains explicit;
- guppy mother-known / sire-unknown uncertainty remains explicit;
- Medaka reproductive outputs retain distinct hatch records and hatch-to-cohort provenance;
- a new Medaka collection creates egg/source evidence only, with no inferred hatch or offspring;
- Neocaridina population provenance retains unknown exact parents;
- annual killifish first wetting, re-dry, second wetting, and explicit hatch remain distinct records; the hatch links to the second wetting attempt and resulting cohort provenance retains the correct output/hatch/wetting identifiers.

## Canonical v0.5 cohort-operation regression

**PASS**.

Fresh rendered operations established:

- count revision remains distinct from mortality;
- explicit mortality changes count/loss state;
- move keeps the same cohort identity and source provenance;
- split conserves `76 = 30 + 46` and preserves source provenance;
- merge returns the split descendants to an exact total of `76`, retains both source histories, and avoids double counting;
- life-stage update changes only the observed stage, not count/provenance;
- detailed feeding remains an explicit `feed` event.

## Responsive/runtime matrix

Chromium `144.0.7559.96`.

| Exact CSS width | Applied | Document/body horizontal overflow | Tested sheet/dialog overflow | Page errors | Console errors |
|---:|---:|---:|---:|---:|---:|
| 320 | 320 | 0 | 0 | 0 | 0 |
| 390 | 390 | 0 | 0 | 0 | 0 |
| 768 | 768 | 0 | 0 | 0 | 0 |
| 1440 | 1440 | 0 | 0 | 0 | 0 |

At every width, the review exercised the dynamic home/attention bands (including Needs context), Breeder Round, recurring schedule detail/completion/defer/skip/edit, lifecycle detail, unknown capacity, grow-out create/edit/detail and real split/merge path, culture update, Program/cohort/selection/Pair Builder, annual-killifish wet/re-dry/second-wet/explicit-hatch path, Medaka collection/explicit-hatch path, and canonical count/mortality/move/split/merge/stage/feed operations.

Responsive/runtime qualification: **PASS**.

## Scope discipline

**PASS**.

No automatic biological completion, opaque AI operational authority, automatic cull/move/split/pairing/selection/sale/rehome decision engine, unrecorded authoritative stocking limit, generic project-management product, genotype prediction workflow, v0.9 commerce handoff, marketplace/pricing/CRM/payment/order/shipping workflow, or implementation/backend authority was found in the admitted v0.8 surface.

## Final authority state

```text
HOLISTIC_V0_8_EXACT_BINDING = PASS
HOLISTIC_V0_8_PRODUCT_OBJECTIVE = FAIL
HOLISTIC_V0_8_DYNAMIC_BREEDER_ROUND = FAIL
HOLISTIC_V0_8_RECURRING_SCHEDULES = PASS
HOLISTIC_V0_8_LIFECYCLE_BOUNDARY = FAIL
HOLISTIC_V0_8_CAPACITY_SEMANTICS = PASS
HOLISTIC_V0_8_GROWOUT_PLAN_BOUNDARY = FAIL
HOLISTIC_V0_8_CULTURE_DEPENDENCY = PASS
HOLISTIC_V0_8_EXPLAINABILITY_HISTORY = FAIL
HOLISTIC_V0_8_V0_7_REGRESSION = PASS
HOLISTIC_V0_8_V0_6_REGRESSION = PASS
HOLISTIC_V0_8_V0_5_REGRESSION = PASS
HOLISTIC_V0_8_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_8_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_8_INDEPENDENT_REVIEW = CHANGES_REQUIRED
HOLISTIC_V0_8_PROMOTION_ELIGIBLE = NO
HOLISTIC_V0_8_CANONICAL = NO
PR_8_MERGE = HOLD
```

Required correction scope is bounded to the two v0.8 operational-authority defects above. Canonical v0.7/v0.6/v0.5 behavior passed this review and should remain protected during correction.