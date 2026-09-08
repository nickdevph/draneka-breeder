# Founder Decision 0006 — Prototype Iteration PR Canonicalization Model

Date: 2026-09-08
Status: **APPROVED / GOVERNING**

## Decision

Beginning with holistic v0.5, every holistic prototype iteration uses one dedicated branch and one dedicated pull request.

`main` represents canonical and historical authority only. Prototype work that is still being produced, corrected, reviewed, or awaiting founder promotion must remain off `main`.

## Canonicalization rule

For holistic prototype iterations v0.5 and later:

`iteration branch + PR -> candidate(s) -> validation -> independent review -> bounded corrections if required -> founder promotion -> merge to main -> canonical`

A founder promotion decision by itself makes the exact artifact eligible to become canonical, but the holistic version is not repository-canonical until the corresponding iteration PR is merged to `main`.

The exact byte-bound artifact SHA-256 remains the product/design payload authority. GitHub `main` records which exact artifact currently holds canonical authority.

## Unit of change

One holistic version equals:

- one iteration branch;
- one pull request;
- potentially several immutable candidate artifacts / commits;
- potentially several review/correction receipts;
- one final founder promotion decision;
- one merge that canonicalizes the iteration.

Small bounded corrections discovered during review remain in the same version PR. Do not create a new PR for every correction.

A new holistic version, such as v0.5 -> v0.6, receives a new branch and new PR.

## Branch naming

Preferred form:

`prototype/vX.Y-<bounded-scope-slug>`

Example:

`prototype/v0.5-cohort-egg-batch-population-operations`

## PR states

The iteration PR should normally begin as a draft.

Recommended lifecycle:

1. **DRAFT / PRODUCING** — iteration work and candidate production in progress.
2. **READY_FOR_INDEPENDENT_REVIEW** — exact candidate is byte-bound; producer validation complete.
3. **CHANGES_REQUIRED** — independent review requires bounded correction; remain in same PR.
4. **PROMOTION_ELIGIBLE** — exact corrected candidate independently passes.
5. **FOUNDER_PROMOTED / READY_TO_MERGE** — founder promotes the exact reviewed artifact.
6. **MERGED / CANONICAL** — merge to `main` completes repository canonicalization.

## Immutable candidate rule

Every candidate that reaches review remains immutable and separately byte-bound even if later commits advance the same PR. A correction creates a new candidate artifact/binding, not an in-place mutation of an already reviewed artifact.

Git history and durable review records preserve rejected or superseded candidates.

## Merge gate

Do not merge a holistic iteration PR unless all are true:

- exact candidate artifact is durably bound by filename, byte size, SHA-256, and durable object location;
- producer validation is recorded;
- fresh independent review of that exact artifact is PASS;
- no unresolved BLOCKER or MAJOR finding remains;
- founder explicitly promotes that exact reviewed artifact;
- canonical predecessor guarantees are either preserved or any intentional change is separately founder-authorized.

## Predecessor rule

Each iteration branch starts from the current canonical `main` state. The iteration record must name the exact canonical predecessor artifact and SHA-256.

## Scope and authority boundary

Merging a holistic prototype PR canonicalizes product/design authority only. It does not automatically admit or mutate web implementation, Android implementation, backend, API, schema, database, deployment, production, signing, or release state.

Implementation admission remains a separate cycle.

## v0.4 transition exception

v0.4 was independently reviewed, founder-promoted, and durably recorded directly on `main` before this process was adopted. Do not manufacture a retroactive PR solely for ceremony.

v0.4 is the transition authority. The PR canonicalization rule is mandatory beginning with v0.5.

## Governing shorthand

`MAIN = CANONICAL_OR_HISTORICAL_ONLY`

`HOLISTIC_ITERATION_WORK = OFF_MAIN_UNTIL_PROMOTED_AND_MERGED`

`ONE_HOLISTIC_VERSION = ONE_BRANCH + ONE_PR`

`BOUNDED_CORRECTIONS = SAME_VERSION_PR`

`MERGE_AFTER_FOUNDER_PROMOTION = CANONICALIZATION_EVENT`
