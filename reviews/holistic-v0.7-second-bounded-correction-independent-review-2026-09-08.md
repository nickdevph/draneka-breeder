# Independent review — holistic v0.7 second bounded correction

Date: 2026-09-08

## Primary disposition

`CHANGES_REQUIRED`

The exact v0.7 second bounded-correction candidate is not promotion-eligible. One independently reproduced Pair Builder authority defect remains promotion-blocking. The other two prior promotion blockers are independently closed, and no collateral regression was found in the required v0.7/v0.6 regression boundary.

Producer claims, prior review PASS/FAIL assertions, PR descriptions, and durable receipts were not used as correctness evidence for this disposition.

## Exact artifact binding

Candidate reviewed:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `13LbZKVuq02tk2Vmhb4mBvWipChpv_V7r`
- Independently downloaded bytes: `332362`
- Independently calculated SHA-256: `f82ef39241b36c0325ff918b9e95b447a964b4426ca2fe530c70e86e3b329930`

Canonical predecessor independently re-downloaded:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Independently downloaded bytes: `295505`
- Independently calculated SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical merge/base commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

PR binding immediately before this receipt-only write:

- PR: `nickdevph/draneka-breeder#7`
- Branch: `prototype/v0.7-selection-line-development`
- Exact candidate/code head reviewed: `612c669be60a2e2bcd04cfdf789705637a2d3da5`
- PR state: `open`
- Merged: `false`
- Base: `main`
- Base SHA: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

This file is a receipt-only mutation after qualification. Any later PR head containing only this review receipt is not the candidate/code head that was exercised.

## Browser/runtime method

- Runtime: Chromium `144.0.7559.96`, headless, controlled with Playwright.
- The candidate was independently SHA-bound first. The exact UTF-8 HTML bytes were then decoded and loaded into a real Chromium document with `page.set_content()`.
- Direct `file://` and loopback HTTP navigation were blocked by the execution environment. The candidate is self-contained: no external script/style resources, `fetch`, XHR, WebSocket, or beacon dependency was found. Runtime qualification therefore exercised the exact candidate HTML/CSS/JavaScript in Chromium without reconstructing or substituting the artifact.
- Candidate state was reset from the exact artifact for independent stress paths unless the path intentionally required sequential mutations.

## Finding

### V07-SECOND-IR-001 — BLOCKER — negative current disposition can remain the rendered active Pair Builder parent

Affected gate: **G1 — disposition semantics and Pair Builder authority**.

#### Exact reproduction

Using a fresh exact-candidate Chromium session:

1. Open the demo fishroom.
2. Open `Copper halfmoon · next generation`.
3. Open `Selection & line development`.
4. Start a selection session.
5. For already breeding-ready `Atlas · retained F2`, record `Non-breeding` and a breeder-entered reason.
6. Save the selection session.
7. Verify the saved stock still has historical `ready=true`, while `selectionDisposition=Non-breeding`.
8. Verify the ordinary breeding-arrangement stock chooser disables Atlas and labels it `Current disposition: Non-breeding`.
9. Open Pair Builder.

The same path was repeated independently with `Retire` and `Sale / rehome`.

#### Expected behavior

A stock record with current `Non-breeding`, `Retire`, or `Sale / rehome` disposition must not be selectable or rendered as an active Pair Builder parent. Historical readiness may remain recorded, but it cannot bypass current disposition authority.

#### Observed behavior

For all three negative dispositions:

- `ready` remained `true`, preserving historical readiness as a distinct record.
- `breedingStockSelectable(Atlas)` returned `false`.
- `pairBuilderEligible(Atlas)` returned `false`.
- The ordinary breeding-arrangement chooser correctly disabled Atlas.
- Pair Builder's Stock A option list correctly excluded Atlas.
- Nevertheless, the Pair Builder result still rendered `Atlas · retained F2 × Iris · retained F2`, the full-sibling warning, Atlas ancestry/coverage, and controls that referenced Atlas. The visible Stock A select had fallen to another available option while the relationship/result panel remained based on the forbidden Atlas record.

Static inspection explains the runtime contradiction: `pairBuilderScreen()` handles an ineligible current A by assigning the hard-coded fallback `lineagePairA='atlas'` and then immediately reading Atlas again without re-validating that fallback. When Atlas itself carries the current negative disposition, the fallback remains ineligible but is still used to calculate and render the relationship state.

#### Why this matters

This is an authority bypass in the governed downstream pairing workflow. The correction successfully updated the eligibility predicate and ordinary breeding-arrangement chooser, but Pair Builder can still present a breeder-explicitly excluded animal as the active pairing subject. The UI therefore contradicts the current authoritative disposition and can invite the breeder to continue a pairing involving stock that the same system says is ineligible.

Classification: **within the bounded v0.7 correction**, not a collateral regression.

No candidate fix was made during this review.

## G1 evidence beyond the blocker

The rest of the required disposition semantics behaved correctly:

- A newly selected Betta offspring with `ready=false` was assigned `Holdback` through the normal selection-session UI. It remained `ready=false`, `breedingStockSelectable=false`, and `pairBuilderEligible=false`; Holdback did not manufacture readiness.
- Ready Atlas assigned `Holdback` remained `ready=true`, `breedingStockSelectable=true`, and `pairBuilderEligible=true`; Holdback was not treated as a negative breeding disposition.
- Ready Atlas assigned each of `Non-breeding`, `Retire`, and `Sale / rehome` remained historically `ready=true` while current downstream eligibility predicates became false. Readiness and disposition therefore remained distinct evidence claims.
- The ordinary breeding-arrangement stock chooser disabled Atlas for each negative current disposition, so the normal pairing-entry path did not re-admit it.
- Selection-session reasons were retained with an immutable goal snapshot.
- `Sale / rehome` remained a disposition only: recording it did not create an exit, listing, channel, marketplace, CRM, payment, or other commerce state.

## G2 — unsupported filial-generation precision

`PASS`

A complete fresh controlled-pair path was executed through the ordinary UI:

1. Create a new Betta Program with the same `Copper halfmoon` line.
2. Select exact parents `Ember` (`F1`) and `Iris · retained F2` (`F2`).
3. Record the controlled pairing.
4. Record `Mixed filial spawn 01` with 10 exact eggs.
5. Record an explicit hatch of 5 exact fry into `Mixed filial fry`.
6. Open the offspring group.
7. Select/promote one offspring into a named individual `Mixed filial offspring`.

Observed result:

- Cohort generation evaluation: `Generation not established · recorded parents F1 × F2`.
- Named offspring generation: `Generation not established · recorded parents F1 × F2`.
- No `F3` was assigned.
- Named offspring preserved exact parent IDs `ember` + `iris`.
- Source output and hatch IDs remained attached.
- Parent identity and filial-generation certainty remained separate evidence claims.

Supported same-filial handling was also retained. Selecting from the existing Betta controlled-pair cohort sourced from `Ember F1 × Lyra F1` produced a named candidate with exact parents Ember/Lyra and generation `F2`.

Population/group-derived generation remained conservative. A Neocaridina individual selected through the normal cohort path preserved source group `blue-colony`, no exact parent IDs, and generation `Generation not established · source population/group recorded`; it remained Pair-Builder-ineligible.

## G3 — initial goal-history ledger completeness

`PASS`

Before any goal mutation, every seeded Program carrying a non-empty current goal had at least one dedicated `goalHistory` record. The annual killifish Program specifically had:

- Program: `p6` / `Rachovii · annual egg-medium line`
- Initial history ID: `gh-p6-0`
- Date: `2026-08-10`
- Goal: `Keep egg-medium batches and wetting attempts distinct without turning killifish into a separate app.`

Existing Program edit test on `p1`:

- Two pre-existing history records were captured first.
- The current goal was edited through the ordinary UI.
- The prior records remained byte-for-byte/field-for-field intact.
- A new goal record was appended.
- Existing phenotype-evaluation `goalSnapshot` values remained the original prior goal.
- Existing selection-session `goalSnapshot` remained the original prior goal.

New Program test:

- The `Mixed filial stress` Program was created through the three-step ordinary Program UI with initial goal `Test conservative filial handling.`
- Immediately after creation and before any edit, its `goalHistory` contained that initial goal.
- Editing the goal to `Second mixed filial review goal.` appended a second history record while preserving the first unchanged.

## Full v0.7 regression boundary

All independently exercised areas below passed except the G1 Pair Builder blocker already reported:

- **Program isolation:** the `Mixed filial offspring` has the same species and same breeder-entered `Copper halfmoon` line as p1 but belongs to an unrelated Program with no p1 membership/source-cohort provenance. It did not appear in p1 selection candidates or the p1 selection-session dialog.
- **Phenotype/genotype boundary:** a new Atlas phenotype evaluation recorded visible phenotype, breeder assessment, notes, goal snapshot, and evidence without adding any genotype field. Stock detail continues to state genotype is not established from appearance.
- **Evidence:** an actual PNG was attached through the phenotype-evaluation UI, converted to local evaluation evidence and linked to the correct evaluation. Existing missing evidence remained visibly `No photo/evidence attachment recorded for this evaluation.` and comparison retained `Not enough evidence` rather than fabricating a score.
- **Selection:** decisions retained breeder-entered reasons and immutable goal snapshots; later goal edits did not rewrite earlier decision meaning.
- **Betta:** Atlas and Iris retained exact recorded parents Ember + Lyra. Pair Builder still detected and rendered their full-sibling relationship from recorded ancestry. No opaque `best pair` authority was introduced; breeder-control copy remained explicit.
- **Fancy guppy:** `Red tuxedo guppy broods` retained one recorded mother (`Ruby 01`) and `Mother recorded; sire unknown`; no sire was invented.
- **Medaka:** `m01` and `m02` remained separate source outputs; `m02` retained two distinct hatch IDs/cohorts; comparison retained `Not enough evidence` and no exact parent fabrication.
- **Neocaridina:** colony/population provenance stayed conservative; selected individual stock retained source group provenance with no exact parents and remained Pair-Builder-ineligible.
- **Count/provenance operations:** quick feeding, unexplained count revision, mortality, life-stage update, move, split, and merge were executed through rendered forms. The count revision event explicitly stated the `-1` difference was an unexplained revision, not mortality; a separate 2-loss mortality event changed 75→73. Move retained cohort identity/source; split conserved 73 as 30+43 with source output `b04` and hatch `legacy-hatch-b04`; merge restored 73 with those same source IDs and both child cohort IDs in `mergedFrom`.

## Canonical v0.6 annual-killifish regression

`PASS`

The complete lifecycle was executed in real Chromium at **each required width** (`320`, `390`, `768`, `1440`), starting from canonical-seeded annual batch `k01` (`Egg medium · 30 Aug`):

1. Wetting attempt 1 recorded with observed development.
2. Immediately after wetting 1: no hatch record and no offspring cohort existed.
3. Re-drying recorded on attempt 1; attempt 1 remained preserved with its own ID and no hatch.
4. Wetting attempt 2 recorded as a distinct attempt with its own ID.
5. Before explicit hatch: still no hatch record/cohort.
6. Explicit observed hatch of 7 fry recorded and linked to attempt 2.
7. Resulting cohort retained source output `k01`, the explicit hatch ID, `sourceWettingAttemptIds=[attempt 2]`, and direct `wettingAttemptId=attempt 2`.
8. Attempt 1 remained separately re-dried and had no hatch link.

A mop/plant path was also executed independently through the UI. `Review mop batch` recorded 11 exact eggs with `workflow=mop-plant`, no hatch records, and no offspring cohort. Collection therefore did not infer hatch or success.

## Real-browser responsive/runtime qualification

`PASS`

Required viewport widths were actually achieved. At every width, `window.innerWidth`, document client width, document scroll width, and body scroll width were recorded. No document/body horizontal overflow, dialog horizontal overflow, page errors, console errors, or console warnings were observed in the primary matrix. A post-mutation merge dialog and the cohort-selection dialog were also measured at all four widths with no horizontal overflow.

| Width | `window.innerWidth` | doc client | doc scroll | body scroll | doc/body overflow | dialog overflow | page errors | console errors |
|---:|---:|---:|---:|---:|---|---|---:|---:|
| 320 | 320 | 320 | 320 | 320 | none | none | 0 | 0 |
| 390 | 390 | 390 | 390 | 390 | none | none | 0 | 0 |
| 768 | 768 | 768 | 768 | 768 | none | none | 0 | 0 |
| 1440 | 1440 | 1440 | 1440 | 1440 | none | none | 0 | 0 |

Major routed/dialog surfaces exercised at every width included:

- home;
- Programs navigation;
- Program detail;
- Program creation dialog;
- Program goal edit;
- selection workspace;
- selection-session dialog;
- phenotype-evaluation/evidence form;
- cohort detail;
- stock detail;
- Pair Builder;
- lineage;
- goal-history rendering within selection workspace;
- count revision;
- mortality;
- move;
- split;
- life-stage update;
- quick feeding;
- annual-killifish program;
- killifish wetting;
- killifish re-dry/hatch precondition surfaces;
- mop/plant collection.

Additional exact-width qualification covered the ordinary cohort-selection dialog at all four widths. After creating real split children, the actual merge dialog was also opened and measured at 320/390/768/1440. The full actual annual wetting→re-dry→second-wetting→explicit-hatch sequence was itself repeated at every required width with no runtime errors or horizontal overflow.

## Scope discipline

`PASS`

Static and runtime review found no admitted v0.8 scheduling/capacity system, no v0.9 marketplace/listing/channel allocation/sales CRM/commerce handoff, and no backend/API/schema/database/deployment/production/Android/release mutation. The only `v0.8`/`v0.9` references are explicit non-admission copy. No runtime network API (`fetch`, XHR, WebSocket, beacon) is present.

`Sale / rehome` remained a v0.7 disposition label only.

## Disposition block

```text
HOLISTIC_V0_7_EXACT_BINDING = PASS
HOLISTIC_V0_7_PRODUCT_OBJECTIVE = FAIL
HOLISTIC_V0_7_GOAL_HISTORY = PASS
HOLISTIC_V0_7_PHENOTYPE_EVALUATION = PASS
HOLISTIC_V0_7_EVIDENCE_ATTACHMENT = PASS
HOLISTIC_V0_7_SELECTION_SESSION = PASS
HOLISTIC_V0_7_PROGRAM_ISOLATION = PASS
HOLISTIC_V0_7_DISPOSITION_SEMANTICS = FAIL
HOLISTIC_V0_7_GENERATION_PRECISION = PASS
HOLISTIC_V0_7_PHENOTYPE_GENOTYPE_BOUNDARY = PASS
HOLISTIC_V0_7_PAIR_BUILDER_AUTHORITY = FAIL
HOLISTIC_V0_7_V0_7_REGRESSION = PASS
HOLISTIC_V0_7_V0_6_REGRESSION = PASS
HOLISTIC_V0_7_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_7_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_7_INDEPENDENT_REVIEW = CHANGES_REQUIRED
HOLISTIC_V0_7_PROMOTION_ELIGIBLE = NO
HOLISTIC_V0_7_CANONICAL = NO
PR_7_MERGE = HOLD
```

Findings: `1 BLOCKER`, `0 MAJOR`, `0 MINOR`, `0 POLISH`.

v0.6 remains canonical. PR #7 must remain open and unmerged. Independent review stops here; no promotion or merge is authorized by this receipt.