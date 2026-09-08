# ROLE = INDEPENDENT DRANEKA AQUARIUM BREEDER HOLISTIC V0.8 BOUNDED-CORRECTION REVIEWER

Perform a **fresh independent review** of the exact corrected holistic v0.8 candidate identified below.

Do **not** inherit PASS claims from:

- the producer;
- bounded-correction producer validation;
- Founder scope prose;
- PR descriptions;
- durable candidate/correction receipts;
- the previous independent review except as the definition of the two defects that must be reproduced;
- earlier conversation context.

Establish the result independently from the exact artifact under review.

Do not redesign or modify the prototype.
Do not promote it.
Do not merge PR #8.
Do not mutate either Drive candidate object.
Do not mutate backend, API, schema, database, deployment, production, Android, release state, or v0.9+ scope.

Your task is to determine whether the bounded correction actually closes `V08-IR-001` and `V08-IR-002` without regressing the complete holistic v0.8 operational-scale objective or canonical v0.7/v0.6/v0.5 authority.

---

# 1. Exact corrected candidate under review

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-BOUNDED-CORRECTION-CANDIDATE.html`

Google Drive ID:

`1Lrdd1OX0I297hS3fBHXOSk6lmAwws3y9`

Expected bytes:

`391223`

Expected SHA-256:

`524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`

Repository:

`nickdevph/draneka-breeder`

PR:

`#8 — Holistic v0.8 — Operational scale`

Branch:

`prototype/v0.8-operational-scale`

Base:

`main`

Before product review, independently download the corrected Drive object, measure bytes and calculate SHA-256. If any value differs, stop with:

`FAIL — EXACT_BINDING_MISMATCH`

Independently bind the PR head present when review begins. Record that exact pre-receipt head. A later review-only receipt commit is permitted, but no product/candidate mutation is permitted during review.

---

# 2. Historical failed candidate and prior review

The original v0.8 candidate remains immutable historical evidence and is **not** the current review target:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-CANDIDATE.html`
- Drive ID: `1SVaVXVm4DEOXyx8lxxRlMBbj8CUQsPS8`
- Bytes: `386074`
- SHA-256: `9dea5ada178d0814f86d2014a05ece56f8ed2c2be4f79f64ab2f34560b3f4704`
- Prior independent disposition: `CHANGES_REQUIRED`
- Exact prior pre-receipt head: `5fcf45b2d20a30bfa17458c9473b5664f9c8a06e`
- Prior review receipt: `reviews/holistic-v0.8-independent-review-2026-09-08.md`
- Receipt-only commit: `6285ee4df025f375527d3450c4769c1ffc21dc55`

Use the prior review only to reproduce the two reported failures. Do not inherit its PASS results for any other gate; rerun the required gates freshly on the corrected bytes.

---

# 3. Canonical predecessor to protect

Holistic v0.7 remains the current canonical product/design authority.

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`

Google Drive ID:

`1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`

Expected bytes:

`334514`

Expected SHA-256:

`1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`

Canonical merge commit:

`11f0adba6b821cd5b3c6642d6927ba25930266bb`

Independently bind the predecessor. Do not rely on producer statements.

---

# 4. Required direct reproduction — V08-IR-001

## Prior defect

An unrelated cohort mutation could falsely execute a grow-out split plan.

## Mandatory negative reproduction

Start from fresh seeded Betta state:

- source cohort count `76`;
- source cohort in its original tank;
- explicit grow-out plan `gp-betta-1` in `Planned` state;
- plan requires a split of `30` fry to the planned target grow-out tank.

Then:

1. Use the canonical **count revision** flow only.
2. Record `76 → 75` with a reason explicitly stating that no move or split occurred.
3. Verify the saved event remains a count revision and not mortality.
4. Verify source cohort remains in the same tank and remains active.
5. Verify the grow-out plan remains `Planned`.
6. Verify no execution-history entry is appended.

Also independently exercise at least two other unrelated mutation classes among mortality, feeding, life-stage update, or observation and confirm none can execute the plan.

Any unrelated mutation that executes the plan is a **MAJOR** failure.

## Mandatory positive matching-operation test

From fresh seed state:

1. Execute the actual canonical split operation required by the plan.
2. Conserve `76 = 30 + 46`.
3. Put the planned 30-animal child in the explicitly planned target location.
4. Verify source becomes historical only because the real split occurred.
5. Verify provenance survives on the resulting cohorts.
6. Verify the plan changes to `Executed` only after that matching operation.
7. Verify execution history identifies the exact matching split event rather than a generic later mutation.

If the intended matching operation no longer executes the plan, the correction is also defective.

---

# 5. Required direct reproduction — V08-IR-002

## Prior defect

A cancelled lifecycle action remained armed and an unrelated later record could falsely close the lifecycle prompt.

## Mandatory negative reproduction

1. Open annual-killifish lifecycle item `Review Rachovii egg-medium development`.
2. Choose `Record wetting attempt`.
3. Cancel/close the wetting form **without saving**.
4. Record an unrelated detailed Betta feeding.
5. Verify the Rachovii lifecycle prompt remains unresolved / `done=false`.
6. Verify no lifecycle history claims it was resolved.
7. Verify no unrelated Betta event ID is attached to lifecycle history.
8. Verify no wetting attempt or hatch was created by the cancelled action.

Repeat with at least one other unrelated record type if practical.

Any unrelated record that closes the lifecycle prompt is a **MAJOR** failure; any fabricated wetting/hatch remains a **BLOCKER**.

## Mandatory positive matching-record test

From fresh seed state:

1. Open the same lifecycle prompt.
2. Choose `Record wetting attempt`.
3. Save a real Rachovii wetting attempt in the intended Program/output context.
4. Verify exactly one new wetting attempt is created.
5. Verify no hatch is created merely by wetting.
6. Verify the lifecycle prompt resolves only after that matching wetting record.
7. Verify lifecycle history links the exact matching wetting event/attempt identity.

---

# 6. Re-run all holistic v0.8 operational-scale gates

Do not limit the review to the two defect reproductions. Freshly establish all of the following on the corrected bytes.

## G1 — Dynamic Breeder Round authority

Prove Breeder Round derives from current operational evidence and updates correctly as sources change:

- one-off plans;
- recurring schedules;
- lifecycle prompts;
- overdue/exception state;
- capacity context;
- grow-out plans;
- critical culture/dependency state;
- source/reason/context traceability.

No attention item may close because of an unrelated record.

## G2 — Due does not mean done

Exercise due, overdue, explicit completion, defer, skip and future cadence edit.

Historical occurrences/reasons must remain append-only and due state must never fabricate completion.

## G3 — Schedule completion vs detailed husbandry

Using the Betta recurring feeding schedule, prove operational completion remains separate from a real detailed feed event and does not invent food/portion data.

## G4 — Lifecycle suggestion vs biological fact

Freshly exercise:

- annual killifish wetting review → explicit wetting → re-dry → later distinct wetting → explicit hatch;
- Medaka hatch review vs explicit hatch;
- Betta/guppy/Apistogramma lifecycle prompts where applicable.

Timing or prompt completion must not fabricate biology.

## G5 — Capacity unknown/known semantics

Unknown capacity remains unknown. Known planning pressure derives only from breeder-entered planning context + recorded quantities. No automatic operational action may result.

## G6 — Grow-out plan vs real mutation

Re-establish plan-only behavior, cancellation behavior, correct move/split matching, quantity conservation and provenance retention, including the direct `V08-IR-001` tests above.

## G7 — Critical live-food/culture dependency

Explicit dependency only; at-risk state may elevate attention; culture maintenance/status changes append history; they must not create feeding or silently complete linked husbandry.

## G8 — Explainability/history

For representative items, establish visible source class, reason, Program/cohort/tank/resource context, due/window, operational state, and exact closing/defer/skip/change history. No false or unrelated event linkage is acceptable.

## G9 — Anti-overwhelm/product shape

Breeder Round remains the operational home. No generic task/project ERP surface, Kanban/Gantt, or second commerce app is admitted. At-risk/overdue/due work should remain prioritized ahead of upcoming/contextual work.

---

# 7. Mandatory canonical v0.7 regression

Freshly exercise at minimum:

1. initial breeding-goal history exists;
2. goal edits append rather than rewrite;
3. phenotype evaluation remains observation/assessment/evidence, not genotype authority;
4. missing evidence remains explicit;
5. historical selection reasons retain their original goal snapshot;
6. `Non-breeding`, `Retire`, and `Sale / rehome` preserve historical readiness but block current breeding-stock and Pair Builder eligibility;
7. `Holdback` remains readiness-neutral;
8. Pair Builder cannot reintroduce a stale ineligible parent via options, active state, relationship calculation/sheet, example/recovery behavior or continuation controls;
9. exact Betta full-sibling ancestry remains visible;
10. mixed filial parentage does not fabricate the next generation;
11. Program isolation remains identity-based;
12. population-derived selection preserves population provenance without exact-parent fabrication.

Any reopening of stale Pair Builder authority is a promotion blocker.

---

# 8. Mandatory canonical v0.6 species/provenance regression

Freshly exercise:

- Betta controlled ancestry/relatedness;
- guppy known/unknown parentage uncertainty;
- Medaka distinct output/hatch provenance;
- Neocaridina population-derived provenance;
- annual killifish wetting → re-dry → later wetting → explicit hatch authority;
- mop/plant collection without inferred hatch/offspring.

Operational attention must not rewrite biological provenance.

---

# 9. Mandatory canonical v0.5 cohort-operation regression

Freshly exercise rendered canonical operations:

- count revision distinct from mortality;
- mortality updates losses/count;
- move retains cohort identity/provenance;
- split conserves quantity/provenance;
- merge avoids double counting and preserves source history;
- life-stage update does not alter count/provenance;
- detailed feeding remains an explicit care event.

The corrected plan-resolution logic must not hijack unrelated canonical operations.

---

# 10. Responsive/runtime qualification

Use a real browser against the **exact SHA-bound corrected bytes**.

Required exact CSS widths:

- `320`
- `390`
- `768`
- `1440`

At every width, exercise at minimum:

- Today / dynamic operational home and all populated attention bands;
- Breeder Round;
- recurring schedule completion/defer/skip/edit;
- lifecycle prompt detail including cancel-then-unrelated-record reproduction;
- capacity detail including unknown;
- grow-out plan detail including unrelated count revision and actual matching split;
- culture dependency update;
- Program/cohort detail;
- selection & line development;
- Pair Builder negative-disposition stale-parent path;
- annual killifish wet/re-dry/later-wet/explicit-hatch;
- Medaka collection/hatch;
- canonical count/mortality/move/split/merge/stage/feed.

Required at every width:

- exact viewport width applied;
- no document/body horizontal overflow;
- no relevant dialog/sheet horizontal overflow;
- zero page errors;
- zero console errors.

Do not use producer screenshots or producer runtime claims as independent evidence.

---

# 11. Scope discipline

Fail or require changes for any introduced:

- automatic biological completion;
- opaque AI operational authority;
- automatic cull/move/split/pairing/selection/sale/rehome decision;
- authoritative stocking limit from unrecorded assumptions;
- generic task/project-management expansion;
- genotype prediction from phenotype;
- v0.9 sale-ready/commerce handoff;
- marketplace listing/channel/pricing/CRM/payment/order/shipping workflow;
- backend/API/schema/database/deployment/production mutation;
- Android/web implementation authority.

---

# 12. Finding classifications

- **BLOCKER** — exact-binding failure, fabricated biological fact, canonical provenance corruption, stale Pair Builder authority bypass, or severe authority failure.
- **MAJOR** — either prior MAJOR remains reproducible, matching operation no longer works, a material v0.8 gate fails, canonical regression occurs, or required responsive/runtime qualification fails.
- **MINOR** — bounded non-authority defect that does not invalidate the product objective.
- **NOTE** — observation only.

Do not downgrade a semantic authority defect because UI presentation looks plausible.

---

# 13. Final disposition

Return exactly one of:

- `PASS`
- `CHANGES_REQUIRED`
- `FAIL`

`PASS` requires:

- corrected candidate and predecessor exact bindings pass;
- `V08-IR-001` is independently closed in both negative and positive tests;
- `V08-IR-002` is independently closed in both negative and positive tests;
- all G1–G9 gates pass;
- canonical v0.7/v0.6/v0.5 regressions pass;
- exact-width responsive/runtime matrix passes;
- scope discipline passes;
- no unresolved BLOCKER or MAJOR remains.

If PASS, explicitly report at least:

```text
V08_IR_001 = CLOSED
V08_IR_002 = CLOSED
HOLISTIC_V0_8_BOUNDED_CORRECTION_EXACT_BINDING = PASS
HOLISTIC_V0_8_PRODUCT_OBJECTIVE = PASS
HOLISTIC_V0_8_DYNAMIC_BREEDER_ROUND = PASS
HOLISTIC_V0_8_RECURRING_SCHEDULES = PASS
HOLISTIC_V0_8_LIFECYCLE_BOUNDARY = PASS
HOLISTIC_V0_8_CAPACITY_SEMANTICS = PASS
HOLISTIC_V0_8_GROWOUT_PLAN_BOUNDARY = PASS
HOLISTIC_V0_8_CULTURE_DEPENDENCY = PASS
HOLISTIC_V0_8_EXPLAINABILITY_HISTORY = PASS
HOLISTIC_V0_8_V0_7_REGRESSION = PASS
HOLISTIC_V0_8_V0_6_REGRESSION = PASS
HOLISTIC_V0_8_V0_5_REGRESSION = PASS
HOLISTIC_V0_8_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_8_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_8_INDEPENDENT_REVIEW = PASS
HOLISTIC_V0_8_PROMOTION_ELIGIBLE = YES_PENDING_FOUNDER_PROMOTION
HOLISTIC_V0_8_CANONICAL = NO
PR_8_MERGE = HOLD
```

If repository workflow requires a review receipt, a **review-only receipt** may be committed after review. Record both the exact pre-receipt head exercised and the receipt-only commit. Do not mutate product bytes, promote, or merge as part of independent review.