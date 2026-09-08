# Decision 0004 — Accept independent breeder research review corrections

Date: 2026-09-08
Status: **FOUNDER-ACCEPTED BOUNDED CORRECTION**

## Review disposition accepted

The independent product-research/product-architecture review returned:

`DRANEKA_BREEDER_RESEARCH_REVIEW = PASS_WITH_CORRECTIONS`

Founder disposition: **ACCEPTED**.

The corrections below govern future prototype work. They do not mutate or supersede the current canonical holistic prototype authority.

Current canonical holistic authority remains:

- Prototype: **v0.3 lineage**
- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.3.html`
- SHA-256: `a1432480caefa231b08435464e1bd53f606788817bd39c3738687153667548c4`
- Size: `218919 bytes`

No web/Android implementation is admitted by this decision.

---

## C1 — Breeding Program is durable context, not mandatory ceremony

The product retains **Breeding Program** as a durable organizing context for line/strain/project continuity.

However, future UX must not require a small breeder to perform administrative setup before doing breeder-native work such as:

- pair these animals;
- record a spawn/drop;
- collect eggs;
- record a berried female/recruitment observation;
- move offspring;
- perform selection.

A Program may therefore be lightweight, quick-created, or implicitly established from the breeder's first meaningful action where product semantics allow it.

The product must not assume that `Program` is the breeder's only mental anchor. Depending on workflow, breeders may think primarily in species/line, pair/group, spawn/drop, egg collection, cohort, colony, or fishroom location.

Tanks remain locations/environmental context and are not ancestry owners.

---

## C2 — Shared core must be biologically neutral

The shared product architecture remains **core + species/reproductive overlay**, but the core must not hard-code the assumptions that:

- every breeding unit is a male/female pair;
- every reproductive output is a discrete spawn;
- every reproductive output immediately becomes one dated cohort;
- every cohort has an exact start date;
- every offspring group has exact sire/dam identity.

The neutral conceptual core is:

`Program context -> Parentage context -> Reproductive output/event -> Offspring group -> Selection`

Where:

- parentage context may be pair, trio, group, colony/population, partial, or unknown;
- reproductive output may be spawn, drop, egg collection, stored egg-medium batch, brood, recruitment, or another species-appropriate event;
- offspring group may be egg batch, fry cohort, juvenile cohort, or population/recruitment group;
- exact biological facts and confidence must be preserved rather than normalized into false certainty.

---

## C3 — v0.4 must include a three-archetype stress test

The v0.4 feature scope remains narrow. The full species-overlay framework is still deferred to v0.6.

However, v0.4 must prove that its generic nouns and interactions survive three contrasting breeder workflows:

1. **Betta splendens** — discrete pair/spawn.
2. **Medaka** — repeated egg collection/batches.
3. **Neocaridina** — population/colony breeding with uncertain exact parentage.

This is a model-validation requirement, not a mandate to expose three separate apps or species-specific navigation systems.

v0.4 must fail review if it silently assumes all breeders operate as `pair -> spawn -> dated fry cohort`.

---

## C4 — fact/action semantics are explicitly separated

Future prototype semantics must distinguish:

`Suggestion -> Scheduled action -> Completed action -> Observation -> Derived state`

These are not interchangeable.

Example:

`Check for free-swimming fry`

may be completed with an observation such as:

- observed;
- not observed;
- uncertain;
- not adequately checked/skipped.

Completing the task alone must never assert `free-swimming = true`.

Lifecycle guidance, expected timing, AI assistance, and schedule completion must not manufacture biological facts.

---

## C5 — cohort remains core, but egg-batch and population semantics are first-class

Cohort-first offspring tracking remains accepted.

v0.5 must additionally validate:

- pre-hatch egg batch -> downstream cohort;
- one egg batch producing more than one hatch cohort;
- partial hatch;
- repeat wet/dry or repeat hatch attempts where relevant;
- uncertain counts;
- cohort split;
- lineage-safe merge;
- merge of groups with differing ancestry/provenance;
- promotion of selected offspring into individual breeder candidates;
- population/colony recruitment where exact cohort assignment is not observable.

A merge must not erase source ancestry. If a merged operational group contains multiple provenance paths, all relevant source provenance must remain represented or the merge must be rejected as ancestry-destructive.

---

## C6 — lineage uncertainty remains authoritative

v0.3 lineage rules remain canonical.

Future work must additionally preserve visible distinctions among:

- known individual parentage;
- known parent group/population provenance;
- partially known parentage;
- exact parentage unknown.

Livebearer sperm storage, group spawning, colony breeding, and incomplete records must not cause the most recent/current partner to be asserted as confirmed parent.

A reproductive event remains the event that can advance ancestry/generation semantics, but breeder-visible generation labels such as `F1/F2` must not claim greater parentage precision than the underlying evidence supports.

---

## C7 — species research before v0.6 is reordered by architectural stress

Research priority before the v0.6 overlay system is:

1. African mouthbrooders.
2. Neocaridina + Caridina colony/selective breeding.
3. Annual/substrate killifish, deeper pass.
4. Ancistrus / cave-spawning Loricariids.
5. Clownfish / marine larval breeders.
6. Discus.
7. Rainbowfish / Corydoras repeated-egg-collection workflows.

The objective is not equal-depth coverage of many popular species. It is to find reproductive modes that can break the shared domain model before that model hardens.

---

## C8 — v0.8 is narrowed

v0.8 is now primarily:

**Dynamic Breeder Round / operational attention**

It must prove useful work generation from:

- recurring husbandry;
- lifecycle-derived suggestions;
- breeder-created schedules;
- exception/risk triggers.

Capacity forecasting, live-food/culture management, QR fast entry, and similar scale aids are no longer mandatory v0.8 scope. They may only enter when prior prototype/user evidence shows that they materially reduce missed work or tank-side friction.

---

## C9 — commerce ownership and quantity semantics are tightened

The Breeder -> Draneka AquaticFinder bounded-context split remains accepted.

**Breeder owns biological truth:**

- biological cohort/individual identity;
- biological count/estimate;
- ancestry/provenance;
- selection and breeder disposition intent;
- sale-ready state.

**Draneka AquaticFinder owns commercial/channel truth:**

- quantity allocated to commerce;
- quantity advertised per channel;
- reservations/orders;
- prices;
- external listing IDs/status;
- marketplace policy/eligibility state.

Commercial outcomes may flow back to Breeder only where relevant to breeder history/reconciliation, including:

- quantity sold/disposed;
- quantity released/returned from commerce;
- disposition date/reference;
- remaining biological quantity after an accepted reconciliation;
- optional traceability linkage where appropriate.

A commercial outcome must never rewrite ancestry, reproductive-event history, or breeder selection evidence.

---

## C10 — differentiation claim is narrowed

Draneka must not claim that merely connecting breeder -> spawn -> cohort -> lineage is sufficient product differentiation; current breeder software already offers parts of this chain.

Future differentiation should be tested around:

- uncertainty-safe lineage;
- correct group/unknown parentage;
- egg-batch/cohort/population-compatible operations;
- species/reproductive adaptation without fragmented mini-apps;
- fact vs suggestion/action semantics;
- fast mobile/tank-side operation;
- deliberate separation between biological breeder workflow and marketplace ERP.

These are product hypotheses to validate, not marketing claims established by this decision.

---

## Revised prototype sequence

`v0.4 Program context + 3-archetype core stress test`

`-> v0.5 Cohort / egg-batch / population operations`

`-> v0.6 Species-aware overlays`

`-> v0.7 Selection / line development`

`-> v0.8 Dynamic Breeder Round / operational attention`

`-> v0.9 Commerce handoff / evidence`

`-> v1.0 Simplify / qualify`

---

## Explicit exclusions for v0.4-v0.6

Do not add during the next three prototype iterations:

- predictive genetics;
- automatic `best pair` authority;
- marketplace management/publishing;
- finance/accounting;
- buyer CRM;
- broad analytics dashboards;
- individual records for every fry/shrimplet;
- broad capacity forecasting;
- live-food inventory ERP;
- social/community feed;
- generic aquarium encyclopedia;
- hardware/controller integration;
- club/BAP administration;
- extra top-level navigation merely to expose new domain objects.

---

## Founder conclusion

`PROCEED_TO_V0_4 = YES_WITH_CORRECTIONS`

`V0_3_CANONICAL_AUTHORITY = UNCHANGED`

`V0_4_PRIMARY_FOCUS = LIGHTWEIGHT_PROGRAM_CONTEXT_AND_CORE_VALIDATION`

`SPECIES_OVERLAY_IMPLEMENTATION = DEFER_TO_V0_6`

`COMMERCE_OWNERSHIP = DRANEKA_AQUATICFINDER`
