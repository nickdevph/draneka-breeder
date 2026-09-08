# Decision 0003 — Breeder scope, commerce boundary, and prototype iteration strategy

Date: 2026-09-08
Status: FOUNDER-LOCKED PRODUCT DIRECTION

## Decision

Draneka Aquarium Breeder remains a breeder-first operating product. It must optimize the work of running breeding programs rather than becoming a generic aquarium journal, inventory ERP, or marketplace manager.

The canonical breeding lifecycle remains compatible with the v0.3 lineage authority but is broadened into the operating backbone:

`Breeding Program -> Breeder Stock -> Pairing / Parent Group -> Reproductive Event -> Cohort -> Grow-out / Split -> Selection -> Holdback / Disposition -> Next Generation or Commerce Handoff`

Tanks are locations and environmental context. They are not the primary owner of the breeding lifecycle.

## Commerce boundary

The commerce product is **Draneka AquaticFinder**.

Breeder may prepare livestock for commerce and hand off structured sale-ready inventory, provenance, photos, lineage-safe public facts, quantities, grades, age/stage, sex when known, and breeder-defined sale notes. Breeder must not grow a second marketplace-management UI.

Draneka AquaticFinder is expected to own cross-marketplace listing operations such as:

- listing drafts and reusable listing templates;
- marketplace eligibility/policy checks;
- marketplace-specific title/category/attribute adaptation;
- publish/update/pause/end actions where the marketplace API permits them;
- quantity and availability synchronization;
- price differences by marketplace;
- listing status and external IDs;
- order/reservation reconciliation;
- channel-specific compliance and shipping rules;
- performance analytics across channels.

The marketplace layer must be policy-aware. It must never assume that one livestock record can be published to every channel. For example, eBay currently allows tropical fish subject to its live-animal policy, permits, and safe overnight shipping requirements, while Etsy's current policy prohibits live animals. Marketplace eligibility therefore belongs to Draneka AquaticFinder and is evaluated per item type, jurisdiction, destination, and current marketplace policy.

## Breeder-to-commerce handoff principle

Breeder owns **what the animal/cohort is and how it was produced**.

Draneka AquaticFinder owns **where, how, and at what commercial terms it is listed and sold**.

A later integration contract should allow a breeder to mark an individual or batch as `sale-ready`, select what facts are public, then hand it to Draneka AquaticFinder without re-entering lineage, phenotype, photos, age, quantity, or provenance.

Commercial state must not rewrite breeding history.

## Prototype iteration strategy

Prototype revisions must be bounded. Each iteration should answer one major product question and should avoid adding unrelated navigation or dashboards.

The current holistic prototype authority remains **v0.3 lineage**. This decision does not promote a new prototype and does not alter current implementation authority.

Planned prototype focus after v0.3:

1. **v0.4 — Breeding Program backbone**
   - Prove Program -> Pairing/Parent Group -> Reproductive Event -> Cohort as the main mental model.
   - Keep Breeder Round as the operational home.
   - Do not add advanced analytics, marketplace management, or deep genetics.

2. **v0.5 — Cohort operations**
   - Prove fast count, move, split, merge, stage-change, loss, photo, and observation flows.
   - Prove promotion of selected cohort members into individually tracked breeder candidates while preserving ancestry.
   - Optimize tank-side speed and progressive disclosure.

3. **v0.6 — Species-aware breeder programs**
   - Introduce the species-template/overlay system.
   - First validation set: Betta splendens, fancy guppy/livebearer, medaka, killifish, Neocaridina shrimp, and Apistogramma-type cave brooders.
   - Species overlays modify milestones, suggested tasks, terminology, and optional fields without changing the core navigation.

4. **v0.7 — Selection and line development**
   - Add breeding goals, time-stamped trait evaluations, grading/selection events, holdbacks, line comparison, and outcome review.
   - Keep phenotype separate from claimed genotype.
   - Do not expose opaque AI pairing authority.

5. **v0.8 — Operational scale**
   - Make Breeder Round fully dynamic from recurring husbandry, lifecycle milestones, explicit schedules, and exceptions.
   - Add capacity pressure, grow-out planning, and critical live-food/culture dependencies only where they reduce operational misses.

6. **v0.9 — Commerce handoff and evidence**
   - Mark individuals/batches sale-ready and hand them to Draneka AquaticFinder.
   - Generate breeder-facing/public provenance and spawn reports from already-recorded facts.
   - Do not embed eBay/Etsy/etc. management inside Breeder.

A future v1.0 candidate should be a simplification/qualification pass rather than another feature sweep.

## Anti-overwhelm rules

1. Navigation should remain small and breeder-language-first.
2. Advanced fields appear only when the species/program or breeder enables them.
3. Suggested milestones are recommendations, never false records of events.
4. The normal tank-side action should take seconds, not require opening a complete breeding record.
5. Cohorts remain the default for offspring; individual identity is created when it becomes useful.
6. Species overlays reuse one core data model rather than creating isolated mini-apps.
7. Intelligence should summarize and surface risk/opportunity from recorded facts; it must not invent parentage, genotype, event completion, or breeding outcomes.
8. Commerce complexity stays outside Breeder.

## Research direction locked

Species-specific breeder programs require deeper evidence before implementation. Research should distinguish:

- reproductive archetype;
- species-specific lifecycle milestones;
- parent unit (pair, trio, group, colony, uncertain sire/dam);
- egg/birth/larval handling;
- cohort grouping and split points;
- sexing/grading/selection windows;
- environmental variables breeders actually record;
- food/culture dependencies;
- parent-removal or parental-care events;
- incubation/diapause requirements;
- sell/rehome readiness;
- edge cases and breeder-defined variation.

The product implementation should be **core + overlay**, not one rigid universal checklist and not one hard-coded workflow per species.

## Non-effects

This decision does not:

- promote a prototype newer than v0.3;
- admit web or Android production implementation;
- alter the existing Journal implementation authority;
- authorize production schema/API/deployment changes;
- authorize marketplace API integration yet.
