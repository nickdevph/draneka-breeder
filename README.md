# Draneka Aquarium Breeder

Durable product/design repository for **Draneka Aquarium Breeder**.

This repository preserves prototype authority, product/design evidence, qualification receipts, and future implementation work for the Breeder product.

## Identity boundary

- User-facing product: **Draneka Aquarium Breeder**
- Existing technical/internal ecosystem: **AquaticFinder**
- Existing AquaticFinder backend/internal identifiers are not renamed by this repository.

## Current prototype authorities

| Surface | Current authority | Status |
| --- | --- | --- |
| Holistic product/design | **v1.0 simplify / qualify bounded-correction authority** | **Founder-promoted and repository-canonical after merged PR #11** |
| Holistic predecessor stack | v0.4 through v0.9 | Historical product/design authorities retained immutably for lineage, provenance and regression evidence |
| Android adaptation | Android v0.1, derived from holistic v0.2 | Historical Android design evidence; **not v1.0 parity** |

### Exact canonical v1.0 binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html`
- SHA-256: `4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d`
- Size: `458038 bytes`
- Durable Drive object: `1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0`
- Authority record: `prototypes/holistic/v1.0/PROMOTION.md`
- Independent review: `reviews/holistic-v1.0-bounded-correction-independent-rereview-2026-09-09.md`
- Founder decision: `prototypes/holistic/v1.0/PROMOTION.md`

Terminal authority state:

`DRANEKA_BREEDER_CANONICAL_HOLISTIC_PRODUCT_DESIGN_AUTHORITY = V1.0`

`DRANEKA_BREEDER_HOLISTIC_V1_0_BOUNDED_CORRECTION_INDEPENDENT_REVIEW = PASS`

`DRANEKA_BREEDER_HOLISTIC_V1_0_FOUNDER_PROMOTION = APPROVED`

`DRANEKA_BREEDER_HOLISTIC_V1_0_REPOSITORY_CANONICALIZATION = PR_11_MERGED / YES`

## Prototype iteration workflow

Beginning with holistic v0.5, every holistic version uses **one iteration branch and one pull request**.

- `main` = canonical or historical authority only.
- Active holistic iteration work stays on `prototype/vX.Y-*` until it passes review, receives founder promotion, and is merged.
- Bounded corrections discovered during review remain in the **same version PR** and create new immutable candidate bindings rather than mutating a reviewed artifact.
- A new holistic version receives a new branch and a new PR.
- For v0.5 and later, **merge to `main` after founder promotion is the repository canonicalization event**.

The exact artifact SHA-256 remains the byte-level product/design payload authority. GitHub `main` records which byte-bound artifact currently holds canonical authority.

Governing documents:

- `decisions/0006-prototype-iteration-pr-canonicalization-model.md`
- `PROTOTYPE-ITERATION-WORKFLOW.md`

v0.4 is the transition exception because it was already independently reviewed and founder-promoted before this model was adopted; no synthetic retroactive PR is required.

## Canonical product rules inherited from the v0.3-v0.9 stack and qualified in v1.0

Breeder remains a breeder-first product with a required web application direction and a dedicated Android client direction. v1.0 preserves the qualified predecessor lineage loop while generalizing the operating model so pair/spawn semantics are not forced onto every breeder workflow.

Core lineage/provenance rules:

- ancestry is derived from recorded reproductive evidence rather than manually asserted;
- exact parents remain exact only where recorded evidence supports them;
- incomplete, group, population, or unknown ancestry remains explicitly incomplete;
- offspring groups preserve reproductive source and source-hatch provenance through downstream operations;
- splits preserve ancestry/provenance and do not create a new generation;
- tanks are locations/environmental context, not lineage owners;
- selected/promoted breeders inherit the evidence actually known about their origin;
- phenotype does not imply genotype;
- only a reproductive event can advance ancestry/generation semantics.

v1.0 additionally locks:

- Breeding Program is lightweight durable context, not mandatory ceremony before breeder-native actions;
- event-first Program creation is atomic with the initiating biological record;
- Medaka may have multiple independent egg batches and repeated partial hatches from one source batch;
- hatch source selection is explicit when multiple egg batches are open;
- Neocaridina and other population-derived stock retain source-population provenance without fabricated sire/dam or forced Pair Builder history;
- suggestion, scheduled action, completed action, observation, and derived state remain distinct;
- routine working surfaces use breeder-native language and preserve the anti-overwhelm information budget.

## Current durable product research and roadmap

- Founder scope/commerce/iteration decision: `decisions/0003-breeder-scope-commerce-boundary-and-iteration-strategy.md`
- Independent-review research correction decision: `decisions/0004-accept-independent-research-review-corrections.md`
- v0.4 promotion decision: `decisions/0005-promote-holistic-v0.4.md`
- Prototype iteration PR model: `decisions/0006-prototype-iteration-pr-canonicalization-model.md`
- Breeder-needs + species-program research: `research/2026-09-08-breeder-needs-and-species-programs.md`
- Bounded prototype roadmap: `roadmap/PROTOTYPE-ITERATION-ROADMAP.md`
- Draneka Breeder -> Draneka AquaticFinder commerce boundary: `integrations/DRANEKA-AQUATICFINDER-COMMERCE-HANDOFF.md`

Planned sequence from the current authority:

`v1.0 canonical`

`-> v0.5 Cohort / egg-batch / population operations`

`-> v0.6 Species-aware overlays`

`-> v0.7 Selection / line development`

`-> v0.8 Dynamic Breeder Round / operational attention`

`-> v0.9 Commerce handoff / evidence`

`-> implementation planning and separate admission`

## v0.5 successor envelope

The authorized v0.5 prototype asks one primary question:

**Can the breeder manage dozens or hundreds of offspring, eggs, or recruits without individual-record overhead or ancestry loss?**

It may prove count/estimate with uncertainty, move, split, lineage-safe merge, life-stage change, loss/mortality adjustment, photo/observation, quick care events, promotion of selected offspring, pre-hatch egg-batch -> downstream group, multiple hatch observations from one egg batch, partial hatch, and population recruitment where exact cohort assignment is unavailable.

A merge of offspring groups must preserve all relevant source provenance or be rejected as ancestry-destructive.

Detailed grading systems, multi-channel commerce, broad reports, sophisticated capacity projection, and full species-overlay UI remain deferred.

## Product / commerce boundary

The product must explicitly distinguish:

`Suggestion -> Scheduled action -> Completed action -> Observation -> Derived state`

A completed check or expected lifecycle milestone must never create a biological fact without evidence.

Commerce-channel operations are owned by **Draneka AquaticFinder**, not Breeder. Breeder owns biological identity/count/provenance and sale-ready intent. AquaticFinder owns commercial allocation, marketplace/channel quantities, listings, reservations/orders, and policy/compliance state. Accepted commercial outcomes may flow back without rewriting breeding history.

## Authority rules

1. Reviewed/promoted prototype versions are immutable; revisions use new version numbers.
2. A newer holistic prototype does not silently amend an implementation cycle.
3. Holistic product semantics are separate from client-specific Android/web adaptation details.
4. Existing Android evidence cannot claim parity with holistic v1.0 until convergence is explicitly performed and reviewed.
5. Journal and Breeder may share account, tank, livestock, water, media, and event identity concepts; duplicate domain events should be avoided.
6. Production backend/API/schema/database/deployment changes require a separate implementation-admission cycle.
7. Durable research/roadmap documents inform future prototypes but do not themselves promote prototype authority.
8. Successor prototypes must preserve the evidence, uncertainty, lineage/provenance, tank-location, fact/action, and anti-overwhelm guarantees of the canonical predecessor unless a separate founder decision explicitly changes them.
9. Beginning with v0.5, holistic iteration work must remain off `main` until the exact reviewed artifact is founder-promoted and the version PR is merged.
10. One holistic version uses one branch and one PR; bounded review corrections stay in that PR.

## Current implementation state

- Breeder web production implementation: **not admitted by v1.0 promotion**
- Breeder Android source implementation: **not admitted by v1.0 promotion**
- Existing Journal Android implementation authority: **unchanged**

The prototype repository is product/design authority and provenance, not automatic production implementation authority.
