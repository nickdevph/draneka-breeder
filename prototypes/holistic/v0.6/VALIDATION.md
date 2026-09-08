# Draneka Aquarium Breeder — Holistic v0.6 Producer Validation

Date: 2026-09-08
Disposition: **PASS / READY_FOR_INDEPENDENT_REVIEW**
Role: producer-side validation only; this is **not** independent review.

## Exact candidate under validation

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-CANDIDATE.html`
- SHA-256: `b47c5738a8215ad3fdbbf879733d4c021f76f024ed3cd2ce9fd6ff414da702cd`
- Size: `277786 bytes`
- Google Drive ID: `17tU_eBaSzO9zOr7_DMX6n63QZcdkMUu2`

The Drive object was freshly downloaded after upload and remained exactly `277786 bytes` with the same SHA-256. The byte-bound Drive object therefore matches the producer-validated candidate.

## Validation method

- Extracted JavaScript passed `node --check` after producer correction of two pre-binding defects found during validation: an event-array insertion syntax defect and an accidentally omitted `progress(stage)` helper. Neither defective byte set was uploaded, bound, reviewed, promoted, or canonicalized.
- The final exact HTML bytes were loaded directly into headless Chromium using Playwright.
- Browser page-error collection remained empty throughout the final validation runs.
- Actual DOM rendering, navigation, forms, modal sheets, Program creation presets, Breeder Round context, and cohort state mutations were exercised.
- Responsive checks were run at 320, 390, 768, and 1440 px.

## Responsive / navigation validation

At every exercised width:

- `document.documentElement.scrollWidth` equalled the viewport width;
- `document.body.scrollWidth` equalled the viewport width;
- no document-level horizontal overflow was observed;
- mobile top-level navigation remained exactly `Today`, `Programs`, `Log`, `Grow-out`, `More`;
- no species-specific permanent navigation destination appeared.

**Result: PASS.**

## Six-species core + overlay validation

Each required Program rendered inside the same Program shell and displayed exactly one contextual `Species-aware program` section.

### Betta splendens

Observed overlay: `Betta · bubble nest`.

The reproductive-output form used:

- `Spawn observed on`;
- `Spawn name`;
- `Eggs recorded`.

Known-pair source remains `ember`, `lyra`.

**Result: PASS.**

### Fancy guppy / Poecilia reticulata

Observed overlay: `Guppy · livebearer`.

The reproductive-output form used:

- `Birth / drop observed on`;
- `Brood / drop name`;
- `Fry observed`.

The overlay exposes known-mother / sire-uncertainty semantics rather than assigning the latest male by assumption.

**Result: PASS.**

### Medaka / Oryzias latipes

Observed overlay: `Medaka · egg collection`.

The reproductive-output form used:

- `Collection date`;
- `Egg collection name`;
- `Eggs collected`.

Repeated collection remains inside the same Program and retains breeding-group/source provenance.

**Result: PASS.**

### Annual killifish / Nothobranchius rachovii

Observed overlay: `Annual killifish · egg medium`.

The reproductive-output form used:

- `Egg medium collected on`;
- `Egg-medium batch name`;
- `Eggs found / estimated`.

The seeded `k01` egg-medium record has zero hatch records. A breeder-set review date is present, while the durable event text explicitly states `no hatch inferred`.

**Result: PASS.**

### Neocaridina davidi

Observed overlay: `Neocaridina · colony`.

The reproductive-output form used:

- `Recruitment first observed on`;
- `Recruitment observation name`;
- `New juveniles observed`.

Population provenance remains first-class; exact sire/dam and generation precision are not fabricated.

**Result: PASS.**

### Apistogramma cacatuoides

Observed overlay: `Apistogramma · cave brood`.

The reproductive-output form used:

- `Cave spawn observed on`;
- `Cave spawn name`;
- `Eggs recorded / estimated`.

The species cue presents maternal-care and male-separation as observation/decision context, not a mandatory automatic parent-removal rule.

**Result: PASS.**

## Program-creation overlay validation

The new-context wizard exposed the exact six required presets:

- Betta splendens -> `egg` / `Pair`;
- Poecilia reticulata -> `live` / `Known mother`;
- Oryzias latipes -> `collection` / `Group`;
- Nothobranchius rachovii -> `collection` / `Pair`;
- Neocaridina davidi -> `shrimp` / `Group`;
- Apistogramma cacatuoides -> `egg` / `Pair`.

All six presets were applied in runtime without submitting the wizard.

Before and after applying every preset, state counts remained unchanged:

- Programs: `7`;
- reproductive-output records: `10`;
- offspring groups: `8`;
- events: `21`.

Therefore choosing an overlay did not create biological records, parentage, cohorts, outputs or milestones.

**Result: PASS.**

## Species-aware Breeder Round validation

The final runtime queue contained both seeded v0.6 suggestion tasks:

- `t8` -> `Review egg-medium development` -> Program `p6` -> source `Suggestion`;
- `t9` -> `Observe maternal brood care` -> Program `p7` -> source `Suggestion`.

When the active Round item was moved to each Program, the actual UI showed:

- a `Species cue`;
- the species-overlay short label;
- species-relevant contextual guidance;
- the explicit line `Suggestion only · the Breeder Round queue is still built from recorded tasks and active contexts, not species predictions.`

No wetting, hatch, parental-care, separation or other biological event was automatically created by the cue.

**Result: PASS.**

## v0.5 provenance / cohort regression

### Medaka — same reproductive output / different hatch observations

Runtime merged `cm02a` and `cm02b`.

Result:

- resulting active count: `9`;
- `sourceOutputIds = ['m02']`;
- both hatch IDs retained: `mh02a`, `mh02b`;
- source groups became historical/inactive.

**Result: PASS.**

### Medaka — uncertainty + differing reproductive outputs

The older `m01` cohort was explicitly changed to estimated precision, then merged with the combined `m02` group.

Result:

- resulting count: `21`;
- precision: `estimated`;
- source outputs retained: `m01`, `m02`;
- source hatches retained: `legacy-hatch-m01`, `mh02a`, `mh02b`.

**Result: PASS.**

### Life-stage observation

The combined Medaka group was changed from Fry to Grow-out.

Unchanged:

- count `21`;
- tank/location;
- both source output IDs;
- all three source hatch IDs.

**Result: PASS.**

### Selection from combined Medaka provenance

One animal was selected from the combined-source group.

Result:

- exact `parentIds` remained empty;
- both output IDs remained attached;
- all contributing hatch IDs remained attached;
- `provenanceAmbiguous = true`;
- selected record remained `ready = false`.

**Result: PASS.**

### Split after combined provenance

After selection reduced the group from 21 to 20, it was split into `8 + 12`.

Both descendants retained:

- estimated precision;
- both source output IDs;
- all three source hatch IDs.

**Result: PASS.**

### Betta known-pair regression

The canonical Betta offspring group was split and a selected individual was promoted from one descendant.

Selected record retained:

- exact parents `ember`, `lyra`;
- `sourceOutputIds = ['b04']`;
- generation `F2`;
- candidate readiness remained false.

**Result: PASS.**

### Neocaridina population-derived regression

One animal was selected from `cs`.

Result:

- exact `parentIds` remained empty;
- source stock retained `blue-colony`;
- source output retained `s01`;
- generation remained explicitly unestablished / source-population based;
- selected record remained `ready = false`.

**Result: PASS.**

### Merge scope safety

Runtime `mergeCandidates()` exposed only active offspring groups from the same Breeding Program. No cross-Program candidate appeared.

**Result: PASS.**

## Anti-fabrication / fact-action-observation review

Producer runtime and source checks confirmed:

- species-overlay checkpoints are guidance, not completed events;
- wizard templates do not mutate biological records before explicit submission;
- Breeder Round species cues do not produce biological events;
- annual-killifish review/wetting timing is breeder guidance, not a hatch prediction;
- Apistogramma parent-separation guidance is conditional;
- guppy sire uncertainty is retained rather than resolved by assumption;
- Neocaridina population provenance remains distinct from exact pair ancestry;
- suggestions, planned actions, completed actions, observations and derived state remain semantically separate.

**Result: PASS.**

## Producer scope review

No v0.6 expansion was found into:

- species-specific top-level apps/navigation;
- v0.7 full grading, line-comparison or selection analytics;
- genotype prediction or authoritative pairing advice;
- v0.8 capacity forecasting or full dynamic scheduling;
- v0.9 commerce/marketplace handoff;
- individual tracking of every fry/shrimplet;
- hardware/automation;
- application implementation, backend, API, schema, database, deployment or release state.

## Producer disposition

`HOLISTIC_V0_6_PRODUCER_VALIDATION = PASS`

`V0_5_PREDECESSOR_GUARANTEES_PRESERVED_BY_PRODUCER_CHECK = YES`

`CORE_PLUS_SPECIES_OVERLAY_PROOF = PASS`

`SIX_REQUIRED_SPECIES_PATHS = PASS`

`GUIDANCE_DOES_NOT_CREATE_FACTS = PASS`

`HOLISTIC_V0_6_READY_FOR_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_6_CANONICAL = NO`

A fresh independent reviewer must bind and exercise the exact candidate without inheriting these producer PASS claims. Founder promotion and PR merge remain prohibited until that independent gate is satisfied.
