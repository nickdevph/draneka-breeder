# Draneka Aquarium Breeder — Holistic v0.8 Producer Validation

Date: 2026-09-08
Role: producer validation only — **not independent evidence**
Candidate SHA-256: `9dea5ada178d0814f86d2014a05ece56f8ed2c2be4f79f64ab2f34560b3f4704`
Candidate bytes: `386074`
Drive ID: `1SVaVXVm4DEOXyx8lxxRlMBbj8CUQsPS8`

## Environment

- Chromium: `144.0.7559.96` on Debian GNU/Linux 13
- Playwright: `1.57.0`
- Candidate load: exact local/Drive-round-tripped HTML bytes with `page.set_content()`
- Exact responsive widths: `320`, `390`, `768`, `1440` CSS px

## Static / byte gates

- JavaScript syntax (`node --check`): **PASS**
- Local artifact size: `386074`: **PASS**
- Local SHA-256: `9dea5ada178d0814f86d2014a05ece56f8ed2c2be4f79f64ab2f34560b3f4704`: **PASS**
- Drive metadata size: `386074`: **PASS**
- Fresh Drive raw re-download size: `386074`: **PASS**
- Fresh Drive re-download SHA-256: exact match: **PASS**

## Dynamic Breeder Round

Producer fixture produced `22` active operational attention items across these source classes:

- Critical dependency
- Capacity pressure
- Explicit plan
- Recurring husbandry
- Lifecycle milestone
- Grow-out plan

The dynamic round condensed current at-risk/overdue/due work into `7` context-locked round entries. Every active attention item carried source + reason + state, and round queue entries retained the operational item IDs that explained why the context was present.

Result: **PASS**

Round-skip boundary was exercised. Skipping the current round context left the underlying at-risk culture dependency unchanged rather than falsely resolving it.

Result: **PASS**

## Recurring schedule semantics

### Completion

A due `Feed Copper fry` recurring occurrence was explicitly completed from its schedule sheet.

Before:
- detailed canonical feeding-event count: `1`
- operational check-event count: `0`
- schedule history records for occurrence: `1`
- next due: `2026-09-08`

After:
- detailed feeding-event count remained `1`
- operational check-event count became `1`
- schedule history appended a `Completed` record retaining original due date `2026-09-08`
- next due advanced to `2026-09-09`

The completion event explicitly says it does not substitute for a detailed feeding, biological or cohort-mutation record.

Result: **PASS**

### Deferral

The overdue guppy nursery review was deferred from `2026-09-07` to `2026-09-10`. The history appended a `Deferred` record retaining the original due date. Prior completion history remained unchanged.

Result: **PASS**

### Skip

A due Medaka collection schedule occurrence was explicitly skipped. No event was created; an append-only `Skipped` schedule-history record retained the original `2026-09-08` due date; next due advanced to `2026-09-09`.

Result: **PASS**

### Future schedule edit

The Betta recurring cadence was edited from every 1 day / next `2026-09-08` to every 2 days / next `2026-09-10`. Earlier history serialized identically before and after; a new `Schedule edited` history item was appended.

Result: **PASS**

## Lifecycle prompt vs biological fact

### Annual killifish

The due `Review Rachovii egg-medium development` lifecycle item existed in Breeder Round while simply calculating/rendering attention produced:

- no new wetting attempt;
- no hatch event;
- no offspring cohort.

The prompt was then explicitly closed as `Checked` with breeder note `Reviewed medium; not wetting today`. Hatch count, wetting-event count and cohort count all remained unchanged.

Result: **PASS**

### Medaka

Rendering/calculating the Medaka hatch-review attention did not change the number of explicit Medaka hatch records.

Result: **PASS**

## Capacity semantics

- Tank `R3` has no breeder planning ceiling. It remained `Needs context` with `planningLimit = null`; no capacity was invented.
- The Neocaridina `S1` context used a breeder-entered planning ceiling of `50`; recorded load `42` yielded operational pressure `Due` (0.84 ratio). The UI labels the ceiling as breeder-entered planning context, not a stocking recommendation.

Result: **PASS**

## Grow-out plan vs cohort mutation

The seeded Betta grow-out plan requested a future split of `30` fry to `R2`.

Editing the plan changed none of:

- source cohort tank (`B1`);
- source cohort count (`76`);
- source active state;
- cohort total;
- root/source provenance.

Result: **PASS — plan only**

The canonical split form was then explicitly completed:

- source `76` became historical/inactive;
- child A = `30` at `R2`;
- child B = `46` at `B1`;
- `30 + 46 = 76` exactly;
- both descendants retained root `cb`, source output `b04`, and corresponding canonical source-hatch provenance in emitted split/move events;
- only after the explicit split did the grow-out plan change from `Planned` to `Executed`.

Result: **PASS — explicit mutation authority retained**

## Critical culture dependency

`Artemia culture A` began `At risk / Low`, explicitly linked to the Copper fry feeding context.

A producer-recorded maintenance/status update changed it to `Available / Good`, appended culture history and set its next maintenance date. The canonical detailed feeding-event count did not change.

Result: **PASS — culture availability does not infer feeding**

## v0.7 Pair Builder authority regression

`Atlas · retained F2` began `ready=true`, selectable and Pair-Builder-eligible. With a current `Non-breeding` disposition applied in the producer regression fixture:

- historical `ready=true` remained true;
- `breedingStockSelectable(Atlas)=false`;
- `pairBuilderEligible(Atlas)=false`;
- an established stale Pair Builder selection was normalized away from Atlas.

Result: **PASS**

## Existing provenance sanity

- Atlas/Iris retained the same exact two recorded parents: **PASS**
- canonical Medaka Program remained present with its existing hatch/output records: **PASS**
- canonical Neocaridina Program remained population/group-based: **PASS**
- canonical guppy Program (`p4`, `Poecilia reticulata`) remained present: **PASS**

These are producer sanity checks, not substitutes for the mandated fresh independent v0.7/v0.6/v0.5 regression.

## Responsive/runtime matrix

At exact widths `320`, `390`, `768`, `1440`:

- `window.innerWidth` matched the target exactly;
- document client width matched the target exactly;
- `document.documentElement.scrollWidth <= viewport`;
- `document.body.scrollWidth <= viewport`;
- tested operational sheets/dialogs remained horizontally contained;
- page errors: `0`;
- console errors: `0`.

Dynamic operational home, attention rows and operational-detail sheets were exercised at every width. The semantic non-mutation fixtures (killifish prompt, Medaka prompt, plan-only, unknown capacity, culture-no-feed, explainability) were also rerun on exact loaded bytes at each width.

Result: **PASS**

## Visual sanity

Producer browser inspection was performed at desktop `1440` and mobile `390`. The candidate retained the canonical Draneka hierarchy and small top-level navigation while making operational attention visible within `Today / Breeder Round`. No generic kanban/Gantt/task-management destination was introduced.

Result: **PASS**

## Scope discipline

Producer inspection found no introduction of:

- automatic biological completion;
- automatic culling/move/split/pairing/selection/sale/rehome decisions;
- opaque AI operational authority;
- genotype inference;
- generic project-management/ERP navigation;
- v0.9 sale-ready handoff;
- marketplace listings/channel allocation/pricing/CRM/payment/order/shipping workflow;
- backend/API/schema/database/deployment/production mutation;
- Android/web implementation authority.

Result: **PASS**

## Producer disposition

No producer-known promotion blocker remains in the exact candidate. This result does **not** promote the artifact and must not be treated as independent evidence.

`HOLISTIC_V0_8_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_8_RESPONSIVE_PRODUCER_MATRIX = PASS`

`HOLISTIC_V0_8_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_8_CANONICAL = NO`

`PR_8_MERGE = HOLD`
