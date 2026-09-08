# Draneka Aquarium Breeder — Prototype Iteration Roadmap

Updated: 2026-09-08
Current holistic authority: **v0.3 lineage**
Review correction authority: `decisions/0004-accept-independent-research-review-corrections.md`

This roadmap governs what each prototype iteration is allowed to focus on. It does not itself promote any prototype.

## Roadmap principle

Each iteration has **one primary product question**. Features that do not help answer that question are deferred.

The app should feel like a breeder's working surface, not a database administration console. New capability should normally appear contextually inside an existing workflow before a new permanent navigation destination is created.

The shared architecture must remain biologically neutral. A `Breeding Program` is durable organizing context, not mandatory administrative ceremony before breeder-native actions.

---

## v0.4 — Lightweight Program context + core stress test

### Primary question

Can a breeder maintain a lightweight stable breeding context across parentage, reproductive output and offspring without being forced into tank-centric or pair/spawn-centric assumptions?

### Must prove

- Lightweight Program creation/context with species/variety/line and an optional plain-language breeding goal.
- Program entry must not block immediate breeder-native work; quick-create/implicit context is allowed where semantics remain clear.
- Breeder stock membership.
- Parentage context that can represent pair, trio/group, population/colony, partial, or unknown parentage.
- Reproductive output/event creation without assuming every output is a conventional discrete spawn.
- Offspring group creation without assuming every group starts as a dated fry cohort.
- Program/context page showing active parents/parent groups, active reproductive outputs, offspring groups, current locations, and next relevant work.
- Tanks shown as current locations/environmental context, not the owner of ancestry.
- Explicit semantic separation:
  - suggestion;
  - scheduled action;
  - completed action;
  - observation;
  - derived state.
- Parentage/generation labels must not claim more certainty than the recorded evidence.

### Required architecture stress tests

The same generic backbone must be exercised against three contrasting workflows without implementing the full species-overlay system:

1. **Betta splendens** — discrete pair/spawn.
2. **Medaka** — repeated egg collection/batches.
3. **Neocaridina** — breeding population/colony with uncertain exact parentage.

The candidate should fail review if its generic nouns silently assume `pair -> spawn -> dated fry cohort`.

### Deliberately defer

- full species-overlay implementation;
- marketplace management;
- capacity forecasting;
- trait/genetics intelligence;
- full analytics dashboards;
- live-food culture management;
- predictive pairing.

### UX budget

No major new bottom-navigation destination unless absolutely required. Prefer lightweight context and fast actions over setup screens. A breeder should be able to enter meaningful work before completing advanced metadata.

### Exit criterion

A breeder can answer: **What breeding context am I working in, which parentage is known, what reproductive output occurred, and what offspring exist now?**

And the same core remains coherent for Betta, Medaka, and Neocaridina.

---

## v0.5 — Cohort / egg-batch / population operations

### Primary question

Can the breeder manage dozens or hundreds of offspring, eggs, or recruits without individual-record overhead or ancestry loss?

### Must prove

- count/estimate with uncertainty;
- move;
- split;
- lineage-safe merge;
- merge of groups with differing ancestry/provenance without ancestry erasure;
- life-stage change;
- loss/mortality adjustment;
- photo/observation;
- quick feeding/care event where relevant;
- promotion of selected offspring into individually tracked breeder candidates;
- ancestry preserved through cohort splits and promotion;
- pre-hatch egg batch -> downstream cohort;
- one egg batch producing more than one hatch cohort;
- partial hatch;
- repeated wet/dry or hatch attempts where relevant;
- population/colony recruitment where exact cohort assignment is unavailable.

### Product rule

`Cohort` remains the default offspring/grow-out primitive where it fits, but egg batches and continuous populations are first-class semantics and must not be falsely represented as conventional cohorts.

A merge must preserve all relevant source provenance or be rejected as ancestry-destructive.

### UX focus

Tank-side actions should generally require a few taps and should not open a full edit form unless the breeder asks for details.

### Deliberately defer

- detailed grading systems;
- multi-channel commerce;
- broad reports;
- sophisticated capacity projections;
- full species-overlay UI.

### Exit criterion

A breeder can maintain real grow-out, egg-batch, and population-derived offspring through moves, splits, merges, partial hatches, and promotion without losing lineage or drowning in forms.

---

## v0.6 — Species-aware breeder programs

### Primary question

Can Draneka adapt to different breeding biology without becoming visually or conceptually fragmented?

### First validation overlays

1. Betta splendens — bubble nest / individual holdbacks.
2. Fancy guppy — livebearer line breeding and sex separation.
3. Medaka — repeated egg collection and hatch batches.
4. Killifish — mop/plant and annual soil-spawner workflows.
5. Neocaridina / Caridina — colony/selective-line breeding.
6. Apistogramma-type cave brooders — parental care workflow.

### Required pre-v0.6 research stress priorities

Research is prioritized by architectural diversity rather than species popularity:

1. African mouthbrooders.
2. Neocaridina + Caridina colony/selective breeding.
3. Annual/substrate killifish — deeper pass.
4. Ancistrus / cave-spawning Loricariids.
5. Clownfish / marine larval breeders.
6. Discus.
7. Rainbowfish / Corydoras repeated-egg-collection workflows.

### Must prove

- one stable navigation/core model across materially different reproductive modes;
- species-specific vocabulary;
- contextual optional fields;
- suggested milestones/tasks;
- breeder override/custom timing;
- explicit distinction between recorded fact and template suggestion/action;
- correct handling of uncertain/group/population parentage;
- species overlays do not create isolated mini-apps.

### UX focus

Only currently relevant species actions are visible. Advanced or uncommon fields remain collapsed.

### Exit criterion

A Betta breeder, repeated-egg collector, killifish breeder, and shrimp line breeder can all use the product naturally without seeing large amounts of irrelevant workflow.

---

## v0.7 — Selection and line development

### Primary question

Can the product support the breeder's actual improvement/selection decisions rather than merely documenting reproduction?

### Must prove

- breeding goal;
- time-stamped phenotype/trait evaluations;
- photos/evidence attached to evaluations;
- selection session;
- breeder holdback;
- non-breeding/sale/rehome/retire disposition;
- comparison of generations/cohorts against the stated goal;
- current Pair Builder relatedness checks retained from lineage authority.

### Product rule

Phenotype does not prove genotype. Unknown genetics remain unknown.

### Intelligence boundary

AI may summarize recorded outcomes, surface patterns, or identify missing evidence. It must not present an opaque `best pair` decision as authoritative.

### Exit criterion

A breeder can answer: **What did I select for, what did this generation produce, and why did I keep these animals?**

---

## v0.8 — Dynamic Breeder Round / operational attention

### Primary question

Can Draneka reliably surface important breeder work across several active breeding contexts without becoming noisy or turning biological expectations into recorded facts?

### Must prove

Breeder Round generated from:

- recurring husbandry;
- lifecycle-derived suggestions;
- breeder-created schedules;
- exceptions/risk triggers.

The UI and underlying semantics must preserve the distinction among:

- suggestion;
- scheduled action;
- completed action;
- observation;
- derived state.

Completing a check must not automatically assert the biological condition being checked.

### Evidence-gated optional aids

The following are **not mandatory v0.8 scope** and may enter only if prior prototype/user evidence shows material reduction in missed work or tank-side friction:

- grow-out capacity pressure;
- expected separation/split pressure;
- live-food/culture dependencies;
- incubation/wetting/egg alerts beyond the basic dynamic Round model;
- QR/location fast-entry.

### UX focus

Prioritize `what needs attention` over dashboards and charts. Suggestions must be suppressible/deferable and should not flood the Round.

### Exit criterion

A breeder with several active breeding contexts can begin the day from Breeder Round and trust that important work is surfaced without confusing a reminder, completed task, and biological observation.

---

## v0.9 — Commerce handoff and evidence

### Primary question

Can successful breeding records become sale-ready inventory and trustworthy provenance without duplicate data entry or duplicate quantity ownership?

### Must prove

- individual or cohort/batch marked sale-ready;
- explicit public/private fact selection;
- photos and permissible lineage/provenance attached;
- structured handoff to Draneka AquaticFinder;
- spawn/breeding/provenance report generation from existing records;
- commercial status does not rewrite breeding history;
- Breeder biological quantity remains distinct from AquaticFinder commerce-allocated quantity;
- commercial outcomes can reconcile back without changing ancestry or reproductive history.

### Explicit boundary

No eBay/Etsy/etc. listing-management UI in Draneka Breeder. Marketplace operations belong to Draneka AquaticFinder.

### Exit criterion

A breeder can finish selection in Breeder and create a commerce-ready handoff without retyping identity, ancestry, age, traits, biological quantity, or photos, while AquaticFinder separately owns channel allocation and sales state.

---

## v1.0 candidate — Simplify and qualify

v1.0 should not be a broad feature iteration.

Focus on:

- removing redundant surfaces;
- improving discoverability;
- measuring tap/step cost of frequent tasks;
- empty/error/recovery states;
- accessibility;
- mobile/web parity boundaries;
- terminology consistency;
- independent breeder usability review;
- production implementation-admission evidence.

---

# Backlog that does not earn prototype priority by itself

The following may be valuable but should not displace the bounded sequence above:

- full finance/accounting;
- social/community feed;
- public marketplace;
- generalized aquarium encyclopedia;
- complex genetics calculators without validated models;
- automatic breeding-pair authority;
- individual records for every fry/shrimplet;
- duplicate Journal analytics;
- hardware integration;
- broad club/BAP automation;
- extensive sales CRM inside Breeder;
- broad capacity forecasting;
- live-food inventory ERP.

---

# Anti-overwhelm design gates for every iteration

A candidate should fail review if it violates these without strong evidence:

1. **Navigation gate:** new capability should not automatically mean new top-level navigation.
2. **Context gate:** irrelevant species fields should stay hidden.
3. **Speed gate:** frequent tank-side events should be faster than writing the equivalent note manually.
4. **Grouping gate:** offspring remain grouped until individual identity creates value; egg batches/populations must not be forced into false cohort semantics.
5. **Fact/action gate:** suggestion, scheduled action, completion, observation, and derived state remain distinct.
6. **Uncertainty gate:** unknown parentage/genetics remain unknown; visible generation labels do not imply unsupported precision.
7. **Boundary gate:** commerce-channel complexity remains in Draneka AquaticFinder.
8. **Iteration gate:** if a feature does not answer the current iteration's primary question, defer it.
9. **Program-friction gate:** Program context must not become mandatory ceremony before simple breeder-native actions.
10. **Differentiation gate:** connected records alone are not treated as sufficient differentiation; simplicity, uncertainty safety, biological flexibility, and operational speed must be validated.
