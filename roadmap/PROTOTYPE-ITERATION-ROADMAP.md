# Draneka Aquarium Breeder — Prototype Iteration Roadmap

Updated: 2026-09-08
Current holistic authority: **v0.3 lineage**

This roadmap governs what each prototype iteration is allowed to focus on. It does not itself promote any prototype.

## Roadmap principle

Each iteration has **one primary product question**. Features that do not help answer that question are deferred.

The app should feel like a breeder's working surface, not a database administration console. New capability should normally appear contextually inside an existing workflow before a new permanent navigation destination is created.

---

## v0.4 — Breeding Program backbone

### Primary question

Can a breeder understand and operate the product around a **breeding program** rather than around tanks?

### Must prove

- Program creation with species/variety/line and a plain-language breeding goal.
- Breeder stock membership.
- Pairing or parent-group setup.
- Reproductive-event creation.
- Offspring cohort creation from that event.
- Program page showing active parents, active reproductive events, offspring/cohorts, and the next relevant work.
- Tanks shown as current locations, not the owner of ancestry.

### Deliberately defer

- advanced species-specific workflows;
- marketplace management;
- capacity forecasting;
- trait/genetics intelligence;
- full analytics dashboards;
- live-food culture management.

### UX budget

No major new bottom-navigation destination unless absolutely required. Prefer Programs as a focused surface accessible from the existing breeder operating model.

### Exit criterion

A breeder can answer: **What am I trying to breed, from which stock, what happened, and what offspring exist now?**

---

## v0.5 — Cohort operations

### Primary question

Can the breeder manage dozens or hundreds of offspring without individual-record overhead?

### Must prove

- count/estimate;
- move;
- split;
- merge with lineage-safe rules;
- life-stage change;
- loss/mortality adjustment;
- photo/observation;
- quick feeding/care event where relevant;
- promotion of selected offspring into individually tracked breeder candidates;
- ancestry preserved through cohort splits and promotion.

### UX focus

Tank-side actions should generally require a few taps and should not open a full edit form unless the breeder asks for details.

### Deliberately defer

- detailed grading systems;
- multi-channel commerce;
- broad reports;
- sophisticated capacity projections.

### Exit criterion

A breeder can maintain a real grow-out population through moves and splits without losing lineage or drowning in forms.

---

## v0.6 — Species-aware breeder programs

### Primary question

Can Draneka adapt to different breeding biology without becoming visually or conceptually fragmented?

### First validation overlays

1. Betta splendens — bubble nest / individual holdbacks.
2. Fancy guppy — livebearer line breeding and sex separation.
3. Medaka — repeated egg collection and hatch batches.
4. Killifish — mop/plant and annual soil-spawner workflows.
5. Neocaridina — colony/selective-line breeding.
6. Apistogramma-type cave brooders — parental care workflow.

### Must prove

- one stable program/navigation model across all six;
- species-specific vocabulary;
- contextual optional fields;
- suggested milestones/tasks;
- breeder override/custom timing;
- explicit distinction between recorded fact and template suggestion;
- correct handling of uncertain/group parentage.

### UX focus

Only the currently relevant species actions are visible. Advanced or uncommon fields remain collapsed.

### Exit criterion

A Betta breeder and a shrimp breeder can both use the product naturally without either seeing a large amount of irrelevant workflow.

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

## v0.8 — Operational scale

### Primary question

Can Draneka reduce missed work as the breeder's fishroom and concurrent cohorts grow?

### Must prove

Breeder Round generated from:

- recurring husbandry;
- lifecycle milestones;
- breeder-created schedules;
- exceptions/risk triggers.

Add only high-value scale aids:

- grow-out capacity pressure;
- expected separation/split pressure;
- critical live-food/culture dependencies where species programs use them;
- overdue incubation/wetting/egg checks;
- QR/location fast-entry exploration if it materially reduces tank-side friction.

### UX focus

Prioritize `what needs attention` over dashboards and charts.

### Exit criterion

A breeder with several active programs can begin the day from Breeder Round and trust that important breeding work is surfaced without manually inspecting every record.

---

## v0.9 — Commerce handoff and evidence

### Primary question

Can successful breeding records become sale-ready inventory and trustworthy provenance without duplicate data entry?

### Must prove

- individual or cohort/batch marked sale-ready;
- explicit public/private fact selection;
- photos and permissible lineage/provenance attached;
- structured handoff to Draneka AquaticFinder;
- spawn/breeding/provenance report generation from existing records;
- commercial status does not rewrite breeding history.

### Explicit boundary

No eBay/Etsy/etc. listing-management UI in Draneka Breeder. Marketplace operations belong to Draneka AquaticFinder.

### Exit criterion

A breeder can finish selection in Breeder and create a commerce-ready handoff without retyping the animal's identity, ancestry, age, traits, quantity, or photos.

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
- extensive sales CRM inside Breeder.

---

# Anti-overwhelm design gates for every iteration

A candidate should fail review if it violates these without strong evidence:

1. **Navigation gate:** new capability should not automatically mean new top-level navigation.
2. **Context gate:** irrelevant species fields should stay hidden.
3. **Speed gate:** frequent tank-side events should be faster than writing the equivalent note manually.
4. **Cohort gate:** offspring remain grouped until individual identity creates value.
5. **Suggestion gate:** lifecycle guidance must never masquerade as a completed event.
6. **Uncertainty gate:** unknown parentage/genetics remain unknown.
7. **Boundary gate:** commerce-channel complexity remains in Draneka AquaticFinder.
8. **Iteration gate:** if a feature does not answer the current iteration's primary question, defer it.
