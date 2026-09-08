# Independent Draneka Breeder research / product-architecture review

Date: 2026-09-08
Review type: independent, non-mutating product-research/product-architecture review
Status: **PASS_WITH_CORRECTIONS**

## Overall disposition

`DRANEKA_BREEDER_RESEARCH_REVIEW = PASS_WITH_CORRECTIONS`

The review found the product thesis substantially sound and recommended proceeding to v0.4 with a bounded correction to what v0.4 is trying to prove.

The review explicitly preserved the existing prototype authority:

- canonical holistic authority: **v0.3 lineage**
- SHA-256: `a1432480caefa231b08435464e1bd53f606788817bd39c3738687153667548c4`
- size: `218919 bytes`

No repository/product authority mutation was performed by the reviewer.

## Executive finding

The product direction is strongest when Draneka:

1. connects parentage, reproductive events, offspring, selection and future breeding stock without tying history to a tank;
2. lets offspring remain grouped while individual identity adds little value;
3. adapts vocabulary and next actions to biological workflow without inventing biological facts;
4. keeps marketplace/channel mechanics out of the breeder's biological operating surface.

The primary correction is that the research moved too quickly from:

`Tank is not a stable lineage owner`

to:

`Breeding Program must be the breeder's primary operating object`.

The review accepts **Breeding Program** as useful durable organizing context, especially for selective lines and multi-generation work, but rejects mandatory Program ceremony before breeder-native actions.

## Gate dispositions

| Gate | Verdict | Review conclusion |
| --- | --- | --- |
| G1 Breeder needs evidence | PASS_WITH_CORRECTIONS | Core recordkeeping, cohorts, selection, location changes and lineage are supported; capacity prediction/commerce handoff less independently validated. |
| G2 Breeding Program primary model | PASS_WITH_CORRECTIONS | Valid durable organizing context; insufficient evidence that it should be mandatory first-level interaction for every breeder. |
| G3 Cohort-first offspring model | PASS_WITH_CORRECTIONS | Cohorts remain core, but egg batches and continuous colonies must not be forced into one conventional cohort interpretation. |
| G4 Lineage semantics | PASS_WITH_CORRECTIONS | v0.3 rules are strong; merge semantics, parentage certainty, sperm storage and breeder-visible generation numbering need clarification. |
| G5 Core + species overlay architecture | PASS_WITH_CORRECTIONS | Correct direction provisionally; shared core must survive annual killifish and colony workflows. |
| G6 Initial species research quality | PASS_WITH_CORRECTIONS | Guppy, Medaka and killifish strongest; Neocaridina lineage semantics need deeper work; Apistogramma evidence comparatively weak. |
| G7 Species research coverage | PASS_WITH_CORRECTIONS | Wave 2 is directionally good but should prioritize architectural stress rather than an equal-depth checklist. |
| G8 Dynamic Breeder Round | PASS_WITH_CORRECTIONS | Four-source generation model is sound; task completion and biological observation require harder semantic separation. |
| G9 Complexity / progressive disclosure | PASS_WITH_CORRECTIONS | Anti-overwhelm rules are good; later roadmap still carries ERP-like accumulation risk. |
| G10 Prototype iteration roadmap | PASS_WITH_CORRECTIONS | Species overlay can wait to v0.6, but three contrasting archetypes must stress-test v0.4/v0.5 earlier; v0.8 should narrow. |
| G11 Breeder <-> AquaticFinder commerce boundary | PASS_WITH_CORRECTIONS | Ownership split is correct; commercial outcome flow-back and quantity ownership require tightening. |
| G12 Multi-marketplace thesis | PASS_WITH_CORRECTIONS | Credible as policy-aware channel adaptation, not universal syndication. |
| G13 Competitive differentiation | PASS_WITH_CORRECTIONS | Connected breeding history alone is not differentiated; uncertainty-safe lineage, biological flexibility, cross-mode operation and simplicity may be. |

## Critical findings

### 1. Program is context, not ceremony

Breeders use different simultaneous mental anchors depending on operation: species/pair/spawn, strain/line, female/drop, breeding group/egg batch, locality/egg collection, colony/population, or fishroom location.

Correction:

- retain `Breeding Program` as durable organizing context;
- allow minimal/quick/implicit establishment;
- never require a user to finish administrative Program setup before performing simple breeder-native work.

### 2. Cohort is correct but not universal for every pre-adult state

The review retained cohort-first offspring tracking but identified cases that require additional semantics:

- repeated Medaka egg batches;
- stored annual-killifish egg-medium collections;
- one collection producing multiple hatch cohorts;
- partial hatches/repeated wettings;
- continuous shrimp recruitment where an exact cohort is not observable.

Correction:

`Cohort` remains first-class, but egg batch/stored medium/population recruitment must not be falsely normalized into one conventional dated cohort.

### 3. Species validation must influence v0.4/v0.5 without implementing overlays early

Minimum v0.4 validation set:

- Betta — discrete pair/spawn;
- Medaka — repeated egg collection;
- Neocaridina — population/uncertain parentage.

The reviewer explicitly did **not** recommend pulling the full species-overlay system into v0.4.

### 4. Fact/action semantics require a five-stage distinction

The review required explicit separation among:

`Suggestion -> Scheduled action -> Completed action -> Observation -> Derived state`

Completing `Check for free-swimming fry` cannot itself create `free-swimming = true`.

### 5. Connected history is not sufficient differentiation

Current breeder products already offer portions of breeder -> spawn -> cohort -> lineage workflows.

Potential Draneka differentiation therefore needs to be validated around:

- uncertainty-safe lineage;
- group/unknown parentage;
- egg-batch/cohort/colony-friendly workflows;
- species adaptation without fragmented mini-apps;
- fact vs suggestion/action semantics;
- fast mobile/tank-side operation;
- breeder/commerce separation.

## Species architecture assessment

Verdict:

`CORE_PLUS_SPECIES_OVERLAY = PROVISIONALLY_ACCEPTED`

The review reduced the shared conceptual invariant to:

`Program context -> Parentage context -> Reproductive output/event -> Offspring group -> Selection`

with the following variability allowed:

- parentage: pair, trio, group, colony, partial, or unknown;
- reproductive output: spawn, drop, egg collection, stored egg batch, brood, recruitment;
- offspring group: eggs, hatch cohort, juvenile cohort, estimated population;
- one reproductive output may produce multiple downstream groups;
- merges must not erase distinct ancestry.

### Highest-stress reproductive mode

**Annual/substrate-spawning killifish** were identified as the strongest architecture stress test because:

`collection -> stored egg medium -> variable development -> wetting -> partial hatch -> re-dry -> later wetting -> later hatch`

cannot be reduced safely to a simple `spawn -> cohort` sequence.

### Second strongest stress mode

**Continuous shrimp breeding populations**, because exact parent-pair identity can be unknown while source-line/population provenance remains meaningful.

## Species-specific dispositions

- Betta splendens: **PASS_WITH_CORRECTIONS** — environment/show fields should remain optional/contextual; removal/jarring are not universal required milestones.
- Guppy/livebearers: **PASS** — maternal cohort, sex separation, selection and sire uncertainty are appropriately represented.
- Medaka: **PASS** — repeated egg collection should use breeder-native batch logging, not repeated full `Create Spawn` forms.
- Killifish: **PASS_WITH_CORRECTIONS** — must prove one egg collection can yield multiple hatch cohorts without false generation advancement.
- Neocaridina: **PASS_WITH_CORRECTIONS** — distinguish known individual parentage, known source-population lineage, and exact parentage unknown.
- Apistogramma-type cave brooder: **PASS_WITH_CORRECTIONS** — parental-care decisions should be breeder decision points, not normative male-removal milestones.

## Complexity / anti-overwhelm disposition

### Always visible

- compact program/line identity;
- current breeder/parent context;
- current reproductive output or offspring group;
- location;
- next action needing attention;
- fast log action;
- exceptions.

### Contextual

- egg batches;
- incubation/wetting;
- parental-care decisions;
- sex separation;
- species-specific lifecycle labels;
- species-relevant environmental observations;
- grading sessions;
- expected milestone suggestions.

### Advanced

- full pedigree graph;
- detailed lineage coverage;
- extensive environment history;
- breeder-set performance;
- custom schedules;
- detailed phenotype evaluation;
- locality/provenance detail;
- public report/evidence configuration.

### Deferred

- genetics prediction;
- automated best-pair authority;
- full finance/accounting;
- buyer CRM;
- marketplace UI inside Breeder;
- general aquarium encyclopedia;
- social/community feed;
- broad hardware integrations;
- elaborate analytics dashboards.

## Roadmap disposition

Revised sequence recommended by the review:

`v0.4 Program context + 3-archetype core stress test`

`-> v0.5 Cohort / egg-batch / population operations`

`-> v0.6 Species-aware overlays`

`-> v0.7 Selection / line development`

`-> v0.8 Dynamic Breeder Round / operational attention`

`-> v0.9 Commerce handoff / evidence`

`-> v1.0 Simplify / qualify`

v0.8 should no longer require capacity forecasting, live-food management, and QR functionality unless earlier evidence earns them.

## Commerce boundary disposition

Verdict:

`BREEDER_AQUATICFINDER_BOUNDARY = MODIFY_WITHOUT_MOVING_BOUNDARY`

The bounded contexts remain correct.

Breeder owns biological truth, including biological cohort/individual quantity or estimate.

AquaticFinder owns commerce/channel truth, including allocated quantity, advertised quantity, reservations/orders, pricing, listing IDs/status, and marketplace policy state.

Commercial results may return to Breeder as disposition/reconciliation outcomes but cannot rewrite ancestry or reproductive history.

## Marketplace-management disposition

Verdict:

`MULTI_MARKETPLACE_LISTING_MANAGEMENT = YES_WITH_CONSTRAINTS`

Accepted abstraction:

`Master sellable item -> eligibility -> channel draft -> seller review -> publish`

Rejected abstraction:

`Create once -> publish everywhere`

Marketplace policy/API capability must be first-class and seller publication remains controlled/reviewable.

## Top five risk assumptions

1. Breeders will accept Program as mandatory primary interaction.
2. Conventional cohort semantics cover all offspring workflows.
3. Species differences can remain absent from early core validation.
4. Dynamic Breeder Round can avoid becoming noisy.
5. Connected breeding records alone provide sufficient differentiation.

## Required pre-v0.6 research priority

1. African mouthbrooders.
2. Neocaridina / Caridina colony-selective breeding.
3. Annual/substrate killifish — deeper pass.
4. Ancistrus / cave-spawning Loricariids.
5. Clownfish / marine larval breeders.
6. Discus.
7. Rainbowfish / Corydoras repeated-egg-collection workflows.

## Final A-I recommendations

- **A — Proceed to v0.4:** `YES_WITH_CORRECTIONS`
- **B — v0.4 focus:** `MODIFY` — lightweight Program context + Betta/Medaka/Neocaridina core stress test.
- **C — Roadmap:** sensible with revised v0.4/v0.5 and narrowed v0.8.
- **D — Core + species overlay:** `PROVISIONALLY` accepted; annual killifish are the strongest stress case.
- **E — Research before v0.6:** mouthbrooders, shrimp colonies, annual killifish, cave-spawning Loricariids, marine larvae, discus, repeated egg collectors.
- **F — Commerce boundary:** `MODIFY` only to tighten quantity/outcome flow; do not move marketplace functions into Breeder.
- **G — Multi-marketplace thesis:** `YES_WITH_CONSTRAINTS`.
- **H — Highest risks:** Program ceremony, cohort universality, delayed species validation, noisy Round, weak differentiation.
- **I — Exclusions for v0.4-v0.6:** marketplace management, predictive genetics, automatic pairing authority, finance/CRM, broad analytics, individual-fry tracking, hardware integration, social feed, aquarium encyclopedia, fishroom ERP expansion.

## Founder follow-up

The review was accepted by `decisions/0004-accept-independent-research-review-corrections.md`.

That founder decision changes future planning only. It does not modify the byte-bound v0.3 prototype.
