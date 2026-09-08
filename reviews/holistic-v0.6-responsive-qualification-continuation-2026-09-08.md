# Independent Responsive Qualification Continuation — Holistic v0.6

Date: 2026-09-08
Role: Fresh responsive/runtime qualification reviewer; producer PASS claims not inherited
Disposition: **PASS**
Promotion eligibility after combined independent evidence: **YES**
Findings: **0 BLOCKER / 0 MAJOR / 0 MINOR / 0 external qualification blockers**

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Repository path: `prototypes/holistic/v0.6/DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Exact size: `295505 bytes`
- SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- PR: `#6`
- Canonical predecessor: holistic v0.5 at merge `2c8df9d9ab5b523b812a37e5739c1f598f68af97`

The Drive object was freshly downloaded in this review context. The raw file measured exactly `295505` bytes and independently hashed to the SHA-256 above. No candidate bytes were modified during qualification.

## Relationship to prior independent review

The existing receipt `reviews/holistic-v0.6-responsive-corrected-independent-review-2026-09-08.md` independently found **0 confirmed product blockers / 0 major / 0 minor** and exercised the candidate successfully at the browser viewport available to that reviewer. Its sole remaining blocker was inability to execute the mandatory exact viewport matrix at 320 / 390 / 768 / 1440 px.

This continuation closes only that external runtime dependency and re-exercises the corrected killifish provenance path while doing so. Earlier CHANGES_REQUIRED receipts remain preserved as immutable historical evidence for superseded candidates.

## Runtime method

A fresh executable Chromium runtime was available at `/usr/bin/chromium`, controlled through Python Playwright. Because the environment policy blocks direct local-file and loopback navigation, the exact raw Drive-downloaded HTML bytes were supplied unchanged to Chromium with `page.set_content`; no HTML, CSS, JavaScript, or data transformation was applied.

Each browser context used an exact viewport width and a 1000px viewport height. Browser runtime errors and console errors were captured independently.

## Exact responsive matrix

The following exact widths were exercised:

| Width | `innerWidth` | document client width | document scroll width | body scroll width | Horizontal overflow |
| ---: | ---: | ---: | ---: | ---: | ---: |
| 320 | 320 | 320 | 320 | 320 | 0 |
| 390 | 390 | 390 | 390 | 390 | 0 |
| 768 | 768 | 768 | 768 | 768 | 0 |
| 1440 | 1440 | 1440 | 1440 | 1440 | 0 |

The route matrix covered 78 surfaces at every width, including:

- splash;
- core top-level navigation surfaces;
- all seven seeded Program detail surfaces;
- all seeded cohort, breeding-stock, and tank detail surfaces;
- lineage, analytics, and media surfaces for all seven Programs;
- the Nothobranchius annual / soil and mop / plant method surfaces;
- mop / plant collection dialog;
- wetting attempt 1 dialog;
- re-drying dialog;
- wetting attempt 2 dialog;
- observed-hatch dialog.

Results across all four widths:

- Route render failures: `0`.
- Document-level horizontal-overflow failures: `0`.
- Dialog horizontal-overflow failures: `0`.
- App/runtime page errors: `0`.
- Console errors: `0`.

### Narrow splash correction

The specific responsive correction is effective:

- 320px viewport: splash card `left=22`, `right=298`, `width=276`; overflow `0`.
- 390px viewport: splash card `left=22`, `right=368`, `width=346`; overflow `0`.
- 768px viewport: splash card `width=410`; overflow `0`.
- 1440px viewport: splash card `width=410`; overflow `0`.

The three splash relationship nodes flex within the card at narrow widths and remain visually contained.

## Killifish provenance regression at every required width

Fifteen functional assertions were executed at each of 320 / 390 / 768 / 1440 px. All passed.

Confirmed behavior:

1. The annual surface presents one core with two contextual killifish methods.
2. Switching to mop / plant changes guidance only and creates no spawn or cohort record.
3. The mop / plant surface renders and its collection form fits the viewport.
4. Recording a mop / plant batch creates one reproductive output and no inferred hatch or cohort.
5. Switching back restores the annual egg-medium wetting history.
6. Wetting attempt 1 creates a structured attempt record.
7. Wetting attempt 1 does not infer hatch or create a cohort.
8. Re-drying updates attempt 1 and retains separate event provenance.
9. Re-drying does not infer hatch or create a cohort.
10. Wetting attempt 2 receives a distinct attempt ID and number.
11. Wetting attempt 2 still does not infer hatch.
12. An observed hatch is created only by the explicit hatch action.
13. The hatch links to the selected second wetting attempt.
14. The selected attempt retains the hatch ID.
15. The new cohort retains both the explicit hatch provenance and the selected wetting-attempt provenance.

## Combined independent disposition

The prior responsive-corrected independent review established the product/domain/runtime evidence available at 1363px and identified only the responsive-capable-browser dependency. This fresh continuation has now executed the exact missing matrix and found no responsive or provenance defect.

`HOLISTIC_V0_6_RESPONSIVE_MATRIX = PASS`

`HOLISTIC_V0_6_RESPONSIVE_CORRECTED_INDEPENDENT_REVIEW = PASS`

`HOLISTIC_V0_6_CORRECTION_REQUIRED = NO`

`HOLISTIC_V0_6_READY_FOR_FOUNDER_PROMOTION = YES`

`HOLISTIC_V0_6_CANONICAL = NO`

PR #6 remains non-canonical until founder promotion of the exact SHA-256-bound candidate and merge to `main` under `PROTOTYPE-ITERATION-WORKFLOW.md`.