# Draneka Aquarium Breeder — Holistic v0.6 Iteration

Date: 2026-09-08
Status: **DRAFT / PRODUCING / NON-CANONICAL**
Branch: `prototype/v0.6-species-aware-breeder-programs`

## Canonical predecessor

Holistic v0.6 begins from the current canonical holistic v0.5 authority on `main`.

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.5-CANDIDATE.html`
- Google Drive ID: `132jlSrFTAyEoc_PrTd4MPzUk9SV0CYha`
- Size: `257138 bytes`
- SHA-256: `762eb3837f0a137c9b0a5f99e83afc28e481f494098804ac1ad992fb34881bb2`
- Canonical merge commit: `2c8df9d9ab5b523b812a37e5739c1f598f68af97`

v0.5 remains canonical and immutable throughout this iteration unless an exact v0.6 candidate completes the full governed review/promotion/merge cycle.

## Primary product question

Can one Draneka Breeder workflow adapt meaningfully to fundamentally different breeding strategies without becoming six separate species mini-apps or overwhelming the breeder?

## Founder-locked v0.6 objective

Prove the **core + species overlay** architecture.

The stable core remains:

`Breeding Program -> Breeder Stock / Parent Source -> Reproductive Event -> Cohort / Offspring Group -> Grow-out / Split -> Selection -> Holdback / Disposition -> Next Generation`

Species overlays may alter only contextual product behavior such as:

- terminology;
- reproductive archetype label;
- recommended parent/source model;
- likely lifecycle checkpoints shown as guidance;
- suggested breeder-round attention points;
- optional observation prompts;
- contextual reproductive-output wording;
- species-relevant milestone choices.

The overlay must not create a different navigation tree or a separate data model per species.

## Required validation set

### 1. Betta splendens

Archetype: bubble-nest / controlled pair.

Stress requirements:

- exact known-pair ancestry remains evidence-bound;
- spawn / hatch / free-swimming / parent-removal terminology can be surfaced contextually;
- environmental and conditioning prompts remain optional;
- no suggested milestone becomes an event until explicitly recorded.

### 2. Fancy guppy / Poecilia reticulata

Archetype: livebearer line breeding.

Stress requirements:

- known mother with uncertain or historical sire remains valid;
- the overlay can surface brood/drop, sex-separation, maternal-line and selection guidance;
- it must not assign the most recently observed male as father;
- line-management guidance must not become v0.7 grading functionality.

### 3. Medaka / Oryzias latipes

Archetype: repeated adhesive-egg collection.

Stress requirements:

- repeated egg collections remain lightweight records inside one Program;
- the overlay can surface collection / incubation / hatch / fry-grow-out language;
- breeder-group provenance remains distinct from exact egg parentage;
- v0.5 multi-hatch and provenance behavior must remain intact.

### 4. Killifish

Archetype: mop/plant-spawner plus annual/soil-spawner variation.

Prototype focus: annual egg-medium workflow using `Nothobranchius rachovii` as the sample.

Stress requirements:

- egg-medium collection, storage/incubation, development check, wetting attempt and optional re-dry/re-wet concepts must fit without a new top-level workflow;
- incubation timing is guidance only, not a predicted biological fact;
- repeated wetting attempts must not collapse into a single fabricated hatch event.

### 5. Neocaridina davidi

Archetype: colony/selective-line caridean shrimp.

Stress requirements:

- breeding-population provenance remains first-class;
- exact sire/dam stays absent unless actually recorded;
- berried/recruitment/juvenile-selection wording may be surfaced without inventing hatch dates or F-generation precision;
- `remove from breeding population` remains neutral terminology rather than assuming euthanasia.

### 6. Apistogramma-type cave brooders

Prototype sample: `Apistogramma cacatuoides`.

Stress requirements:

- cave/site, eggs/wrigglers/free-swimming, maternal brood care and male-separation decision points can be surfaced contextually;
- parental-care guidance must remain conditional rather than hard-coded as a mandatory removal rule;
- offspring remain normal cohorts once independently tracked.

## Product rules that must remain locked

1. **One core navigation.** No species tab, species app, species dashboard or permanent species destination.
2. **Guidance is not fact.** Suggested milestones, timing and attention points cannot silently mutate state.
3. **Unknown stays unknown.** Overlays cannot infer parentage, genotype, hatch completion, sex, generation or success.
4. **Cohort-first offspring tracking remains canonical.** Individual identity appears only when useful.
5. **Tanks remain location/environment context, not lineage owners.**
6. **v0.5 provenance operations remain intact.** Split, merge, move, count, stage, loss and selected-breeder promotion cannot lose ancestry evidence.
7. **Progressive disclosure.** The default Program screen stays readable; species detail is contextual and optional.

## Explicit non-scope

Do not admit v0.7 work:

- full trait-grading systems;
- breeding-goal scoring;
- line-comparison dashboards;
- longitudinal selection analytics;
- genotype prediction or AI pairing authority.

Do not admit v0.8 work:

- capacity forecasting;
- grow-out allocation planning;
- fully dynamic Breeder Round scheduling engine;
- live-food/culture dependency management beyond contextual guidance.

Do not admit v0.9 work:

- sale-ready handoff;
- commerce integration;
- marketplace operations;
- public provenance/export expansion beyond existing demo boundaries.

## Implementation authority boundary

This iteration is product/design prototype work only.

It must not authorize or mutate:

- Android implementation;
- web application implementation;
- backend services;
- APIs;
- schemas;
- databases;
- production data;
- authentication;
- deployment;
- signing;
- release state.

## Evidence basis

The existing durable research `research/2026-09-08-breeder-needs-and-species-programs.md` supplies the initial six-species research wave and the core+overlay architecture. Fresh source checks during this iteration reconfirmed the major workflow distinctions before candidate production.

## Candidate acceptance target

A v0.6 candidate is producer-ready only if a reviewer can open each required sample Program and observe that:

- the same Program shell and navigation remain in use;
- species-aware language and guidance are meaningfully different;
- the overlay presents only contextually relevant suggestions/prompts;
- no suggestion silently creates a biological record;
- v0.5 cohort/provenance paths still operate;
- the UI remains usable at mobile and desktop widths;
- no prohibited later-version scope appears.

`HOLISTIC_V0_6_IMPLEMENTATION_AUTHORITY_CHANGED = NO`

`HOLISTIC_V0_6_CANONICAL = NO`
