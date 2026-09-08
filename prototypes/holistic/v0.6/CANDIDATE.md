# Draneka Aquarium Breeder — Holistic v0.6 Candidate

Date: 2026-09-08
Status: **READY_FOR_INDEPENDENT_REVIEW / NON-CANONICAL**
PR: `#6` — Holistic v0.6 — Species-aware breeder programs

This record binds the first immutable holistic v0.6 candidate produced from the exact canonical v0.5 predecessor. Candidate production and producer validation do not promote it. v0.5 remains canonical until the exact v0.6 candidate independently passes, receives founder promotion, and PR #6 is merged to `main`.

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-CANDIDATE.html`
- SHA-256: `b47c5738a8215ad3fdbbf879733d4c021f76f024ed3cd2ce9fd6ff414da702cd`
- Size: `277786 bytes`
- Google Drive ID: `17tU_eBaSzO9zOr7_DMX6n63QZcdkMUu2`
- Google Drive URL: `https://drive.google.com/file/d/17tU_eBaSzO9zOr7_DMX6n63QZcdkMUu2/view`

The Drive object was freshly downloaded after upload. The downloaded file remained exactly `277786 bytes` and independently hashed to the same SHA-256 above. This is the producer-validated immutable candidate byte set.

## Canonical predecessor

v0.6 is derived from the exact canonical v0.5 authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.5-CANDIDATE.html`
- SHA-256: `762eb3837f0a137c9b0a5f99e83afc28e481f494098804ac1ad992fb34881bb2`
- Size: `257138 bytes`
- Google Drive ID: `132jlSrFTAyEoc_PrTd4MPzUk9SV0CYha`
- Canonical merge commit: `2c8df9d9ab5b523b812a37e5739c1f598f68af97`

v0.5 remains immutable and canonical while this PR is open.

## v0.6 product proof

### One stable core plus species overlays

The candidate keeps one Program / reproductive-output / cohort / lineage structure and one top-level navigation model. Species-aware behavior is contextual rather than a new species-specific app structure.

An overlay can change:

- breeder-facing terminology;
- reproductive archetype explanation;
- expected parent/source model;
- contextual output-record wording;
- likely lifecycle checkpoints shown as guidance;
- optional observation prompts;
- Breeder Round context cues;
- lightweight Program-creation defaults.

An overlay cannot silently create parentage, reproductive events, hatches, generation labels, sex, genotype, task completion, or breeding outcomes.

### Six required validation programs

The candidate exposes and exercises:

1. `Betta splendens` — bubble-nest / controlled pair.
2. `Poecilia reticulata` — livebearer line context with known-mother / uncertain-sire semantics.
3. `Oryzias latipes` — repeated egg collection with breeding-group provenance.
4. `Nothobranchius rachovii` — annual killifish egg-medium / development / wetting-context guidance.
5. `Neocaridina davidi` — colony / population-derived recruitment without invented individual parentage.
6. `Apistogramma cacatuoides` — cave-brood / parental-care context with conditional, not mandatory, parent-separation guidance.

### Program creation

The new breeding-context wizard offers the six species presets as optional contextual templates. Selecting a preset changes suggested method, parent/source form, terminology and default location where sample data exists. Merely applying a template does not create a Program, reproductive output, cohort, event, parentage edge or milestone.

### Species-aware reproductive logging

The same core logging sheet adapts its words and prompts. Examples include:

- Betta: `Spawn observed on`, `Spawn name`, `Eggs recorded`.
- Guppy: `Birth / drop observed on`, `Brood / drop name`, `Fry observed`.
- Medaka: `Collection date`, `Egg collection name`, `Eggs collected`.
- Annual killifish: `Egg medium collected on`, `Egg-medium batch name`, `Eggs found / estimated`.
- Neocaridina: `Recruitment first observed on`, `Recruitment observation name`, `New juveniles observed`.
- Apistogramma: `Cave spawn observed on`, `Cave spawn name`, `Eggs recorded / estimated`.

These are UI adaptations over the shared record model, not separate species schemas.

### Species-aware Breeder Round

The Breeder Round remains assembled from recorded tasks and active breeder contexts. Species overlays add a visible context cue for the current Program, but that cue is explicitly suggestion-only.

The seeded annual-killifish and Apistogramma examples demonstrate this boundary:

- `Review egg-medium development` is a `Suggestion`, not a wetting or hatch event.
- `Observe maternal brood care` is a `Suggestion`, not a recorded parental-care outcome.

### Annual killifish uncertainty

The sample `Nothobranchius rachovii` egg-medium record contains a breeder-set review date but zero hatch records. Its event text explicitly states that no hatch was inferred. The overlay treats wetting/development timing as guidance rather than a biological prediction.

### Existing v0.5 cohort/provenance behavior retained

The candidate retains:

- exact and estimated count semantics;
- mortality/loss distinct from unexplained count revision;
- move;
- split with provenance propagation;
- same-output and differing-output merge;
- source reproductive-output and hatch provenance retention;
- historical source groups after split/merge;
- life-stage observation without count/location/ancestry mutation;
- photo / observation;
- quick care / feeding events;
- selected-offspring promotion;
- conservative exact-parent handling after combined provenance;
- Betta exact-parent behavior;
- Medaka partial/repeated hatch behavior;
- Neocaridina population-derived / unknown-exact-parent behavior.

## UX / scope discipline

- No species-specific top-level navigation was introduced.
- Core mobile navigation remains `Today`, `Programs`, `Log`, `Grow-out`, `More`.
- Species information is progressive/contextual on Program, creation and Breeder Round surfaces.
- Cohort-first offspring tracking remains intact.
- Tanks remain current locations/environment context, not lineage owners.
- Suggestions remain visually and semantically separate from completed biological records.

## Explicitly not admitted

This candidate does not introduce the planned later-version work for:

- v0.7 full grading, breeding-goal scoring, line-comparison or longitudinal selection systems;
- genotype prediction or opaque pairing authority;
- v0.8 capacity forecasting, allocation planning or a fully dynamic scheduling engine;
- v0.9 commerce / marketplace handoff;
- production implementation of any kind.

## Producer qualification

Producer validation is recorded in `prototypes/holistic/v0.6/VALIDATION.md`.

`HOLISTIC_V0_6_CANDIDATE_PRODUCED = YES`

`HOLISTIC_V0_6_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_6_READY_FOR_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_6_CANONICAL = NO`

A fresh independent reviewer must bind and exercise these exact bytes without inheriting the producer PASS decision.
