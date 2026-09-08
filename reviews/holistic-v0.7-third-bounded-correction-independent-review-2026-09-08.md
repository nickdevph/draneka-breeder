# Independent review — Holistic v0.7 third bounded correction

Date: 2026-09-08
Role: Independent Draneka Aquarium Breeder v0.7 third bounded-correction reviewer
Disposition: **PASS**

This review was performed freshly against the exact Drive-bound candidate. Producer claims, prior review dispositions, Founder claims, PR prose, and producer receipts were not treated as correctness evidence.

No promotion or merge was performed. v0.6 remains canonical pending Founder promotion and a later governed merge of PR #7.

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`
- Independently measured bytes: `334514`
- Independently calculated SHA-256: `1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`
- Exact binding: **PASS**

The object was independently retrieved from Drive and hashed from the downloaded bytes before product review.

## Canonical predecessor binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Independently measured bytes: `295505`
- Independently calculated SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical merge/base commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`
- Binding: **PASS**

## PR binding before receipt

- Repository: `nickdevph/draneka-breeder`
- PR: `#7 — Holistic v0.7 — Selection and line development`
- Branch: `prototype/v0.7-selection-line-development`
- Base: `main`
- Exact pre-receipt head reviewed: `2d3bbbc3ef287689bb326a2ed70e0fb1d903e6e5`
- Base SHA: `f38b9546665df806ab2fe3b91749abcb4ba020fe`
- PR state before receipt: open, unmerged

The branch head above is the product/review head that was exercised. This receipt is a review-only mutation after that review head.

## Browser/runtime method

- Chromium: `144.0.7559.96` on Debian GNU/Linux 13
- Playwright: `1.57.0`
- Load method: the exact independently hashed HTML bytes were decoded and loaded directly into a real Chromium document with `page.set_content()`; the candidate was not reconstructed or modified.
- Exact widths exercised: `320`, `390`, `768`, `1440` CSS px.
- At every width: `window.innerWidth` and document client width matched the target exactly; document/body scroll widths stayed within the viewport; relevant sheets/dialogs stayed horizontally contained; page errors = 0; console errors = 0.

## V07-SECOND-IR-001 — Pair Builder stale-parent authority bypass

**PASS — blocker closed.**

Fresh UI reproduction was executed separately for `Non-breeding`, `Retire`, and `Sale / rehome` on already-ready `Atlas · retained F2`.

For each negative disposition:

- historical `ready=true` remained historical evidence;
- current disposition persisted;
- `breedingStockSelectable(Atlas)=false`;
- `pairBuilderEligible(Atlas)=false`;
- Atlas was absent from Pair Builder options;
- Atlas was absent from active Stock A / Stock B state;
- Atlas was absent from active relationship title/path/coverage state;
- relationship-sheet and continuation state did not use Atlas;
- example/demo controls did not reintroduce Atlas.

The Pair Builder normalized to currently eligible records only when another valid pair existed.

Stale-state test also passed: an established `Atlas × Iris` Pair Builder state was followed by a current `Non-breeding` disposition on Atlas. On revisit, Atlas was normalized out and the active state contained only currently eligible parents.

No-valid-parent fail-closed behavior passed on a one-parent guppy context: no fabricated Stock B, no relationship result using an invalid hidden parent, and no continuation action was available until two eligible parents existed.

## Holdback semantics

**PASS.**

- Ready Atlas → `Holdback`: historical readiness remained true; Holdback did not block eligibility by itself.
- Newly selected non-ready candidate → `Holdback`: readiness remained false; Holdback did not manufacture readiness; breeding-stock and Pair Builder eligibility remained false.

## Sale / rehome scope boundary

**PASS.**

A selection-session `Sale / rehome` decision persisted only as a disposition/history record. It did not create exits, marketplace/listing state, pricing, sales-channel allocation, CRM, payment, or commerce state. No commerce keys or workflow were introduced.

## Filial-generation precision

**PASS.**

A rendered end-to-end mixed-filial path was created with an exact F1 parent and exact F2 parent, then a controlled spawn, explicit hatch, offspring cohort, and named selected offspring.

Observed selected-offspring result:

`Generation not established · recorded parents F1 × F2`

Exact parent IDs remained preserved; no F3 was fabricated; generation certainty remained distinct from identity.

Legitimate exact same-line `F1 × F1 → F2` handling was also independently established from the controlled Betta lineage: Ember F1 + Lyra F1 are exact recorded parents of Atlas/Iris F2.

## Population-derived generation

**PASS.**

A new named selection from the Neocaridina population retained the source population/group provenance, had no fabricated exact parent IDs, remained `Generation not established · source population/group recorded`, and remained Pair Builder-ineligible while not exact-lineage/ready evidence.

## Initial breeding-goal history

**PASS.**

The annual killifish Program already contained an initial goal-history record before any edit.

Existing Copper Program test:

- pre-existing history remained unchanged;
- editing the current goal appended a new record;
- prior phenotype-evaluation goal snapshots were unchanged;
- prior selection-session goal snapshots/reasons were unchanged.

New Program test:

- a Program created with an initial goal immediately had an initial goal-history record before any later edit;
- editing appended a second record rather than rewriting the first.

## Program isolation

**PASS.**

A second Betta Program was created with the same species and the exact same breeder-entered line text (`Copper halfmoon`). Its selected juvenile did not leak into the original Copper Program selection candidates, selection sessions/evidence, or Pair Builder eligibility merely through species/line-text equality.

## Phenotype / genotype boundary and evidence

**PASS.**

A phenotype evaluation with a real image file attached through the rendered ordinary evaluation flow retained the attachment on the correct evaluation and displayed it as evidence. The evaluation persisted observed traits, breeder assessment, notes, timestamp and goal snapshot.

A second evaluation saved without evidence remained visibly `0 evidence items` and explicitly displayed `No photo/evidence attachment recorded for this evaluation.` It retained `Not enough evidence` rather than receiving an invented score/evidence value.

No genotype/allele state was established by either observation. The rendered stock/evaluation surfaces explicitly kept genotype not established and described phenotype as observation/evidence rather than genetic proof.

## Selection history

**PASS.**

A newly recorded `Retire` selection decision retained its breeder-entered reason and original goal snapshot after the current Program goal was later edited. The historical session remained byte-for-byte equivalent in its rationale fields while the current goal changed.

## Betta provenance / relatedness

**PASS.**

Exact controlled ancestry remained intact. Pair Builder rendered Atlas × Iris as full siblings with shared recorded parents `Ember + Lyra`, exposed the relationship path and coverage, and allowed the breeder to decide whether to continue. The UI explicitly states that it does not issue an opaque authoritative “best pair” recommendation.

## Fancy guppy uncertainty

**PASS.**

Rendered guppy lineage retained `Known mother / unknown sire` / `Mother recorded; sire unknown`. No sire was invented and phenotype evidence did not resolve missing parentage.

## Medaka provenance

**PASS.**

The 8 September Medaka collection retained two distinct hatch observations and two distinct cohorts, each with its own hatch provenance ID while sharing the same source output. Exact egg parents remained unassigned to the breeding-group-derived source.

## Neocaridina provenance

**PASS.**

Rendered lineage remained colony/population-derived with parents unknown; named selection retained source-group provenance; no exact parents were fabricated; Pair Builder remained conservative.

## Count and provenance operations

**PASS through saved rendered UI operations.**

- Count revision: 76 → 75 created a `count` event and explicitly recorded the difference as unexplained, not mortality; mortality ledger did not change.
- Mortality: a separate explicit 2-loss event changed the cohort count and recorded-loss ledger.
- Move: cohort ID and source output/hatch provenance remained unchanged while tank changed.
- Split: 73 conserved as 30 + 43; both children retained source output/hatch provenance; the source became historical and was excluded from live totals.
- Merge: the two children recombined to exactly 73; both sources became historical and the merged group retained provenance without double counting.
- Life-stage update: changed only the observed lifecycle label; count/tank/source provenance remained intact.
- Feeding: created a shared operational feed event and did not mutate provenance.

## Full canonical v0.6 annual-killifish regression

**PASS.**

Starting from the existing `k01` egg-medium batch:

1. Wetting attempt 1 was recorded.
2. No hatch or cohort was created by wetting.
3. Attempt 1 was explicitly re-dried and remained a distinct historical attempt.
4. Wetting attempt 2 was recorded as a separate attempt.
5. Still no hatch/cohort existed until explicit hatch recording.
6. An observed 7-fry hatch was explicitly recorded and linked to attempt 2.
7. The new cohort retained source output `k01`, the exact new hatch ID, and wetting-attempt-2 provenance.
8. Attempt 1 remained re-dried with no hatch IDs and was not rewritten as the successful attempt.

## Killifish mop / plant regression

**PASS.**

The rendered method switch created no biological record. A real mop/plant collection flow then recorded an 11-egg `mop-plant` output with spawning-mop/plant source context. It created no hatch, no offspring cohort and no inferred reproductive success.

## Responsive/runtime matrix

**PASS.**

At each exact width (`320`, `390`, `768`, `1440`) the following were exercised in real Chromium against the exact bytes: home, Programs, Program detail, Selection & line development, selection-session dialog, Pair Builder with a negative disposition, phenotype-evaluation dialog, stock detail, cohort detail, lineage, cohort selection, count revision, mortality, move, split, merge, life-stage update, feeding, annual killifish wetting → re-dry → second wetting → explicit hatch, and mop/plant collection.

All tested layout checks passed with no horizontal document/body overflow or relevant sheet overflow and zero console/page errors.

## Scope discipline

**PASS.**

No unauthorized v0.8 dynamic scheduling/capacity/workload forecasting functionality was found. No v0.9 marketplace/listing/channel allocation/CRM/pricing/payment workflow was found. No backend/API/schema/database/deployment/production/Android mutation was performed or introduced. No phenotype-to-genotype inference and no authoritative best-pair engine were present.

## Findings and disposition

No promotion blocker remains. `V07-SECOND-IR-001` is independently closed. No collateral canonical-v0.6 regression was reproduced, and no unauthorized scope expansion was found.

**Final disposition: PASS**

```text
HOLISTIC_V0_7_EXACT_BINDING = PASS
HOLISTIC_V0_7_PRODUCT_OBJECTIVE = PASS
HOLISTIC_V0_7_GOAL_HISTORY = PASS
HOLISTIC_V0_7_PHENOTYPE_EVALUATION = PASS
HOLISTIC_V0_7_EVIDENCE_ATTACHMENT = PASS
HOLISTIC_V0_7_SELECTION_SESSION = PASS
HOLISTIC_V0_7_PROGRAM_ISOLATION = PASS
HOLISTIC_V0_7_DISPOSITION_SEMANTICS = PASS
HOLISTIC_V0_7_GENERATION_PRECISION = PASS
HOLISTIC_V0_7_PHENOTYPE_GENOTYPE_BOUNDARY = PASS
HOLISTIC_V0_7_PAIR_BUILDER_AUTHORITY = PASS
HOLISTIC_V0_7_V0_7_REGRESSION = PASS
HOLISTIC_V0_7_V0_6_REGRESSION = PASS
HOLISTIC_V0_7_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_7_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_7_INDEPENDENT_REVIEW = PASS
HOLISTIC_V0_7_PROMOTION_ELIGIBLE = YES_PENDING_FOUNDER_PROMOTION
HOLISTIC_V0_7_CANONICAL = NO
PR_7_MERGE = HOLD
```

Receipt-only commit SHA is recorded by the enclosing GitHub commit for this file and is reported in the independent-review result after creation.