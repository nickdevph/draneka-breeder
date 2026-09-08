# Draneka Aquarium Breeder — Holistic v0.8 Bounded Correction Receipt

Date: 2026-09-08
Status: **BOUNDED CORRECTION PRODUCED / NON-CANONICAL / MERGE HOLD**

## Triggering independent review

The first holistic v0.8 independent review returned `CHANGES_REQUIRED` on exact pre-receipt head `5fcf45b2d20a30bfa17458c9473b5664f9c8a06e`.

Review receipt:

`reviews/holistic-v0.8-independent-review-2026-09-08.md`

Receipt-only commit:

`6285ee4df025f375527d3450c4769c1ffc21dc55`

The independent review identified exactly two MAJOR promotion blockers:

- `V08-IR-001` — unrelated cohort mutation could falsely mark a grow-out plan `Executed`.
- `V08-IR-002` — a cancelled lifecycle action could remain armed and an unrelated later record could falsely close the lifecycle prompt.

The same review independently passed canonical v0.7, v0.6 and v0.5 regressions, responsive/runtime qualification, and scope discipline. This correction is therefore bounded to those two operational-authority defects.

## Historical failed candidate — preserved

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-CANDIDATE.html`
- Drive ID: `1SVaVXVm4DEOXyx8lxxRlMBbj8CUQsPS8`
- Bytes: `386074`
- SHA-256: `9dea5ada178d0814f86d2014a05ece56f8ed2c2be4f79f64ab2f34560b3f4704`
- Independent disposition: `CHANGES_REQUIRED`

That Drive object was not overwritten.

## New immutable bounded-correction candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `1Lrdd1OX0I297hS3fBHXOSk6lmAwws3y9`
- Exact bytes: `391223`
- SHA-256: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`
- MIME: `text/html`

A raw Drive re-download reproduced the same filename, `391223` bytes and SHA-256 above.

## Correction V08-IR-001 — grow-out plan execution authority

The prior candidate treated any quantity/location/active-state mutation on the planned cohort as evidence that a plan had executed.

The bounded correction removes that loose mutation rule.

A `Planned` grow-out plan can now become `Executed` only when the saved canonical operation matches all relevant plan authority:

- same Program;
- same source cohort;
- same operation type (`move` or `split`);
- for a move: same explicit target and whole-group quantity;
- for a split: source becomes historical, child quantity remains conserved, and a resulting child has the planned quantity in the planned target location.

Count revisions, mortality, feeding, life-stage changes, observations and other unrelated mutations cannot execute a grow-out plan.

Execution history records the exact matching operation/event ID rather than merely claiming that some cohort mutation occurred.

## Correction V08-IR-002 — lifecycle prompt resolution authority

The prior candidate retained a global pending lifecycle marker after a record form was cancelled. A later unrelated record could therefore be mistaken as resolution evidence.

The bounded correction replaces that behavior with an ephemeral lifecycle record intent that:

- is established only for the explicit lifecycle action being opened;
- is cleared when the record form/dialog is cancelled or closed;
- resolves a prompt only when the saved record type matches the prompt's expected action;
- requires matching Program identity;
- requires matching cohort identity when the prompt is cohort-bound;
- requires matching reproductive-output/spawn identity when the prompt is output-bound;
- stores the exact matching event ID in lifecycle history.

Annual-killifish wetting uses the same semantic-resolution rule even though its canonical wetting form is a specialized workflow rather than the generic Quick Log form.

An unrelated Betta feeding, or any other context-mismatched record, cannot resolve a Rachovii wetting review.

## Authority boundary

No v0.9 commerce behavior, backend/API/schema/database/deployment mutation, Android/web implementation authority, genotype inference, automatic biological completion, or generic task-management expansion is introduced.

Canonical v0.7 remains the product/design authority until this corrected candidate independently passes, receives Founder promotion and PR #8 is merged.

`V08_IR_001_CORRECTION = PRODUCED`

`V08_IR_002_CORRECTION = PRODUCED`

`HOLISTIC_V0_8_BOUNDED_CORRECTION_CANONICAL = NO`

`PR_8_MERGE = HOLD`