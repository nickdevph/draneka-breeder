# Producer Validation — Holistic v0.7 Bounded-Correction Candidate

Date: 2026-09-08
Disposition: **PASS / READY_FOR_FRESH_INDEPENDENT_REVIEW / NON-CANONICAL**
PR: `#7`

## Exact candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1WCEPsAM35WsGo-y5IdJ0w5pSNBXHV_Hg`
- Exact size: `330298 bytes`
- SHA-256: `6c47d96330fca26dd7d2c2d9d1f7dcc2ba0753b283d23f19415793cca9bc0186`

Fresh Drive re-download: **PASS**, exact size/hash match.

## Correction-specific regression

A synthetic unlinked Betta individual was inserted with the exact same species and line-name string as Program `p1`. The corrected selection candidate query excluded that record unless explicit Program membership or source-cohort provenance linked it to `p1`.

`CROSS_PROGRAM_SELECTION_ISOLATION = PASS` at 320 / 390 / 768 / 1440.

## Complete runtime matrix

At each exact width `320 / 390 / 768 / 1440`:

- routed surfaces: `85`;
- route failures: `0`;
- document horizontal-overflow failures: `0`;
- dialog horizontal-overflow failures: `0`;
- page errors: `0`;
- console errors: `0`;
- functional assertions: `27 / 27 PASS`.

## Functional coverage retained

The corrected candidate independently re-ran the original producer checks for:

- breeding-goal history and immutable historical goal snapshots;
- phenotype evaluation with current goal snapshot;
- explicit photo evidence attachment;
- ancestry immutability during evaluation;
- Holdback / Non-breeding / Sale-rehome / Retire selection decisions;
- decision reasons and selection-session goal snapshot;
- disposition without commerce workflow;
- Betta full-sibling relatedness detection;
- no opaque authoritative Pair Builder choice;
- Medaka two-cohort comparison;
- explicit insufficient evidence rather than fabricated zero;
- distinct Medaka hatch provenance;
- Neocaridina population/colony provenance through holdback;
- conservative Pair Builder ineligibility with insufficient exact ancestry;
- holdback not implying breeding readiness;
- guppy sire uncertainty preservation;
- killifish method-switch no-record boundary;
- mop/plant collection distinct from hatch;
- first wetting, re-dry, second wetting and explicit hatch provenance;
- final mutated-state responsive integrity.

All passed at every required width.

## Scope

No v0.8 dynamic operational scheduling/capacity expansion, v0.9 commerce handoff, backend/API/schema/database/deployment, production, Android, or web implementation authority is admitted.

`HOLISTIC_V0_7_CORRECTED_JAVASCRIPT_SYNTAX = PASS`

`HOLISTIC_V0_7_CORRECTED_RESPONSIVE_MATRIX = PRODUCER_PASS`

`HOLISTIC_V0_7_CORRECTED_FUNCTIONAL_ASSERTIONS = 27_OF_27_PASS_AT_ALL_REQUIRED_WIDTHS`

`HOLISTIC_V0_7_CORRECTED_DRIVE_ROUND_TRIP = PASS`

`HOLISTIC_V0_7_CORRECTED_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_7_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_7_CANONICAL = NO`

Producer validation is not independent review. The corrected exact bytes remain non-canonical pending a fresh independent PASS, founder promotion, and PR merge.