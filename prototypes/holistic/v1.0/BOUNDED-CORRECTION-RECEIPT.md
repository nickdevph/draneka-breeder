# Draneka Aquarium Breeder — Holistic v1.0 Bounded-Correction Receipt

Date: 2026-09-09
Status: **PRODUCED / PRODUCER-VALIDATED / NON-CANONICAL / PENDING FRESH INDEPENDENT RE-REVIEW**

## Why this receipt exists

The fresh independent holistic v1.0 review returned `CHANGES_REQUIRED` against the exact original v1.0 candidate.

The review-only receipt is preserved on `review/holistic-v1.0-independent-2026-09-09` at commit:

`c6ad074c4fa15e7275fbf2cd3c6e945182383eab`

That receipt has exactly one parent, the reviewed producer head:

`9c635b04259eb243e5e11e10cdf8a84453b32d41`

The independent review found one promotion blocker and four additional bounded defects:

- `V10-IR-001` — legacy scalar hatch materialization was omitted from remaining-output authority and historical reproductive outputs could acquire positive new commerce quantity;
- `V10-IR-002` — zero-result Program text search lost reset recovery and regressed to `projects` terminology;
- `V10-IR-003` — the wide primary sidebar used `Quick Log` instead of required `Log`;
- `V10-IR-004` — Commerce evidence history overflowed horizontally at `320px`;
- `V10-IR-005` — Settings retained stale `Version 0.2` qualification text.

The prior review receipt remains independent evidence. It was not modified by this producer correction.

## Exact failing reviewed target

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-CANDIDATE.html`
- Google Drive ID: `18egQ7iZ5jCyDJxoHQ9a1SvI2PIdfigos`
- MIME: `text/html`
- Exact bytes: `456195`
- SHA-256: `8c65ef2f2121d71ba29d4bb7d73bf21bc7b1ad71c684df1abe458b8f477b8909`
- PR #11 reviewed producer head: `9c635b04259eb243e5e11e10cdf8a84453b32d41`

The raw reviewed Drive object was rebound before correction and matched this identity. It was not overwritten.

## Exact corrected candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0`
- MIME: `text/html`
- Exact bytes: `458038`
- SHA-256: `4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d`

The corrected object was uploaded as a new immutable Drive file in the same Drive area. A fresh raw Drive download reproduced the exact `458038` bytes and SHA-256 above.

## Bounded corrections

### V10-IR-001 — legacy hatch compatibility and singular remaining-output authority

The prior helper calculated materialized hatch quantity only from structured `hatches[]`. Legacy records whose already-hatched quantity existed only in scalar `hatched` therefore exposed materialized offspring again as remaining reproductive-output quantity.

The correction:

1. recognizes scalar `hatched` as the materialized total for records with no structured hatch history;
2. continues using structured `hatches[]` as authoritative for structured records so scalar summary fields are not double-counted;
3. when the first new structured hatch is appended to a legacy scalar-hatch record, freezes the old scalar in `legacyHatchedBaseline` and adds subsequent structured hatch amounts on top of that baseline;
4. subtracts that normalized materialized total in `eggRemaining()` everywhere that remaining-output authority is consumed;
5. renders legacy scalar hatch observations as observed hatch evidence rather than `Not observed`;
6. rejects `historical=true` reproductive outputs from positive new commerce quantity while preserving provenance/reporting.

Producer runtime results on the corrected exact bytes:

| Output | Materialized hatch | Remaining | Commerce authority |
|---|---:|---:|---|
| `b02` | 52 | 28 | blocked — historical |
| `b03` | 61 | 39 | blocked — historical |
| `b04` | 84 | 16 | 16 |
| `m01` | 12, with 2 removed | 4 | 4 |
| `m02` | 9 structured | 15 | 15 |

A compatibility append test on legacy `b04` preserved baseline `84`, added a structured hatch of `5`, and produced materialized total `89` / remaining `11`.

### V10-IR-002 — Program text-search recovery

The live text-search renderer now uses `Program` terminology and includes `Reset search and filters`. Activating that recovery clears the search and restores the default active Program list.

### V10-IR-003 — wide primary label

The wide primary navigation now renders `Log`, preserving the exact destination set:

`Today / Programs / Log / Grow-out / More`

The underlying action remains the existing Quick Log workflow.

### V10-IR-004 — Commerce history 320px reflow

Long commerce schema/status/ledger content can now shrink and break/wrap inside its containing sheet. Producer runtime measured `0px` Commerce-history sheet overflow at `320 / 390 / 768 / 1440`.

### V10-IR-005 — Settings identity

Settings now identifies `Version 1.0` and the exact bounded-correction artifact filename. Stale `Version 0.2` text is absent.

## Producer runtime validation

Real headless Chromium was used against the corrected exact bytes at exact CSS widths:

- `320`
- `390`
- `768`
- `1440`

At every width, primary navigation rendered exactly `Today / Programs / Log / Grow-out / More`.

The Commerce evidence history sheet measured zero horizontal overflow at all four widths, including `320px`.

The Program zero-result text-search state and reset action were exercised live. The corrected legacy hatch/remaining-output functions and commerce authority were exercised live. No browser runtime exception, log error or `console.error` was observed during the targeted producer matrix.

These checks are construction/correction evidence only. They do not replace the independent review.

## Preserved authority and scope

This correction does not reopen the v1.0 product model. It does not authorize or add:

- new reproductive semantics beyond compatibility normalization of already-recorded hatch evidence;
- new ancestry/generation or genotype inference;
- automatic pairing authority;
- new commerce/marketplace domains;
- backend/API/schema/database changes;
- production AquaticFinder integration;
- Android/web implementation;
- deployment, signing or release;
- v1.1+ scope.

Canonical corrected v0.9 remains product/design authority until and unless the exact corrected v1.0 candidate independently passes, receives Founder promotion, and PR #11 merges.

## Fresh independent re-review required

The complete re-review mandate is:

`prototypes/holistic/v1.0/BOUNDED-CORRECTION-INDEPENDENT-REVIEW-MANDATE.md`

The fresh reviewer must independently bind the new Drive object and current PR #11 producer head, reproduce all five correction paths, and rerun the complete v1.0 qualification contract. Producer PASS statements in this receipt must not be inherited.

```text
V10_IR_001_PRODUCER_CORRECTION = PASS
V10_IR_002_PRODUCER_CORRECTION = PASS
V10_IR_003_PRODUCER_CORRECTION = PASS
V10_IR_004_PRODUCER_CORRECTION = PASS
V10_IR_005_PRODUCER_CORRECTION = PASS

HOLISTIC_V1_0_BOUNDED_CORRECTION_EXACT_BINDING = PASS
HOLISTIC_V1_0_BOUNDED_CORRECTION_DRIVE_ROUND_TRIP = PASS
HOLISTIC_V1_0_BOUNDED_CORRECTION_TARGETED_RESPONSIVE = PASS
HOLISTIC_V1_0_BOUNDED_CORRECTION_PRODUCER_VALIDATION = PASS
HOLISTIC_V1_0_READY_FOR_FRESH_INDEPENDENT_REREVIEW = YES
HOLISTIC_V1_0_INDEPENDENT_REVIEW = PENDING_FRESH_REREVIEW
HOLISTIC_V1_0_PROMOTION_ELIGIBLE = NO_PENDING_FRESH_INDEPENDENT_REREVIEW
HOLISTIC_V1_0_CANONICAL = NO
```