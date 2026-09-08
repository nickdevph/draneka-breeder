# Producer Correction Receipt — Holistic v0.7

Date: 2026-09-08
Status: **CORRECTED CANDIDATE PRODUCED / NON-CANONICAL**
PR: `#7`

## Original candidate preserved

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-CANDIDATE.html`
- Drive ID: `1Nh9wctld-lfE5doncPbpNdteRGQVupZw`
- Size: `330316 bytes`
- SHA-256: `d25500aa46ff36eaac29fa5856552ac1caffb93f8ff0407b330a1aba3032c5c0`

The original Drive object was not overwritten.

## Corrected candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `1WCEPsAM35WsGo-y5IdJ0w5pSNBXHV_Hg`
- URL: `https://drive.google.com/file/d/1WCEPsAM35WsGo-y5IdJ0w5pSNBXHV_Hg/view`
- Size: `330298 bytes`
- SHA-256: `6c47d96330fca26dd7d2c2d9d1f7dcc2ba0753b283d23f19415793cca9bc0186`

A fresh raw Drive download matched the exact size and SHA-256 above.

## Bounded correction

A producer static audit identified an overly broad Program-membership predicate in the selection workspace: matching species plus a breeder-entered line-name string could admit an otherwise unlinked individual from another Program.

The correction removes line-name equality as a membership rule. A selection-session individual now requires explicit Program breeder-stock membership or source-cohort provenance belonging to that Program.

No biological records, ancestry rules, phenotype/genotype boundary, selection decision semantics, navigation, v0.6 provenance logic, or later-version scope were otherwise changed.

A synthetic cross-Program regression fixture using the same species and line-name string is now explicitly excluded from the Program selection candidate list.

## Qualification

The corrected bytes passed JavaScript syntax validation and the complete producer qualification at exact `320 / 390 / 768 / 1440` widths:

- 85 routed surfaces per width;
- 0 route failures;
- 0 document horizontal-overflow failures;
- 0 dialog overflow failures;
- 0 page errors;
- 0 console errors;
- 27/27 bounded functional assertions at every required width;
- cross-Program candidate isolation: PASS;
- all original v0.7 selection/evidence/uncertainty checks: PASS;
- v0.6 killifish provenance regression: PASS.

A fresh independent review of the corrected SHA-bound bytes is still required. This receipt does not claim an independent PASS.

`HOLISTIC_V0_7_LATEST_CANDIDATE = BOUNDED_CORRECTION`

`HOLISTIC_V0_7_CORRECTED_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_7_CANONICAL = NO`
