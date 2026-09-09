# Draneka Aquarium Breeder — Holistic v0.9 True Independent Review

Date: 2026-09-09
Reviewer role: fresh independent holistic v0.9 reviewer
Disposition: **CHANGES_REQUIRED**

This receipt records a review-only result. It does not modify prototype bytes, promotion state, canonical state, product source, backend/API/schema/database, deployment, Android/web implementation, or release state.

## Independence

This review did not inherit PASS/FAIL/correction/promotion conclusions from producer validation, prior same-context review, PR prose, prior receipts, merge messages, Founder prose, or earlier assistant conclusions. Prior repository material was used only to bind historical/repository identity and understand required test definitions.

## Exact v0.9 binding

Review target:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1OQqLK4aovt4RAfAdKxFnn9n-VB-nUaEX`
- MIME: `text/html`
- Exact bytes independently measured from the raw Drive object: `437100`
- SHA-256 independently calculated from the raw Drive object: `21736560a33f7ab7a42b46c7691b690b9fb7336638c8fec616da30af345d4327`

Result: `HOLISTIC_V0_9_EXACT_BINDING = PASS`

## Canonical predecessor binding for this exercise

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1Lrdd1OX0I297hS3fBHXOSk6lmAwws3y9`
- MIME: `text/html`
- Exact bytes independently measured: `391223`
- SHA-256 independently calculated: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`
- Historical v0.8 merge inspected: `600d992e20d48f3520311d2fdcb087514d68fc95`

Result: predecessor binding PASS.

## Repository state inspected

Repository: `nickdevph/draneka-breeder`

- Current `main` observed at review time: `80ce9259966ca2600a0c35f4633bbec4016329f3`
- Historical PR #9 observed merged; its base binds to the v0.8 merge above.
- The v0.9 HTML bytes are not stored as an HTML blob in the repository tree; the exact byte authority for this review was therefore the independently downloaded Drive object.
- `prototypes/holistic/v0.9/BOUNDED-CORRECTION-RECEIPT.md` identifies the same bounded-correction filename, Drive ID, byte count, and SHA-256. That receipt was not used as proof of the binding; the raw Drive object was independently measured and hashed.
- `prototypes/holistic/v0.9/CANDIDATE.md` still describes the earlier failed, pre-correction v0.9 candidate. This is governance-history metadata, not the byte authority reviewed here.

The existing merge was treated only as governance history, never as qualification evidence.

## Browser/runtime method

The SHA-bound candidate was exercised in real headless Chromium through Playwright. Direct `file://`/localhost navigation is administratively blocked in the execution environment, so the exact UTF-8 document from the SHA-bound raw file was loaded into Chromium with `page.set_content`. The candidate bytes were not edited; all review mutations were transient demo-state interactions inside the browser.

Required viewport widths exercised exactly:

- 320 CSS px
- 390 CSS px
- 768 CSS px
- 1440 CSS px

At every width, 30 representative critical pages/dialogs were exercised, including Today/Breeder Round context, Program, individual/cohort commerce, valid egg-output commerce, blocked materialized-output commerce, historical zero-source blocking, sale-ready privacy, structured handoff, provenance report, reconciliation, Sale/rehome selection, Pair Builder, recurring schedule, lifecycle, capacity, grow-out, culture, count/mortality/move/split/merge/stage/feed forms, annual-killifish wetting, Medaka hatch flow, and More/contextual commerce.

Observed at all four widths:

- exact `window.innerWidth` applied;
- no document/body horizontal overflow;
- no relevant sheet/dialog horizontal overflow;
- zero page errors;
- zero console errors.

Result: `HOLISTIC_V0_9_RESPONSIVE_MATRIX = PASS`.

## Mandatory prior v0.9 defect reproductions

### V09-IR-001 — zero/historical source quantity

Fresh reproduction:

1. Started Betta cohort `cb` at 76.
2. Performed an explicit rendered split of `76 = 30 + 46`, placing the 30-child into R2.
3. Confirmed original `cb` became inactive/historical with current quantity `0`.
4. Attempted sale-ready on original `cb`.
5. Injected a stale commerce profile into transient browser state and attempted a new handoff from original `cb`.

Observed:

- sale-ready was blocked with `No sale-ready quantity is owned by this source`;
- stale profile could not bypass final handoff guard;
- no positive quantity was fabricated;
- provenance report remained available;
- the matching planned split moved to `Executed` only because the exact split occurred.

Result: `V09_IR_001 = CLOSED`.

### V09-IR-002 — duplicate materialized-source quantity ownership

Fresh Neocaridina reproduction:

- descendant cohort `cs` owned current quantity `42`;
- exact parents remained absent;
- cohort provenance remained `Colony provenance only; parents unknown`;
- a cohort handoff of proposed quantity `10` correctly snapshotted biological quantity `42`;
- reproductive output `s01` was blocked from sale-ready/commerce quantity ownership because its recruit total had materialized into offspring records.

Fresh Medaka contrasting case:

- `m02` = 24 recorded eggs;
- total observed hatches = 9;
- remaining distinct egg quantity = 15;
- `m02` was allowed as a distinct remaining-output owner of exactly 15;
- a proposed handoff of 8 snapshotted 15 without changing the 5- and 4-animal descendant cohorts.

Result: `V09_IR_002 = CLOSED`.

### V09-IR-003 — Sale / rehome contextual handoff

Fresh reproduction:

1. Recorded Atlas as `Sale / rehome` through rendered Selection session UI.
2. Historical `ready=true` remained.
3. Current breeding-stock eligibility became false.
4. Pair Builder eligibility became false.
5. Selection workspace rendered `Sale / rehome → commerce-ready handoff`.
6. Forced stale Pair Builder requested parents (`Atlas`/`Iris`), then opened Pair Builder.
7. Pair Builder normalized away from Atlas; Atlas did not render as an active pairing parent.
8. Marked Atlas sale-ready.
9. Pair Builder eligibility remained false.

Result: `V09_IR_003 = CLOSED`.

## G1 — Sale-ready versus biological state

Opening and cancelling sale-ready was non-mutating. Marking sale-ready changed only commerce profile state. Creating a handoff changed only commerce handoff state. Across these operations the reviewed biological snapshot remained unchanged: cohort quantities/state, stock ancestry/readiness/disposition, spawn/hatch provenance, task/lifecycle state, goal/evaluation/selection counts, and biological event ledger.

Result: PASS.

## G2 — Public/private information control

### BLOCKER: V09-TIR-001 — unselected media caption leaks into public handoff/report

Classification: **BLOCKER — private-data exposure**

Safely bounded to v0.9: **YES**. The defect is in the v0.9 commerce/public-evidence projection. No evidence was found of a v0.8/v0.7/v0.6/v0.5 biological-authority regression caused by this defect.

Fresh exact reproduction through rendered UI:

1. Started from active Betta cohort `cb` at 76.
2. Added two source-linked photos through the normal photo UI:
   - `PUBLIC SELECTED PHOTO CAPTION`
   - `PRIVATE UNSELECTED PHOTO CAPTION`
3. Opened `Mark sale-ready / choose public facts`.
4. Enabled public facts: `identity`, `provenance`, `quantity`, and `photos` (`Selected photo evidence`).
5. In the separate media chooser, selected only the first photo and explicitly unchecked the second.
6. Added an internal commerce-preparation note and saved sale-ready.
7. Confirmed the commerce profile contained only the selected media ID.
8. Opened AquaticFinder handoff and proposed quantity 10.
9. Confirmed the handoff `mediaIds` contained only the selected media ID.
10. Inspected the rendered public handoff preview, saved the handoff, and generated the breeding/provenance report.

Expected:

- the unchecked photo and all of its public-facing metadata must remain private;
- `Selected photo evidence` must be derived only from explicitly selected media IDs;
- handoff public facts, handoff preview, and public provenance report must not reveal any caption/metadata belonging to unselected media.

Observed:

- `profile.mediaIds = [selected-photo-id]` — correct;
- `handoff.mediaIds = [selected-photo-id]` — correct;
- but `handoff.publicFacts.photos` contained **both** captions:

  `PUBLIC SELECTED PHOTO CAPTION · PRIVATE UNSELECTED PHOTO CAPTION`

- the public handoff preview rendered the private/unselected caption;
- the breeding/provenance report rendered the private/unselected caption;
- internal preparation/handoff notes did remain private.

The defect is caused by the public `photos` fact being derived from all source-linked media rather than the explicit selected-media permission set. Thus the media ID filter is correct while the parallel public-fact projection leaks metadata from media the breeder explicitly kept private.

Required correction boundary: the public photo-evidence fact/preview/report must be projected only from explicitly permitted media, with no caption/metadata from unchecked media. The correction should remain entirely within the v0.9 public-evidence/handoff/report layer.

Result: `HOLISTIC_V0_9_PUBLIC_PRIVATE_EVIDENCE = FAIL_BLOCKER`.

## G3 — Provenance integrity

Independently exercised:

- Betta Atlas retained exact recorded parents `Ember + Lyra`.
- Fancy guppy retained `Mother recorded; sire unknown`.
- Medaka `cm02a` and `cm02b` retained the same output `m02` but distinct hatch IDs `mh02a` and `mh02b`; `m02` remaining eggs stayed 15.
- Neocaridina retained colony/population provenance with no exact parents.
- Annual killifish was exercised as explicit wetting attempt 1 → explicit re-dry → explicit wetting attempt 2 → explicit observed hatch of 5 linked to wetting attempt 2. Before the hatch record, wetting/re-dry state produced no hatch. The hatch retained its selected wetting-attempt provenance.
- Mop/plant workflow recorded a 12-egg estimated collection and produced no hatch record or wetting attempt.

No commerce operation fabricated parentage, hatch, or genotype in these paths.

Result: PASS.

## G4 — Structured AquaticFinder handoff

Actual handoffs contained the expected schema/version, stable source identity, source type, Program ID, biological quantity snapshot, separate proposed commerce quantity, selected public fields/facts, selected media IDs, provenance snapshot, handoff identity/history, allocation/outcome ledger fields, and internal handoff note.

Handoff creation did not create a marketplace listing or biological event and did not change count, ancestry, hatch, readiness, lifecycle or selection authority.

Result: PASS apart from the G2 privacy projection blocker above.

## G5 — Provenance report

Reports were generated from existing Breeder records without retyping identity, timing/provenance, quantity or evidence fields. Report boundary copy explicitly distinguishes recorded facts, breeder assessment, selection decision and unknown evidence, and disclaims DNA/genotype inference.

The report shares the same G2 blocker: when the public `photos` fact is enabled, it can reveal captions from unselected source media.

Result: FAIL due to `V09-TIR-001`.

## G6 — Quantity ownership authority

Grouped-source test:

- Breeder biological quantity: 76
- proposed commerce quantity: 20
- downstream allocations/outcomes exercised separately
- statuses exercised: Allocated, Partially sold, Sold, Returned / released, Closed
- Breeder biological quantity stayed 76 through all commerce reconciliations.

After an explicit biological split made the original source historical at quantity 0, reconciliation against the already-created handoff continued as commerce history without changing the now-historical biological source.

Additional quantity-owner paths:

- active cohort: allowed;
- historical zero cohort: blocked;
- materialized Neocaridina output `s01`: blocked;
- genuinely remaining Medaka egg output `m02`: allowed at exactly 15 remaining eggs.

Result: PASS.

## G7 — Commerce reconciliation

Actual reconciliations for Allocated, Partially sold, Sold, Returned / released and Closed remained linked to the same handoff and updated only commerce ledger/history. Biological quantity, ancestry, hatch provenance and selection evidence were unchanged. Reconciliation remained possible after the source later became historical through a real biological split.

Result: PASS.

## G8 — Selection and Pair Builder authority

Fresh disposition results for Atlas:

- `Non-breeding`: historical readiness stayed true; breeding-stock selectable false; Pair Builder eligible false.
- `Retire`: readiness stayed true; selectable false; Pair Builder false.
- `Sale / rehome`: readiness stayed true; selectable false; Pair Builder false; contextual commerce entry rendered.
- `Holdback`: readiness stayed true; selectable true; Pair Builder true (readiness-neutral behavior preserved).

Stale requested-parent recovery normalized away from a newly ineligible Atlas and relationship rendering did not resurrect it. Adding sale-ready commerce state did not restore eligibility.

Result: PASS.

## Complete v0.8 regression

Independently exercised operational attention, recurrence, completion, deferral, skip, future cadence edit, due-versus-done semantics, schedule completion versus detailed husbandry, lifecycle suggestion versus biological fact, capacity unknown/known behavior, grow-out planning, culture dependency, explainability and attention prioritization.

Former defects:

- `V08-IR-001`: count revision, mortality, feeding and stage-change records each left the planned split `Planned`; only the exact explicit 30-to-R2 split set it `Executed` and conserved 76 as 30+46.
- `V08-IR-002`: cancelling Rachovii wetting then recording unrelated Betta feeding left the lifecycle prompt unresolved with zero wetting/hatch records; a matching wetting record alone resolved the intended prompt and still created no hatch.

Result: `HOLISTIC_V0_9_V0_8_REGRESSION = PASS`.

## Complete v0.7 regression

Independently exercised:

- append-only goal update (2 prior goal records → 3 after update);
- old evaluation and old selection goal snapshots remained unchanged;
- a new selection session captured the new current goal snapshot;
- phenotype evidence remained observational and genotype remained not established;
- missing evidence stayed explicit (`Not enough evidence`, zero evidence IDs) rather than becoming a fabricated score;
- negative disposition authority and Holdback neutrality;
- Pair Builder stale-parent exclusion;
- Atlas/Iris full-sibling detection;
- mixed `F1 × F2` returned `Generation not established · recorded parents F1 × F2`;
- Program-scoped merge candidates remained isolated to the same Program;
- population-derived Neocaridina provenance retained no exact parents.

Result: `HOLISTIC_V0_9_V0_7_REGRESSION = PASS`.

## Complete v0.6 regression

Independently exercised controlled Betta ancestry, guppy sire uncertainty, Medaka output/hatch identity, Neocaridina population provenance, annual killifish wet → re-dry → later wet → explicit hatch, and mop/plant collection without inferred hatch.

Result: `HOLISTIC_V0_9_V0_6_REGRESSION = PASS`.

## Complete v0.5 regression

Independently exercised:

- count revision distinct from mortality;
- mortality loss ledger;
- whole-group move retains identity/count/provenance;
- split conserves quantity and historical source semantics;
- merge conserves quantity and retains multiple hatch/source provenance without double counting;
- life-stage change preserves count/provenance;
- detailed feeding creates an explicit feeding event and leaves quantity unchanged.

Commerce reconciliation did not masquerade as any of these biological operations.

Result: `HOLISTIC_V0_9_V0_5_REGRESSION = PASS`.

## Scope discipline and anti-overwhelm

Rendered bottom navigation remained exactly:

`Today / Programs / Log / Grow-out / More`

No dedicated commerce bottom-nav destination was added. Commerce appeared contextually from source/selection/More surfaces. The rendered commerce screen explicitly assigns listing/channel/payment/order/shipping execution to AquaticFinder and states that those workflows are not implemented in Breeder.

No marketplace management, pricing optimizer, sales CRM, payment/order/shipping workflow, public marketplace, ERP, genotype inference, automatic biological decision, backend/API/schema/database/deployment mutation, Android/web implementation authority, or v1.0 expansion was exercised or found.

Result:

- `HOLISTIC_V0_9_SCOPE_DISCIPLINE = PASS`
- `HOLISTIC_V0_9_ANTI_OVERWHELM = PASS`

## Non-blocking metadata note

The HTML document `<title>` still says `Holistic Prototype v0.8 · Operational Scale` and the meta description still refers to a v0.7 second bounded-correction candidate. Rendered in-app version/scope text is v0.9. This is a non-authority metadata hygiene issue and was not treated as a promotion blocker.

## Final disposition

`CHANGES_REQUIRED`

Promotion blocker:

- `V09-TIR-001` — **BLOCKER** — unselected media caption leaks through the public `Selected photo evidence` fact into the handoff public snapshot/preview and provenance report.

The primary v0.9 product/authority model is not fundamentally invalid. The blocker is safely bounded to the v0.9 public-evidence projection. Therefore the correct disposition is `CHANGES_REQUIRED`, not `FAIL`.

Status summary:

```text
V09_IR_001 = CLOSED
V09_IR_002 = CLOSED
V09_IR_003 = CLOSED

HOLISTIC_V0_9_EXACT_BINDING = PASS
HOLISTIC_V0_9_SALE_READY_BOUNDARY = PASS
HOLISTIC_V0_9_PUBLIC_PRIVATE_EVIDENCE = FAIL_BLOCKER_V09_TIR_001
HOLISTIC_V0_9_PROVENANCE_REUSE = FAIL_DUE_TO_PUBLIC_MEDIA_METADATA_LEAK
HOLISTIC_V0_9_AQUATICFINDER_HANDOFF = FAIL_DUE_TO_PUBLIC_MEDIA_METADATA_LEAK
HOLISTIC_V0_9_QUANTITY_OWNERSHIP_BOUNDARY = PASS
HOLISTIC_V0_9_COMMERCE_RECONCILIATION = PASS
HOLISTIC_V0_9_SELECTION_PAIRBUILDER_BOUNDARY = PASS

HOLISTIC_V0_9_V0_8_REGRESSION = PASS
HOLISTIC_V0_9_V0_7_REGRESSION = PASS
HOLISTIC_V0_9_V0_6_REGRESSION = PASS
HOLISTIC_V0_9_V0_5_REGRESSION = PASS

HOLISTIC_V0_9_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_9_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_9_ANTI_OVERWHELM = PASS

HOLISTIC_V0_9_TRUE_INDEPENDENT_REVIEW = CHANGES_REQUIRED
HOLISTIC_V0_9_PROMOTION_ELIGIBLE = NO
```

The existing v0.9 merge is not validated by this review.

```text
EXISTING_V0_9_CANONICALIZATION_GOVERNANCE_STATUS =
REQUIRES_FOUNDER_DISPOSITION_AFTER_TRUE_INDEPENDENT_REVIEW
```
