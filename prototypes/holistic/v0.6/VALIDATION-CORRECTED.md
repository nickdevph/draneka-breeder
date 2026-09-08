# Draneka Aquarium Breeder — Corrected v0.6 Producer Validation Receipt

Date: 2026-09-08
Disposition: **STATIC_AND_DRIVE_PASS / BROWSER_RUNTIME_UNAVAILABLE**
Role: producer-side correction validation only; this is **not** independent review.
PR: #6 — prototype/v0.6-species-aware-breeder-programs

## Exact corrected candidate under validation

- Artifact: DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-CORRECTED-CANDIDATE.html
- SHA-256: 3f99ee9c2a763aac86c39c06042f83cdfbbce480eb7ac9dbf78bf2bd005ddfe3
- Size: 295329 bytes
- Google Drive ID: 1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24
- Google Drive URL: https://drive.google.com/file/d/1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24/view?usp=drivesdk

The new Drive object was freshly downloaded. The downloaded bytes measured 295329 bytes and hashed to the exact SHA-256 above.

## Original binding protection

The original candidate was separately re-downloaded and verified unchanged:

- Original Drive ID: 17tU_eBaSzO9zOr7_DMX6n63QZcdkMUu2
- Original size: 277786 bytes
- Original SHA-256: b47c5738a8215ad3fdbbf879733d4c021f76f024ed3cd2ce9fd6ff414da702cd

The corrected HTML contains the original candidate content followed by one producer correction block before the closing script tag. No original Drive bytes were overwritten. The preserved independent receipt remains CHANGES_REQUIRED; no independent-review PASS is claimed.

## Syntax and bounded-scope validation

- Extracted JavaScript compiled successfully with Node vm.Script: PASS.
- Corrected local candidate and fresh Drive download matched byte-for-byte: PASS.
- Six existing species presets remain present: Betta splendens, Poecilia reticulata, Oryzias latipes, Nothobranchius rachovii, Neocaridina davidi, and Apistogramma cacatuoides: STATIC PASS.
- Existing core navigation remains Today / Programs / Log / Grow-out / More: STATIC PASS.
- No fetch, XHR, WebSocket, backend, schema, database, deployment or production mutation was added in the correction block: PASS.

## Killifish correction validation

### Mop / plant variant

The corrected candidate exposes a contextual Mop / plant variant alongside Annual / soil within the Nothobranchius Program. The mop path includes explicit mop / plant collection, holding/incubation and observed-hatch vocabulary, and its save path creates a normal collection/reproductive-output record in the existing shared core. Method switching creates no biological record, parentage, hatch or success fact: STATIC PASS.

### Annual wetting attempts

The corrected path stores wettingAttempts as structured records with:

- unique attempt ID and number;
- wetting date and observed state;
- re-drying date and observed state on the same attempt;
- separate wetting and re-drying event IDs;
- hatch IDs attached to the selected attempt.

The guarded sequence is:

1. first wetting creates attempt 1;
2. re-drying updates attempt 1 and retains its provenance;
3. second wetting creates attempt 2;
4. each observed hatch selects an attempt and receives a distinct hatch ID;
5. each resulting cohort retains its selected hatch and wetting-attempt provenance.

Wetting or timing never creates a hatch or success fact: STATIC PATH PASS. Runtime clicks could not be executed because no browser executable was available.

## Six species and v0.5 regression checks

- Six required species overlay definitions and the shared Program / reproductive-output / cohort model remain present: STATIC PASS.
- Existing v0.5 normalization, hatch, cohort, split, merge, move, stage, loss, selection and provenance code remains in the preserved pre-correction HTML region: STATIC PRESERVATION PASS.
- Full runtime regression clicks for v0.5 paths were not executable in this environment: NOT RUN.

## Browser/runtime and responsive validation

A browser run was attempted. The agent-browser CLI is not installed, and the installed Playwright package has no Chromium executable; no system Chromium, Chrome, Firefox or WebKit executable was available.

Therefore these checks are explicitly NOT RUN, not PASS claims:

- browser page-error collection;
- mop / plant runtime interaction;
- first wetting → re-drying → second wetting → distinct hatch runtime interaction;
- six-species runtime surfaces;
- v0.5 runtime regression interactions;
- responsive overflow checks at 320, 390, 768 and 1440 px.

The untouched CSS and existing responsive rules remain in the candidate, but their rendered widths were not asserted without a browser.

## Producer disposition

HOLISTIC_V0_6_CORRECTED_CANDIDATE_PRODUCED = YES

HOLISTIC_V0_6_STATIC_AND_DRIVE_VALIDATION = PASS

HOLISTIC_V0_6_BROWSER_RUNTIME_VALIDATION = UNAVAILABLE

HOLISTIC_V0_6_RESPONSIVE_VALIDATION = UNAVAILABLE

HOLISTIC_V0_6_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES

HOLISTIC_V0_6_CANONICAL = NO

A fresh independent reviewer must bind and exercise the exact corrected Drive bytes. This producer receipt does not replace the preserved independent review and does not claim independent-review PASS.


## Latest responsive-corrected candidate validation

Date: 2026-09-08
Candidate: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
PR head: `10a581d6108280f138cfda33b27a5a1508407d6d`
Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
Google Drive URL: `https://drive.google.com/file/d/1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_/view`
Size: `295505 bytes`
SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`

A new Drive object was uploaded; the raw Drive download was re-downloaded and hashed independently. It measured 295505 bytes and matched the local candidate SHA-256 exactly. The predecessor corrected Drive object `1BnnOxiojKI04HjBtjnvjeUpYV9cdLs24` remains untouched.

### Bounded correction

The candidate differs from the predecessor corrected candidate only by the following second style block before `</head>`:

```css
@media (max-width:420px) {
  .splash-card { min-width:0; max-width:100%; }
  .splash-visual { margin-left:0; margin-right:0; gap:6px; }
  .splash-node { min-width:0; flex:1; width:auto; }
}
```

Static JavaScript compilation, six required species presence, mop/plant presence, structured wetting/re-drying/attempt provenance, and bounded-diff assertions passed.

### Cloud-browser functional evidence

The exact candidate was served through a temporary local preview using the site preview runtime. A separate browser context at its fixed 1363 x 936 viewport:

- loaded the candidate and rendered the breeder shell;
- opened Programs;
- opened all seven seeded program surfaces (Betta, Medaka, Corydoras, Neocaridina, Nothobranchius rachovii, Apistogramma, and guppy);
- confirmed the killifish Annual / soil and Mop / plant surfaces;
- opened the Mop / plant egg-batch form and confirmed date, batch, count basis, and collection/holding notes fields;
- confirmed the persisted annual state retains Attempt 1, re-drying, Attempt 2, distinct hatch provenance, and the explicit no-inference language;
- observed zero app-origin console errors;
- observed no horizontal overflow at the available 1363px viewport (document/body width 1348px versus inner width 1363px).

The producer browser run separately created the repeated annual sequence by recording wetting attempt 1, re-drying it, recording wetting attempt 2, and recording a hatch explicitly linked to attempt 2. The independent tab verified that stored state without adding a second biological event.

### Responsive gate

The required exact widths 320, 390, 768, and 1440px were not executable. The cloud browser runtime starts at a fixed 1363 x 936 viewport and its documented API has no viewport setter. The local environment reports Playwright installed but provides no agent-browser CLI or executable Chromium/Chrome/Firefox/WebKit. Therefore the responsive matrix is **NOT RUN**, not inferred from static CSS and not reported as PASS.

`HOLISTIC_V0_6_LATEST_CANDIDATE_PRODUCED = YES`

`HOLISTIC_V0_6_STATIC_AND_DRIVE_VALIDATION = PASS`

`HOLISTIC_V0_6_BROWSER_FUNCTIONAL_VALIDATION = PASS_AT_1363PX`

`HOLISTIC_V0_6_RESPONSIVE_VALIDATION = NOT_RUN_EXTERNAL_RUNTIME_BLOCKER`

`HOLISTIC_V0_6_READY_FOR_INDEPENDENT_REVIEW = INCOMPLETE`

`HOLISTIC_V0_6_CANONICAL = NO`

`PR_6_MERGE = HOLD`
