# Producer Validation — Holistic v0.7 Second Bounded-Correction Candidate

Date: 2026-09-08
Disposition: **TARGETED_PRODUCER_PASS / READY_FOR_FRESH_INDEPENDENT_REVIEW / NON-CANONICAL**
PR: `#7`

## Exact candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `13LbZKVuq02tk2Vmhb4mBvWipChpv_V7r`
- Exact size: `332362 bytes`
- SHA-256: `f82ef39241b36c0325ff918b9e95b447a964b4426ca2fe530c70e86e3b329930`

Fresh Drive re-download: **PASS**, exact size/hash match.

## JavaScript syntax

The single inline script was extracted from the exact candidate and passed `node --check`.

`JAVASCRIPT_SYNTAX = PASS`

## Correction-specific functional harness

Exact corrected function bodies were extracted from the candidate and exercised against controlled records.

Passed assertions:

1. ready + `Holdback` remains Pair Builder eligible when all prior eligibility conditions are satisfied;
2. ready + `Non-breeding` is Pair Builder ineligible;
3. ready + `Retire` is Pair Builder ineligible;
4. ready + `Sale / rehome` is Pair Builder ineligible;
5. `Holdback` with `ready=false` remains Pair Builder ineligible;
6. recorded `F1 × F2` returns `Generation not established · recorded parents F1 × F2` rather than `F3`;
7. same-line recorded `F1 × F1` retains the narrower supported automatic `F2` path.

The exact named-offspring save path continues to assign `generation:generationForCohortSelection(c)`, so the corrected conservative helper is shared by cohort selection and promoted individual creation.

`DISPOSITION_SEMANTICS_TARGETED = PASS`

`MIXED_FILIAL_PRECISION_TARGETED = PASS`

`NAMED_OFFSPRING_GENERATION_PATH_STATIC_BINDING = PASS`

## Goal-history checks

Static/runtime invariants on the exact candidate confirm:

- missing fixture goal-history records are seeded for Program `p2`, `p6` and `p7`;
- a runtime migration seeds a current Program goal when its ledger is absent;
- new Program creation appends the initial non-empty goal to `goalHistory`;
- `saveGoal` defensively backfills a missing prior goal before appending the changed goal;
- evaluation and selection goal snapshots are not rewritten.

`INITIAL_GOAL_HISTORY = PASS`

## Browser/runtime qualification note

The available local Chromium binary in this execution environment did not complete even a minimal `--headless --dump-dom` invocation, and Playwright is not installed here. Therefore this producer did **not** claim a fresh exact-browser responsive/runtime matrix for the new bytes.

The prior independent review established the responsive matrix on the predecessor candidate at `320 / 390 / 768 / 1440` with zero horizontal/dialog overflow and zero console/page errors, but that result is not inherited as proof for this new SHA-bound artifact.

Fresh independent review must therefore rerun the required browser/runtime and responsive matrix on the exact new bytes.

`SECOND_CORRECTION_BROWSER_MATRIX = NOT_RUN_IN_PRODUCER_ENVIRONMENT`

## Scope

No v0.8 dynamic operational scheduling/capacity expansion, v0.9 commerce handoff, backend/API/schema/database/deployment, production, Android, web implementation authority, promotion, or merge is admitted.

`HOLISTIC_V0_7_SECOND_CORRECTION_DRIVE_ROUND_TRIP = PASS`

`HOLISTIC_V0_7_SECOND_CORRECTION_TARGETED_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_7_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_7_CANONICAL = NO`

`PR_7_MERGE = HOLD`
