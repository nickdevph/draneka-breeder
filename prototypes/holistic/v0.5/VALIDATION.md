# Draneka Aquarium Breeder — Holistic v0.5 Producer Validation

Date: 2026-09-08
Disposition: **PASS / READY_FOR_INDEPENDENT_REVIEW**
Role: producer-side validation only; this is **not** independent review.

## Exact candidate under validation

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.5-CANDIDATE.html`
- SHA-256: `762eb3837f0a137c9b0a5f99e83afc28e481f494098804ac1ad992fb34881bb2`
- Size: `257138 bytes`
- Google Drive ID: `132jlSrFTAyEoc_PrTd4MPzUk9SV0CYha`

The Drive object was re-downloaded after upload and matched the producer-validated local bytes exactly.

## Static/runtime validation method

- Extracted JavaScript passed `node --check` with no syntax errors.
- The exact HTML bytes were loaded into headless Chromium with Playwright and its actual DOM, JavaScript, forms, navigation, and state mutations were exercised.
- Direct `file://` navigation is blocked by the execution environment, so the exact bytes were loaded directly into the browser document. This is the same bounded runtime approach previously used to exercise the v0.4 prototype in Chromium.
- Representative responsive routes were exercised at approximately 320, 390, 768, and 1440 px widths.

## Functional stress validation

### Medaka — same reproductive output, different partial hatches

Seed state contains egg batch `m02` with two distinct partial hatch records:

- `mh02a` -> offspring group `cm02a`, count 5
- `mh02b` -> offspring group `cm02b`, count 4

Merging `cm02a` and `cm02b` produced:

- resulting count: `9`
- `sourceOutputIds = ['m02']`
- both source hatch IDs retained: `mh02a`, `mh02b`
- both source groups became historical/inactive rather than being deleted
- no quantity double-counting remained in active groups

**Result: PASS.**

### Medaka — differing reproductive output provenance

The merged `m02` group was then combined with an offspring group from `m01`.

Result preserved:

- both reproductive output IDs: `m01`, `m02`
- all contributing hatch provenance, including `mh02a`, `mh02b`, and the retained legacy hatch source for `m01`
- combined biological quantity
- conservative ancestry semantics rather than collapsing the merged group to one false source

**Result: PASS.**

### Count uncertainty through merge

A Medaka source group was first changed to estimated count precision, then merged with another group.

Result:

- biological quantity combined correctly
- merged precision remained `estimated`
- output/hatch provenance remained intact

**Result: PASS.**

### Explicit life-stage change

The combined Medaka offspring group was changed to `Grow-out`.

Unchanged through the life-stage operation:

- biological count
- tank/location
- source output IDs
- source hatch IDs

The operation recorded the lifecycle label without fabricating another reproductive event.

**Result: PASS.**

### Selection/promotion from combined Medaka provenance

An individual was selected from the combined-source Medaka group.

Result:

- exact `parentIds` remained empty
- contributing source output/hatch provenance remained retained
- provenance was marked ambiguous at exact-parent level
- Pair Builder remained unavailable

No exact parents were invented from merged provenance.

**Result: PASS.**

### Split after combined provenance

The combined Medaka group was split after one selected individual had been removed.

Result:

- source group count reduced coherently
- child group counts summed to the remaining source quantity
- both descendants retained both source output IDs and all contributing source hatch IDs

**Result: PASS.**

### Betta known-pair regression

A known-pair Betta offspring group was split and an individual was then selected from a descendant.

Result:

- exact parent IDs remained `ember`, `lyra`
- generation remained `F2`
- split did not create a new generation

**Result: PASS.**

### Neocaridina population-derived regression

An individual was selected from the population-derived Neocaridina group.

Result:

- exact `parentIds` remained empty
- source-population provenance remained available
- Pair Builder remained unavailable

No conventional pair/spawn history was fabricated.

**Result: PASS.**

### Merge scope safety

Merge partner selection offered only active offspring groups within the same Breeding Program. Cross-Program merge was not exposed in this v0.5 candidate.

**Result: PASS / bounded scope.**

## Existing operation regression

Producer runtime checks retained functional behavior for:

- count / estimate changes;
- mortality / loss adjustment;
- move;
- split;
- observation/photo flow;
- quick care / feeding events;
- partial/repeated hatch;
- selected-offspring promotion;
- Program navigation;
- grow-out navigation;
- stock and lineage views.

No JavaScript page errors were observed during the exercised stress paths.

## Responsive / anti-overwhelm validation

Representative routes included Home, Programs, Medaka Program, Grow-out, Medaka cohort, Neocaridina cohort, Stock, Medaka lineage, Guide, and More.

At approximately 320, 390, 768, and 1440 px:

- no document-level horizontal overflow was observed;
- group operations remained contextual rather than becoming new top-level navigation;
- no new permanent navigation destination was introduced.

**Result: PASS.**

## Producer scope review

No material v0.5 expansion was found into:

- detailed grading;
- commerce/marketplace administration;
- finance/CRM;
- predictive genetics or authoritative best-pair decisions;
- broad analytics/reports;
- capacity forecasting;
- full species-overlay implementation;
- individual tracking of every fry/shrimplet;
- hardware/automation.

## Producer disposition

`HOLISTIC_V0_5_PRODUCER_VALIDATION = PASS`

`V0_4_PREDECESSOR_GUARANTEES_PRESERVED_BY_PRODUCER_CHECK = YES`

`HOLISTIC_V0_5_READY_FOR_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_5_CANONICAL = NO`

A fresh independent reviewer must bind and exercise the exact candidate without inheriting these producer PASS claims. Founder promotion and PR merge remain prohibited until that independent gate is satisfied.
