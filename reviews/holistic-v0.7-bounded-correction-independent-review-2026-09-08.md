# Independent review — holistic v0.7 bounded correction

Date: 2026-09-08

## Primary disposition

`CHANGES_REQUIRED`

The exact corrected v0.7 candidate is not promotion-eligible. Two independently reproduced authority/decision defects are promotion-blocking MAJOR findings. One additional MINOR goal-history completeness defect was found.

## Exact artifact binding

Candidate reviewed:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1WCEPsAM35WsGo-y5IdJ0w5pSNBXHV_Hg`
- Independently downloaded bytes: `330298`
- Independently calculated SHA-256: `6c47d96330fca26dd7d2c2d9d1f7dcc2ba0753b283d23f19415793cca9bc0186`

Canonical predecessor independently re-downloaded for comparison:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Independently downloaded bytes: `295505`
- Independently calculated SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical base / merge commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

PR binding before this receipt-only commit:

- PR: `nickdevph/draneka-breeder#7`
- Branch: `prototype/v0.7-selection-line-development`
- Exact PR head reviewed: `a3615935fad4caf34a92df61218efc219d93f439`
- PR state when reviewed: open, unmerged

Producer claims and prior receipts were not used as correctness evidence.

## Browser/runtime method

- Runtime: Chromium `144.0.7559.96`, headless, through Playwright.
- Exact candidate bytes were independently hashed first, then the UTF-8 HTML was decoded and loaded with `page.set_content()` into Chromium.
- Direct `file://` / localhost navigation was blocked by the execution environment. The candidate is self-contained: no external script/style resources, `fetch`, or XHR dependency was found, so its HTML/CSS/JavaScript runtime was still exercised in a real Chromium document.

## Findings

### V07-IR-001 — MAJOR — Non-breeding / Retire decisions remain Pair Builder candidates

A real Program-scoped selection session was recorded through the candidate UI. Existing breeding-ready Betta stock was assigned the following breeder decisions with reasons:

- Ember: `Non-breeding`
- Lyra: `Retire`
- Atlas: `Sale / rehome`
- Iris: `Holdback`

The selection records were saved correctly, and the dispositions remained breeder decisions rather than inferred biological defects. However, `pairBuilderEligible()` does not consider `selectionDisposition`. Ember and Lyra remained `ready=true`, remained `pairBuilderEligible=true`, and both remained visible as selectable Pair Builder breeding stock after the `Non-breeding` and `Retire` decisions.

This materially weakens the governed product objective: a breeder's explicit negative selection decision is recorded but not honored by the pairing workflow. Pair Builder therefore can invite a pairing that directly contradicts current breeder intent without a disposition warning or gate.

Bounded correction required: Pair Builder eligibility/gating must consume the current recorded selection disposition. At minimum, `Non-breeding` and `Retire` must not silently remain ordinary eligible breeding-stock choices. `Holdback` must still not create readiness by itself. `Sale / rehome` must remain a disposition only and must not create commerce behavior.

### V07-IR-002 — MAJOR — Mixed filial generations are automatically promoted to unsupported precision

The candidate's generation derivation is:

`generationFromParents(ids) -> F(max(parent F-number) + 1)`

An independent controlled-pair stress fixture used exact recorded parents:

- Ember: `F1`
- Atlas: `F2`

At runtime:

- `generationFromParents(['ember','atlas'])` returned `F3`.
- `generationForCohortSelection()` returned `F3` for their controlled-pair offspring cohort.
- Selecting an offspring through the normal `Select individual` flow created a named animal with exact parent IDs `['ember','atlas']` and automatically assigned generation `F3`.

Exact parentage evidence supports who the parents are; it does not, by itself, justify labelling every mixed F1 × F2 cross as F3. The mandatory v0.7 authority invariant explicitly rejects generation labels that imply unsupported genetic precision.

Bounded correction required: do not infer a precise filial generation from `max(Fn)+1`. Preserve `Generation not established` unless the generation label is supported by an explicit, valid line-generation context/rule. A correction may retain legitimately supported generation labels, but mixed-generation/outcross cases must not be coerced into a precise F-number.

### V07-IR-003 — MINOR — Initial goal version is absent from the goal-history ledger for unseeded/new Programs

Existing seeded p1 goal history behaved correctly: changing the current goal did not rewrite prior evaluation or selection `goalSnapshot` values, and a new goal revision was appended.

A stress test on p6 exposed a completeness gap. p6 begins with a meaningful current goal but has no seeded `goalHistory` record. After changing that goal, `saveGoal()` appended only the new goal. The prior goal was retained in the timeline event text, but it did not appear as a goal-history revision. The same structural behavior applies to newly created Programs because Program creation stores `goal` but does not seed `state.goalHistory`.

Historical evaluation/selection snapshots remain immutable, so this does not retroactively rewrite decision meaning. It does make the dedicated goal-history ledger incomplete.

Bounded correction recommended: seed the initial goal revision on Program creation, or on first change preserve the prior goal as a history revision before appending the new one.

## Independently verified PASS areas

- Exact candidate binding by Drive ID, filename, bytes, and SHA-256.
- Corrected Program isolation: a same-species + same-visible-line animal in another Program, with no Program membership/source-cohort provenance, was rejected from p1 selection candidates.
- Time-stamped phenotype evaluation records with subject identity, assessment, notes, observed traits, sample information where applicable, and goal snapshot.
- Evidence attachment to the intended evaluation; prior evidence remained unchanged; missing evidence rendered explicitly as missing; synthetic demo evidence is labelled as synthetic/prototype evidence and not genotype proof.
- Selection session creation and reason retention for Holdback, Non-breeding, Sale / rehome, Retire, and Undecided semantics.
- Holdback does not make a newly selected offspring breeding-ready.
- Betta exact controlled ancestry remained intact through evaluation, offspring selection, and Holdback.
- Fancy guppy known-mother / unknown-sire provenance stayed uncertain; no father was invented.
- Medaka partial/repeated hatch outputs retained distinct hatch provenance; comparison showed sample coverage and explicit missing evidence.
- Neocaridina population/colony-derived selected stock retained no fabricated exact parents and remained Pair-Builder-ineligible even after readiness was explicitly set where group provenance lacked exact parents.
- Pair Builder relatedness warnings for known relationships and conservative `No known common ancestor` copy when ancestry is incomplete; no opaque `best pair` recommendation was present.
- Generation/cohort comparison preserved uneven coverage, sample sizes, and `Not enough evidence`; missing evidence did not become zero/negative/success.
- Complete v0.6 killifish regression: mop/plant collection did not infer hatch; wetting attempt 1 did not infer hatch; re-drying did not infer hatch; wetting attempt 2 received a distinct attempt ID; explicit hatch linked only to attempt 2; resulting cohort retained source output, source hatch, and wetting-attempt provenance.
- Core count revision vs mortality semantics, move identity/provenance preservation, split conservation/provenance, lineage-safe merge, observed mortality, life-stage update, and quick feeding were exercised independently and passed.
- No v0.8 dynamic operational scheduling/capacity/allocation system was admitted.
- No v0.9 marketplace/listing/order/channel/commerce handoff was admitted. `Sale / rehome` remained a breeder disposition record.
- Selection remains contextual within the existing breeder workflow rather than becoming a new top-level navigation destination.

## Exact responsive/runtime matrix

Twenty-seven major routed/dialog surfaces were exercised at each exact width, including splash, Today, Programs, Program detail, stock detail, cohort/grow-out, evaluations, evidence-related UI, selection workspace/session, comparison/analytics, lineage/Pair Builder, Betta/Guppy/Medaka/Neocaridina contexts, and required killifish dialogs.

| Width | window.innerWidth | document client width | document scroll width | body scroll width | Horizontal overflow | Dialog overflow | Page errors | Console errors |
|---:|---:|---:|---:|---:|---|---|---:|---:|
| 320 | 320 | 320 | 320 | 320 | 0 | 0 | 0 | 0 |
| 390 | 390 | 390 | 390 | 390 | 0 | 0 | 0 | 0 |
| 768 | 768 | 768 | 768 | 768 | 0 | 0 | 0 | 0 |
| 1440 | 1440 | 1440 | 1440 | 1440 | 0 | 0 | 0 | 0 |

Console warnings were also zero at all four widths.

`HOLISTIC_V0_7_RESPONSIVE_MATRIX = PASS`

## Static-only / unexecuted boundaries

No conclusion about the two MAJOR findings relies only on static inspection; both were reproduced in Chromium runtime. Program isolation, goal mutation, evaluation/evidence, selection, species stress paths, comparison, Pair Builder relationship checks, killifish regression, and major core inventory/provenance operations were also executed in runtime.

Static inspection supplemented runtime for anti-overwhelm/navigation structure, absence of prohibited v0.8/v0.9 systems, and absence of external runtime dependencies. Backend, API, schema, database, deployment, production, Android, signing, and release behavior were not executed because they are explicitly outside this prototype review scope. Direct URL navigation was environment-blocked as noted above; the self-contained exact candidate was executed via `page.set_content()` instead.

## Required disposition block

```text
HOLISTIC_V0_7_EXACT_BINDING = PASS
HOLISTIC_V0_7_PRODUCT_OBJECTIVE = FAIL
HOLISTIC_V0_7_GOAL_HISTORY = FAIL
HOLISTIC_V0_7_PHENOTYPE_EVALUATION = PASS
HOLISTIC_V0_7_EVIDENCE_ATTACHMENT = PASS
HOLISTIC_V0_7_SELECTION_SESSION = PASS
HOLISTIC_V0_7_PROGRAM_ISOLATION = PASS
HOLISTIC_V0_7_DISPOSITION_SEMANTICS = FAIL
HOLISTIC_V0_7_GENERATION_COMPARISON = PASS
HOLISTIC_V0_7_PHENOTYPE_GENOTYPE_BOUNDARY = FAIL
HOLISTIC_V0_7_PAIR_BUILDER_AUTHORITY = FAIL
HOLISTIC_V0_7_V0_6_REGRESSION = PASS
HOLISTIC_V0_7_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_7_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_7_INDEPENDENT_REVIEW = CHANGES_REQUIRED
HOLISTIC_V0_7_PROMOTION_ELIGIBLE = NO
HOLISTIC_V0_7_CANONICAL = NO
PR_7_MERGE = HOLD
```

Findings: `0 BLOCKER`, `2 MAJOR`, `1 MINOR`, `0 POLISH`.

v0.6 remains canonical. PR #7 must remain unmerged. Any correction must stay inside the existing v0.7 branch/PR and produce a new immutable candidate with a new filename, Drive object, byte count, and SHA-256 while preserving both prior v0.7 candidate objects as historical evidence.