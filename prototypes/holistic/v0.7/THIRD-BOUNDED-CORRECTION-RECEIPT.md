# Producer Third Bounded-Correction Receipt — Holistic v0.7

Date: 2026-09-08
Status: **THIRD_BOUNDED_CORRECTION_PRODUCED / NON-CANONICAL / MERGE_HOLD**
PR: `#7`
Branch: `prototype/v0.7-selection-line-development`

## Founder-authorized correction boundary

This correction responds only to independent finding `V07-SECOND-IR-001`: Pair Builder could re-admit an explicitly excluded animal as its rendered relationship subject through an unchecked hard-coded Atlas fallback even after the current disposition made that animal ineligible.

The correction is intentionally bounded to Pair Builder parent resolution and current-disposition authority. No filial-generation, goal-history, phenotype/evaluation, evidence, selection-history, program-isolation, provenance, killifish lifecycle, v0.8 scheduling/capacity, v0.9 commerce, backend/API/schema/database/deployment, Android implementation, promotion, or merge scope is admitted.

## Prior independently reviewed candidate preserved

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `13LbZKVuq02tk2Vmhb4mBvWipChpv_V7r`
- Size: `332362 bytes`
- SHA-256: `f82ef39241b36c0325ff918b9e95b447a964b4426ca2fe530c70e86e3b329930`
- Independent review: `CHANGES_REQUIRED`
- Promotion blocker: `V07-SECOND-IR-001`

The prior Drive object was not overwritten or mutated.

## New immutable third bounded-correction candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`
- Exact size: `334514 bytes`
- SHA-256: `1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`

A fresh raw Drive re-download returned exactly `334514` bytes and independently hashed to the same SHA-256.

## Exact bounded correction

Pair Builder now resolves every active parent through the existing `pairBuilderEligible()` authority before it can be used for selection, relationship calculation, ancestry rendering, relationship-sheet rendering, example-pair loading, or continuation controls.

The correction specifically:

- removes the unchecked `lineagePairA='atlas'` fallback;
- makes `pairOptions()` reject an ineligible active parent;
- adds eligibility-aware parent normalization before Pair Builder rendering;
- ensures stale Stock A / Stock B values are replaced only by currently eligible records;
- prevents relationship and continuation state from rendering when two currently eligible parents are not available;
- revalidates relationship-sheet parent state before opening it;
- makes the Atlas demo-pair shortcuts unavailable whenever Atlas or the counterpart is currently ineligible;
- constrains the Stock-A change fallback to `pairBuilderEligible()` records.

Historical `ready=true` is not rewritten. Current `Non-breeding`, `Retire`, and `Sale / rehome` remain blocking dispositions. `Holdback` remains readiness-neutral.

## Canonical authority

The canonical predecessor remains holistic v0.6:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Size: `295505 bytes`
- SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical merge/base commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_PRODUCED = YES`

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_DRIVE_ROUND_TRIP = PASS`

`HOLISTIC_V0_7_CANONICAL = NO`

`HOLISTIC_V0_7_PROMOTION_ELIGIBLE = NO_PENDING_FRESH_INDEPENDENT_REVIEW`

`PR_7_MERGE = HOLD`
