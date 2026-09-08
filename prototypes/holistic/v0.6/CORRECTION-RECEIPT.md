# Producer Correction Receipt — Holistic v0.6 Candidate

Date: 2026-09-08
Role: Producer correction worker
Disposition: **CORRECTED CANDIDATE PRODUCED / NON-CANONICAL**
PR: `#6` — `prototype/v0.6-species-aware-breeder-programs`

## Original candidate preserved

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-CANDIDATE.html`
- Google Drive ID: `17tU_eBaSzO9zOr7_DMX6n63QZcdkMUu2`
- Size: `277786 bytes`
- SHA-256: `b47c5738a8215ad3fdbbf879733d4c021f76f024ed3cd2ce9fd6ff414da702cd`
- Independent receipt: `reviews/holistic-v0.6-independent-review-2026-09-08.md`

The original Drive object was not overwritten. It was freshly downloaded and still matched the original size and SHA-256. The independent review receipt remains unchanged and remains **CHANGES_REQUIRED**.

## Corrected candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24`
- Google Drive URL: `https://drive.google.com/file/d/1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24/view?usp=drivesdk`
- Size: `295329 bytes`
- SHA-256: `3f99ee9c2a763aac86c39c06042f83cdfbbce480eb7ac9dbf78bf2bd005ddfe3`

The corrected file was uploaded as a new Drive object. A fresh download of that new object measured `295329 bytes` and hashed to the exact SHA-256 above.

## Bounded corrections

1. Added a mop / plant-spawning killifish workflow alongside the existing annual / soil-spawning egg-medium workflow. Both use the existing Program, reproductive-output and cohort model; the method view is contextual guidance only.
2. Added structured annual-killifish wetting attempts. First wetting creates attempt 1, re-drying records a separate phase on that attempt, and the next wetting creates attempt 2. An observed hatch must select an attempt; hatch IDs, cohort source hatch IDs and selected wetting-attempt IDs remain distinct. Wetting timing never infers hatch or success.

## Scope boundary

No application implementation, backend, API, schema, database, deployment, production data, release state, v0.7 grading, v0.8 planning, or v0.9 commerce work was added. v0.5 remains canonical on `main`. A fresh independent review of the corrected Drive bytes is still required; this receipt makes no independent-review PASS claim.


## Follow-up bounded responsive correction

Date: 2026-09-08
Previous corrected candidate: `1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24` / `3f99ee9c2a763aac86c39c06042f83cdfbbce480eb7ac9dbf78bf2bd005ddfe3`
Latest candidate: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_` / `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
Latest size: `295505 bytes`

The latest candidate is a new Drive object. The previous corrected object and the original candidate remain untouched. The bounded change is CSS-only and addresses narrow splash-card sizing at `max-width:420px`; it does not alter the shared core, species overlays, breeding records, wetting/re-drying provenance, or scope. Static checks and a real cloud-browser functional pass at the available 1363px viewport passed. Exact responsive widths 320 / 390 / 768 / 1440 remain unrun because the available cloud browser has no viewport-setting API and the local runtime has no executable browser. The PR remains non-canonical and merge-held pending a responsive-capable browser qualification.
