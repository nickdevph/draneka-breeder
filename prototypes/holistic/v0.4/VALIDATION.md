# Draneka Aquarium Breeder — Holistic v0.4 Candidate Validation

Date: 2026-09-08
Candidate status: **READY_FOR_INDEPENDENT_REVIEW / NON-CANONICAL**

Exact artifact under validation:

- `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.4-CANDIDATE.html`
- SHA-256: `31fed7d432ab80151a192991744f8957dda157e96a03d0e6d40a94900b6b1bbc`
- Size: `235203 bytes`
- Drive ID: `1OI8GqmNVINsYQ2BqiuXyPgaFWgf1ZMv6`

## Static validation

- HTML source generated successfully.
- Embedded JavaScript extracted and checked with `node --check`: **PASS**.
- Seed fixture loaded independently: **PASS**.
- v0.4 seed includes the required three architecture stress-test paths:
  - Betta discrete pair/spawn;
  - Medaka repeated egg collection;
  - Neocaridina breeding population / uncertain exact parentage.

## Render/runtime smoke checks

The candidate was executed in a bounded DOM/browser-runtime harness sufficient to render the product functions without invoking production services.

Passed screens / flows:

- Home / Today: **PASS**
- Programs list: **PASS**
- Betta Program overview: **PASS**
- Medaka Program overview: **PASS**
- Neocaridina Program overview: **PASS**
- Breeder Round: **PASS**
- Medaka Quick Log: **PASS**
- Medaka `Collect eggs` form: **PASS**
- Medaka selected-batch `Record hatch` form: **PASS**
- Global Quick Log: **PASS**
- Event-first lightweight context start: **PASS**

## Mutation / semantic checks

### Repeated Medaka reproductive output

- Recording another Medaka collection adds one reproductive-output record without creating a new Program: **PASS**.
- The new collection becomes the current output while the previous open egg batch remains independently open: **PASS**.

### Multiple open egg batches

- A non-current selected Medaka egg batch can be hatched independently: **PASS**.
- The resulting offspring group is tied to the selected egg batch: **PASS**.
- If another egg batch remains open, the Program remains in the egg-attention state rather than falsely collapsing to a single global Fry state: **PASS**.

### Fact/action boundary

- Completing a scheduled egg-collection check without logging eggs does not create a reproductive-output record: **PASS**.
- The completion creates a `check` event rather than a biological event: **PASS**.

### Parentage stress paths

- Neocaridina seed preserves breeding-population provenance with exact parents unknown: **PASS**.
- Betta seed preserves a discrete known-pair path: **PASS**.

## Defect corrected during producer validation

An intermediate build allowed hatching one Medaka batch to move the whole Program out of the egg stage even when another egg batch remained open.

Correction applied before candidate binding:

- egg-batch hatch state is now evaluated independently;
- open egg outputs keep the Program in egg-attention state;
- the corrected bytes are the only bytes bound by the SHA-256 above.

## Not proven by this receipt

This is producer-side qualification, not independent product review. It does not prove:

- independent UX approval;
- comprehensive browser/device matrix coverage;
- accessibility conformance;
- real breeder usability;
- production API/schema suitability;
- Android parity;
- marketplace integration;
- species-overlay completeness.

Those remain outside the v0.4 candidate's authority.

## Disposition

`HOLISTIC_V0_4_CANDIDATE_VALIDATION = PASS`

`HOLISTIC_V0_4_INDEPENDENT_REVIEW = REQUIRED`

`CANONICAL_HOLISTIC_AUTHORITY = V0_3_UNCHANGED`
