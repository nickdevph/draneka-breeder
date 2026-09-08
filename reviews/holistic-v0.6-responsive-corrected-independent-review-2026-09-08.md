# Independent Review Receipt — Holistic v0.6 Responsive-Corrected Candidate

Date: 2026-09-08
Role: Fresh independent holistic product, UX, domain-model, and runtime reviewer
Reviewer context: Separate cloud-browser tabs and independent Drive re-download; producer PASS claims not inherited
Disposition: **INCOMPLETE / NOT PROMOTION-ELIGIBLE**
Findings: **0 confirmed product blockers / 0 major / 0 minor / 1 external qualification blocker**

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Repository path: `prototypes/holistic/v0.6/DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- PR head: `10a581d6108280f138cfda33b27a5a1508407d6d`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Exact size: `295505 bytes`
- SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`

A fresh raw Drive download independently matched the recorded size and SHA-256. The earlier corrected Drive object `1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24` remains unchanged. v0.5 remains canonical at merge `2c8df9d9ab5b523b812a37e5739c1f598f68af97`.

## Independent review evidence

The exact candidate was loaded from the local site-preview copy in a separate cloud-browser context at the available fixed 1363 x 936 viewport.

- Initial breeder shell rendered successfully.
- Programs navigation succeeded.
- All seven seeded program detail surfaces rendered: Betta, Medaka, Corydoras, Neocaridina, Nothobranchius rachovii, Apistogramma, and guppy.
- The Nothobranchius surface exposed both Annual / soil and Mop / plant contextual methods.
- The Mop / plant collection action opened a form containing collection date, batch name, eggs/count basis, and collection/holding notes; the form was closed without creating a new biological record.
- The annual surface retained Attempt 1, re-drying, Attempt 2, hatch-to-attempt-2 provenance, distinct hatch evidence, and explicit no-inference language.
- No app-origin console errors were observed in the isolated program checks.
- At the available viewport, document/body width was 1348px against an inner width of 1363px; no horizontal overflow was observed.

These checks are functional evidence at the available viewport, not a substitute for the required exact responsive matrix.

## External qualification blocker

The required responsive gates at exactly 320px, 390px, 768px, and 1440px could not be executed:

1. The cloud browser starts at 1363 x 936 and its documented control surface has no viewport-setting method.
2. The local environment has the Playwright package but no executable browser and no `agent-browser` CLI.
3. Attempts to use local Chrome/Firefox and direct loopback/raw artifact URLs were unsuccessful; the site-preview cloud route was the successful runtime path, but it remains fixed-width.

Consequently, the reviewer cannot honestly mark the responsive matrix PASS. This is an execution-environment blocker, not a confirmed product defect.

## Disposition

`HOLISTIC_V0_6_RESPONSIVE_CORRECTED_INDEPENDENT_REVIEW = INCOMPLETE`

`HOLISTIC_V0_6_PROMOTION_ELIGIBLE = NO`

`HOLISTIC_V0_6_CANONICAL = NO`

`PR_6_MERGE = HOLD`

A responsive-capable browser runtime is the only remaining qualification dependency identified in this review. No promotion or merge is authorized by this receipt.
