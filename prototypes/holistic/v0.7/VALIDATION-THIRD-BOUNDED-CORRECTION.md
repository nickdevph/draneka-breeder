# Producer Validation — Holistic v0.7 Third Bounded Correction

Date: 2026-09-08
Status: **PASS / READY_FOR_FRESH_INDEPENDENT_REVIEW / NON-CANONICAL**
PR: `#7`

## Exact candidate validated

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`
- Size: `334514 bytes`
- SHA-256: `1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`
- Drive round-trip: exact size/hash match

Producer validation does not promote this candidate and must not be inherited as independent evidence.

## Static qualification

- Inline JavaScript extracted from the exact candidate and parsed with Node.js `v22.16.0`: **PASS**.
- Candidate-to-predecessor diff is bounded to Pair Builder parent-resolution behavior plus the Pair Builder Stock-A change fallback. No filial-generation, goal-history, provenance, evidence, selection-history, scheduling, commerce, backend, Android, or deployment logic was modified.

## Real-browser qualification

Runtime: Chromium `144.0.7559.96`, controlled with Playwright.

The SHA-bound exact HTML bytes were loaded into a real Chromium document using `page.set_content()`.

### V07-SECOND-IR-001 reproduction matrix

For each current negative disposition below, the producer started from fresh candidate state, recorded the disposition for already-ready `Atlas · retained F2` through the normal selection-session UI with a breeder-entered reason, then opened Pair Builder with Atlas requested.

| Disposition | historical `ready` | current disposition | `breedingStockSelectable(Atlas)` | `pairBuilderEligible(Atlas)` | Atlas in Stock A options | Atlas active in relationship/result | result |
|---|---:|---|---:|---:|---:|---:|---|
| Non-breeding | true | Non-breeding | false | false | no | no | PASS |
| Retire | true | Retire | false | false | no | no | PASS |
| Sale / rehome | true | Sale / rehome | false | false | no | no | PASS |

In all three cases Pair Builder normalized to currently eligible stock (`Forge` + `Iris` in the seeded runtime state). Atlas did not appear in the active relationship panel, ancestry/coverage subject, or Atlas demo-pair controls. A direct call to the example loader after each negative disposition also failed closed and retained only currently eligible active parents.

### Holdback semantics

- Ready Atlas → `Holdback`: `ready=true`, selectable=true, Pair-Builder-eligible=true; Atlas remained usable. **PASS**.
- A producer-only runtime fixture representing a non-ready Betta candidate was assigned `Holdback` through the ordinary selection-session UI: `ready=false`, selectable=false, Pair-Builder-eligible=false`. Holdback did not create readiness. **PASS**.

No producer-only fixture is persisted in candidate bytes.

### Filial-generation guardrail smoke

The unchanged generation helper was exercised:

- `F2 × F1` → `Generation not established · recorded parents F2 × F1`: **PASS**.
- same-line `F1 × F1` → `F2`: **PASS**.

This is a smoke guard only; the fresh independent reviewer must rerun the full UI generation/provenance path.

## Responsive Pair Builder smoke

Pair Builder was rendered at the required widths. No page/console errors and no document/body horizontal overflow were observed.

| width | `window.innerWidth` | doc client | doc scroll | body scroll | errors |
|---:|---:|---:|---:|---:|---:|
| 320 | 320 | 320 | 320 | 320 | 0 |
| 390 | 390 | 390 | 390 | 390 | 0 |
| 768 | 768 | 768 | 768 | 768 | 0 |
| 1440 | 1440 | 1440 | 1440 | 1440 | 0 |

This producer smoke does not replace the required fresh independent full responsive/runtime matrix.

## Producer disposition

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_EXACT_BINDING = PASS`

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_JS_SYNTAX = PASS`

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_PAIR_BUILDER_AUTHORITY = PASS_PRODUCER`

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_HOLDBACK_SEMANTICS = PASS_PRODUCER`

`HOLISTIC_V0_7_THIRD_BOUNDED_CORRECTION_RESPONSIVE_SMOKE = PASS_PRODUCER`

`HOLISTIC_V0_7_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_7_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_7_PROMOTION_ELIGIBLE = NO_PENDING_FRESH_INDEPENDENT_REVIEW`

`HOLISTIC_V0_7_CANONICAL = NO`

`PR_7_MERGE = HOLD`
