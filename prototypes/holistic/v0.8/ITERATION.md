# Draneka Aquarium Breeder — Holistic v0.8 Iteration

Date: 2026-09-08
Status: **DRAFT / PRODUCING / NON-CANONICAL**
Branch: `prototype/v0.8-operational-scale`

## Canonical predecessor

Holistic v0.8 begins from the exact repository-canonical holistic v0.7 authority on `main`.

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`
- Size: `334514 bytes`
- SHA-256: `1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`
- Canonical merge commit: `11f0adba6b821cd5b3c6642d6927ba25930266bb`

v0.7 remains immutable and canonical unless and until an exact v0.8 candidate completes producer validation, fresh independent review, Founder promotion, and merge of the v0.8 iteration PR.

## Primary product question

Can Draneka Breeder help a breeder reliably operate many simultaneous breeding programs without forcing them to manually translate every record, lifecycle state, and recurring husbandry need into a separate task list?

## Founder-locked v0.8 objective

Prove **operational scale** by making Breeder Round a dynamic, evidence-grounded attention surface derived from:

1. explicit breeder schedules;
2. recurring husbandry rules;
3. species/program lifecycle milestones;
4. recorded biological state;
5. overdue or exceptional conditions;
6. capacity pressure and grow-out constraints; and
7. critical live-food/culture dependencies where failure would create an operational miss.

The candidate must preserve v0.7 selection/line-development authority, v0.6 species/provenance semantics, and all uncertainty boundaries.

The system may surface work, pressure, risk, and dependencies. It must not silently claim that husbandry, lifecycle events, spawning, hatch, selection, mortality, or other biological events occurred merely because a schedule became due.

## Must prove

### 1. Dynamic Breeder Round

Breeder Round becomes a current operational queue rather than a static/predefined list.

Each surfaced item must have a visible reason/source, such as:

- explicit breeder schedule;
- recurring husbandry rule;
- species-overlay lifecycle milestone;
- recorded state transition that creates a follow-up;
- overdue item;
- exception/risk;
- capacity pressure; or
- critical dependency.

The breeder must be able to distinguish scheduled work from observed/completed biological facts.

### 2. Explicit schedules and recurring husbandry

A breeder can define or use contextual schedules for recurring work such as feeding, checks, maintenance, water-change/test routines, culture maintenance, or breeder-defined repeated tasks.

Required semantics:

- schedule definition is not completion evidence;
- due/overdue status is derived from the schedule and completion history;
- completing a task creates an operational completion record, not an unrelated biological claim;
- skip/defer/reschedule remains explicit and auditable;
- changing a future schedule does not rewrite past due/completion history.

### 3. Lifecycle milestone attention

Species/program overlays may surface suggested lifecycle attention based on recorded state and elapsed time where appropriate.

Required semantics:

- milestone prompts are recommendations/attention items, not inferred biological events;
- a due hatch check must not create a hatch;
- a sexing/grading window must not invent sex, grade, or selection results;
- a parent-removal prompt must not record removal until the breeder records it;
- killifish wetting/diapause prompts must preserve explicit wetting/hatch authority;
- missing or uncertain dates must reduce precision rather than fabricate a date.

### 4. Exception and overdue handling

Breeder Round must prioritize meaningful exceptions without becoming a generic notification inbox.

At minimum, demonstrate:

- overdue recurring husbandry;
- overdue breeder-defined schedule;
- lifecycle follow-up that has not been recorded;
- dependency at risk;
- capacity pressure requiring breeder attention.

The UI must explain why an item is elevated.

### 5. Capacity pressure

The product may surface simple operational pressure when recorded occupancy/planned grow-out creates a meaningful constraint.

Capacity is an operational planning aid, not a biological fact or an authoritative stocking recommendation.

Required behavior:

- pressure derives from breeder-entered/recorded capacity context and actual cohorts/locations;
- unknown capacity remains unknown rather than assumed;
- the product can show where upcoming cohorts may need grow-out space;
- resolving pressure requires an explicit breeder action/plan;
- no automatic move, cull, sale, rehome, or pairing decision is made.

### 6. Grow-out planning

A breeder can see near-term grow-out needs connected to real cohorts/programs and create an explicit plan.

A grow-out plan may reference:

- target tank/location;
- approximate timing/window;
- cohort/group;
- expected split or move intent;
- breeder notes.

The plan must remain distinct from the eventual operational mutation. Planning a move/split must not perform it.

### 7. Critical live-food/culture dependencies

Where a breeding program depends on a breeder-recorded live-food/culture resource, Breeder Round may surface maintenance or shortage risk.

Required behavior:

- dependency must be explicit or contextually enabled; do not assume every species/program requires a particular food;
- culture maintenance/completion is operational history;
- low/at-risk status is breeder-recorded or derived from explicit thresholds/state, not invented;
- dependency risk may elevate related fry/cohort attention;
- no feeding event is fabricated from culture availability.

### 8. Work-item provenance and history

Every dynamic attention item must remain traceable to its source.

At minimum retain enough information to explain:

- why it exists;
- what Program/cohort/stock/location/resource it concerns;
- whether it is schedule-, lifecycle-, exception-, capacity-, or dependency-derived;
- due/window information when established;
- current state (`Due`, `Overdue`, `Upcoming`, `Deferred`, `Done`, `Skipped`, or equivalent);
- the explicit action/history that closed or changed it.

Historical completion/deferral reasons must not be rewritten by later schedule edits.

## Product rules

1. **Due does not mean done.** A schedule or milestone becoming due never creates a biological or husbandry completion event by itself.
2. **Suggested does not mean observed.** Species overlays may suggest checks/windows but may not infer outcomes.
3. **Plans do not mutate reality.** Capacity/grow-out plans remain separate from move, split, merge, count, mortality, feeding, selection, or reproductive records.
4. **Unknown remains unknown.** Missing capacity, uncertain dates, unknown parentage, unknown genotype, or missing evidence remain visibly uncertain.
5. **Attention must be explainable.** Every elevated item shows why it is in Breeder Round.
6. **Operational state must not rewrite provenance.** Task completion, scheduling, capacity planning, and dependency state cannot alter parentage, source output, hatch, wetting-attempt, or cohort ancestry.
7. **No opaque authority.** Draneka may prioritize recorded operational risks but may not silently decide the breeder's pairing, culling, rehome, sale, or biological outcome.
8. **Anti-overwhelm is mandatory.** Breeder Round should show the smallest useful set of current actions, with progressive disclosure for detail/history.

## Required stress paths

### Betta — concurrent spawn + grow-out pressure

- Use a controlled Betta Program with exact recorded lineage and an active offspring cohort.
- Surface recurring husbandry and a lifecycle-linked selection/grow-out window.
- Introduce recorded capacity context where the cohort creates near-term grow-out pressure.
- Create a grow-out plan without performing a move/split.
- Then explicitly perform the relevant move/split and confirm provenance remains intact.
- Confirm operational planning never changes selection history, parent IDs, or generation evidence.

### Fancy guppy — recurring operational load

- Use multiple active guppy cohorts/parent groups with recurring husbandry.
- Demonstrate Breeder Round combining due work without collapsing uncertain sire/parentage semantics.
- Defer one task and complete another; confirm histories remain separate and auditable.
- Confirm schedule completion does not fabricate reproductive events or lineage certainty.

### Medaka — repeated collection/hatch follow-up

- Use recorded egg collections/hatch-derived cohorts.
- Surface lifecycle follow-ups derived from the real collection/hatch state.
- A hatch-check prompt must not create a hatch.
- Record a hatch explicitly and confirm the operational item closes/changes because of the new recorded fact while hatch provenance remains exact.

### Annual killifish — diapause/wetting authority

- Surface an appropriate wetting/diapause attention item from recorded batch state.
- Becoming due must create no wetting attempt and no hatch.
- Explicit wetting creates the attempt; re-dry remains attached to that attempt; later wetting remains separate.
- Only explicit hatch recording creates offspring, preserving the v0.6/v0.7 provenance rule.

### Neocaridina — population provenance + capacity pressure

- Use a population-derived shrimp cohort/group with no fabricated exact parents.
- Surface capacity/grow-out pressure from breeder-entered context.
- A proposed split/move must remain a plan until explicitly executed.
- Population provenance must remain unchanged throughout.

### Critical culture dependency

- Attach a breeder-recorded live-food/culture dependency to a fry-rearing context.
- Surface culture maintenance/shortage risk.
- Resolve the culture work explicitly.
- Confirm this neither fabricates feeding nor marks fry husbandry complete automatically.

## UX constraints

- Keep existing top-level navigation small; do not create a separate generic task-management app.
- Breeder Round remains the operational home.
- Default presentation should prioritize `Overdue / At risk`, then `Due`, then near-term `Upcoming` work.
- Every item must show concise reason + subject + timing; detail/history expands progressively.
- Common tank-side actions must remain fast at mobile widths.
- Capacity and dependency information should appear only when established/relevant.
- Avoid dense project-management constructs such as kanban boards, Gantt charts, generic resource ERP, or broad analytics dashboards.
- Preserve breeder language and the Program/cohort/stock mental model.

## Explicitly not admitted

This iteration does **not** introduce:

- automatic completion of scheduled or lifecycle events;
- authoritative stocking-density recommendations from unrecorded assumptions;
- automatic culling, move, split, pairing, selection, sale, or rehome decisions;
- opaque AI operational authority;
- generic project/task-management features unrelated to breeding operations;
- v0.9 sale-ready handoff workflow;
- marketplace listings, channel allocation, pricing, CRM, payment, order, or shipping workflow;
- genotype prediction from phenotype;
- new backend/API/schema/database/deployment/production authority;
- Android or web implementation authority.

## Regression authority

The exact v0.8 candidate must preserve all canonical behavior that remains applicable, including:

- v0.7 breeding goals, evaluation evidence, selection-session history, holdback/disposition authority, generation precision, Program isolation, phenotype/genotype boundary, and Pair Builder eligibility/relatedness semantics;
- v0.6 species overlays, Betta controlled ancestry, guppy uncertainty, Medaka output/hatch provenance, Neocaridina population provenance, annual killifish wetting/re-dry/hatch authority, and mop/plant collection behavior;
- v0.5 count revision vs mortality, move identity, split quantity/provenance conservation, merge double-count protection, life-stage update, and feeding semantics.

## Validation gates

The candidate is not promotion-eligible until all of the following are independently exercised on the exact immutable candidate bytes:

- exact canonical v0.7 predecessor binding;
- dynamic Breeder Round source/reason behavior;
- recurring schedule due/overdue/completion/defer/skip semantics;
- schedule-edit history preservation;
- lifecycle prompt vs biological-event boundary;
- capacity unknown/known behavior;
- grow-out plan vs real move/split boundary;
- critical culture dependency behavior;
- Betta, guppy, Medaka, killifish, and Neocaridina stress paths above;
- v0.7 selection/line-development regression;
- v0.6 species/provenance regression;
- v0.5 cohort-operation regression;
- responsive/runtime matrix at `320 / 390 / 768 / 1440`;
- zero page/console errors in the mandated runtime matrix;
- no v0.9 commerce or implementation-authority leakage.

## Exit criterion

A breeder running multiple simultaneous programs can open Breeder Round and answer:

**What needs my attention now, why is it here, what is at risk next, and what action do I actually need to record?**

while Draneka keeps schedules, suggestions, plans, operational completions, and biological facts distinct.

`HOLISTIC_V0_8_ITERATION_STARTED = YES`

`HOLISTIC_V0_8_CANONICAL_PREDECESSOR = V0_7`

`HOLISTIC_V0_8_CANONICAL = NO`
