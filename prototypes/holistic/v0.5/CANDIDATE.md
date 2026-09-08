# Draneka Aquarium Breeder — Holistic v0.5 Candidate

Date: 2026-09-08
Status: **READY_FOR_FOUNDER_PROMOTION / NON-CANONICAL**
PR: `#4` — Holistic v0.5 — Cohort / egg-batch / population operations

This record binds the first immutable holistic v0.5 candidate produced from the exact canonical v0.4 predecessor. Candidate creation and producer validation do not promote it. v0.4 remains canonical until the exact final v0.5 candidate independently passes, receives founder promotion, and PR #4 is merged to `main`.

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.5-CANDIDATE.html`
- SHA-256: `762eb3837f0a137c9b0a5f99e83afc28e481f494098804ac1ad992fb34881bb2`
- Size: `257138 bytes`
- Google Drive ID: `132jlSrFTAyEoc_PrTd4MPzUk9SV0CYha`
- Google Drive URL: `https://drive.google.com/file/d/132jlSrFTAyEoc_PrTd4MPzUk9SV0CYha/view`

The uploaded Drive object was downloaded again after upload and independently rebound to the same 257,138 bytes and SHA-256 above. The downloaded bytes were byte-for-byte identical to the locally producer-validated candidate.

## Canonical predecessor

v0.5 is derived from the exact founder-promoted v0.4 authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.4-BOUNDED-CORRECTION-CANDIDATE.html`
- SHA-256: `4f82843586c630d3e7542def1632feb8e5c5e766b7d9909e8e41d69b41163a16`
- Size: `242549 bytes`
- Google Drive ID: `19EXK4Gh5Da2_W_5HuUU-ws7feON7qMV7`

The v0.4 predecessor remains immutable and canonical while this PR is open.

## v0.5 capability added

### Group merge with provenance preservation

Active offspring groups may be merged only within the same Breeding Program in this prototype iteration. A merge:

- combines biological quantity without double-counting the source groups;
- preserves the union of all `sourceOutputIds`;
- preserves the union of all `sourceHatchIds`;
- propagates estimated count precision if either source count is estimated;
- retains both source groups as historical records with `mergedInto` rather than deleting their history;
- records merge history on the source groups and resulting group;
- records a move when a source group changes tank as part of the merge;
- flags pending source-group tasks for reassignment rather than silently moving them;
- does not infer a single exact parent pair when combined provenance does not support one.

Same-output / different-hatch merges therefore preserve one reproductive output and multiple source hatch observations. Differing-output merges preserve all contributing outputs instead of erasing ancestry evidence.

Cross-Program merge is deliberately not admitted in v0.5.

### Explicit life-stage observation

An offspring group can record a breeder-observed life-stage change such as Fry or Grow-out without altering quantity, location, ancestry, or provenance.

### Conservative promotion from combined-source groups

Selection/promotion from an offspring group retains exact parent IDs only when the full source evidence supports the same recorded controlled parent pair. For combined or population-derived provenance where exact origin cannot be resolved safely:

- exact parents remain absent;
- contributing source output/hatch arrays remain attached;
- ambiguous provenance remains visible;
- Pair Builder eligibility remains blocked rather than presenting an unsupported relatedness claim.

### Existing v0.4 operations retained and made coherent with v0.5

The candidate retains and exercises:

- exact or estimated group counts;
- count adjustment and mortality/loss;
- move;
- split with provenance propagation;
- photo/observation;
- quick care / feeding events;
- selected-offspring promotion;
- partial and repeated hatch observations;
- multiple hatch-derived offspring groups from one egg batch;
- population-derived Neocaridina recruitment without fabricated exact parents.

## Required stress-state data

The Medaka sample state includes one egg batch with two distinct partial hatch observations and two resulting offspring groups. This gives the candidate an immediately exercisable same-output / differing-hatch merge path without requiring review setup mutations first.

The candidate also preserves Betta known-pair and Neocaridina population-derived paths for regression and merge/promotion stress testing.

## UX / scope discipline

- No new top-level navigation was introduced.
- Group operations remain contextual to offspring / grow-out surfaces.
- The interface does not introduce individual records for every fry or shrimplet.
- No grading, marketplace, finance/CRM, predictive genetics, broad analytics, capacity forecasting, hardware, or full species-overlay expansion is admitted.
- Tanks remain locations rather than lineage owners.
- Suggestion, scheduled action, completed action, observation, and derived state remain distinct.

## Independent review qualification

The exact candidate passed a fresh independent review. The complete review receipt is recorded in `reviews/holistic-v0.5-independent-review-2026-09-08.md`.

- `HOLISTIC_V0_5_INDEPENDENT_REVIEW = PASS`
- `HOLISTIC_V0_5_CORRECTION_REQUIRED = NO`
- `HOLISTIC_V0_5_READY_FOR_FOUNDER_PROMOTION = YES`
- No unresolved BLOCKER or MAJOR promotion-blocking findings.

Founder promotion is still separate and must apply to these exact bytes. v0.5 remains non-canonical until that promotion and the later merge of PR #4.

## Producer qualification

Producer validation is recorded in `prototypes/holistic/v0.5/VALIDATION.md`.

`HOLISTIC_V0_5_CANDIDATE_PRODUCED = YES`

`HOLISTIC_V0_5_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_5_READY_FOR_INDEPENDENT_REVIEW = YES`
`HOLISTIC_V0_5_INDEPENDENT_REVIEW = PASS`
`HOLISTIC_V0_5_READY_FOR_FOUNDER_PROMOTION = YES`
`HOLISTIC_V0_5_CANONICAL = NO`

No correction was required. If a later correction is authorized, it must remain inside PR #4 and produce a new immutable candidate binding.
