# Independent Review Mandate — Holistic v0.7 Third Bounded Correction

Date: 2026-09-08

## Role

Act as the **independent Draneka Aquarium Breeder v0.7 third bounded-correction reviewer**.

Perform a fresh independent review of the exact candidate below. Do not inherit PASS claims from the producer, prior independent reviews, Founder disposition, producer validation, PR descriptions, durable receipts, or earlier conversation context.

Do not redesign or modify the prototype. Do not promote it. Do not merge PR #7. Do not mutate candidate Drive bytes. Do not mutate backend, API, schema, database, deployment, production, Android, release state, or later-version scope.

Your task is to determine independently whether the remaining promotion blocker `V07-SECOND-IR-001` is closed without regression to the Founder-approved v0.7 selection/line-development objective or canonical v0.6 breeding/provenance behavior.

## Exact candidate under review

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-THIRD-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1-tsivYwu1htoqd2xgfx20iWklKwJjJl-`
- Expected size: `334514 bytes`
- Expected SHA-256: `1e6ce9f961224423fb5b6d1f4abad2687cc13a633884ebdbefc57e542c9d2a3f`

Independently retrieve the Drive object and calculate size/SHA-256 before product review. Fail exact binding if they differ.

## Canonical predecessor

Independently bind canonical v0.6 as the regression authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Expected size: `295505 bytes`
- Expected SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical merge/base commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

## PR binding

Repository: `nickdevph/draneka-breeder`
PR: `#7`
Branch: `prototype/v0.7-selection-line-development`
Base: `main` / canonical v0.6

Bind the exact PR head present at the start of review. The current producer record commits are not correctness evidence. If you write a durable independent-review receipt, clearly distinguish the exact pre-receipt head reviewed from any receipt-only head created afterward.

## Remaining blocker that must be independently reproduced/closed

`V07-SECOND-IR-001 — Pair Builder stale-parent authority bypass`

Prior failure path:

1. Open `Copper halfmoon · next generation` → `Selection & line development`.
2. Start a normal selection session.
3. For already-ready `Atlas · retained F2`, record a negative current disposition with a breeder-entered reason and save.
4. Confirm historical `ready=true` remains while current selection disposition changes.
5. Confirm the ordinary breeding-stock chooser excludes/disables Atlas.
6. Open Pair Builder.

Required result: Atlas must not be selectable **and must not be rendered as an active pairing parent** in the relationship/result state. Historical readiness may remain as historical evidence but may not bypass current disposition authority.

Repeat independently for each of:

- `Non-breeding`;
- `Retire`;
- `Sale / rehome`.

For each negative disposition verify all of the following:

- `ready=true` can remain historical;
- current disposition is retained with breeder reason and goal snapshot;
- ordinary breeding-stock selection rejects Atlas;
- Pair Builder Stock A and Stock B options reject Atlas;
- Pair Builder active internal parent IDs do not retain Atlas through fallback/default/preselection state;
- relationship title/copy/path/ancestry/coverage do not render Atlas as an active parent;
- relationship-sheet rendering cannot resurrect Atlas;
- continuation controls cannot proceed with Atlas as a hidden/stale parent;
- hard-coded/demo pairing controls cannot re-admit Atlas when currently ineligible;
- a stale selection becoming ineligible while Pair Builder is revisited/re-rendered is normalized or fails closed.

Also verify the no-two-valid-parent edge case fails closed: Pair Builder must not calculate/render a relationship or continuation state using an ineligible record merely to populate the UI.

## Holdback boundary

Independently verify both directions:

- a previously ready animal assigned `Holdback` remains historically ready and eligible if it otherwise satisfies Pair Builder requirements;
- a non-ready animal assigned `Holdback` remains non-ready and Pair-Builder-ineligible. Holdback must not manufacture readiness.

`Sale / rehome` must remain a disposition label only and must not create marketplace, listing, channel-allocation, CRM, payment, or other commerce behavior.

## Mandatory v0.7 regression gates

Re-run the previously passing v0.7 gates rather than inheriting their PASS status:

### Filial-generation precision

Exercise an ordinary complete `F1 × F2` controlled-pair path through pairing → reproductive output → explicit hatch/birth → cohort → named-stock selection.

Required:

- no fabricated `F3`;
- conservative `Generation not established · recorded parents F1 × F2` (ordering may reflect actual parent order);
- exact recorded parent IDs preserved independently from generation certainty.

Also verify supported same-filial behavior remains legitimate, e.g. exact same-line `F1 × F1` can produce `F2`.

Population/group-derived paths, especially Neocaridina, must remain generation-uncertain and must not invent exact parents.

### Initial goal history

Every seeded Program that has a non-empty current goal must have an initial goal-history record before edits, including the annual killifish Program.

Verify:

- existing history records remain immutable when the current goal changes;
- new goal edits append rather than rewrite;
- existing evaluation/selection goal snapshots remain unchanged;
- a newly created Program with an initial goal creates its initial goal-history record immediately and later edits append.

### Program isolation

Create/use a same-species record with the same line text in a different Program. It must not leak into the unrelated Program's selection candidate/session population solely because species/line text matches.

### Phenotype/genotype boundary

Phenotype observations, breeder assessments, evidence, and selection decisions must not establish or claim genotype.

### Evidence and selection history

Verify real evidence attachment works, missing evidence remains visibly missing, breeder-entered selection reasons persist, and goal snapshots remain immutable after later goal edits.

### Species/provenance paths

Recheck the required Betta, fancy guppy, Medaka, and Neocaridina uncertainty boundaries and lineage behavior:

- Betta exact controlled ancestry remains exact when actually recorded;
- relatedness warning remains evidence-based;
- guppy known-mother/unknown-sire uncertainty remains unresolved;
- Medaka distinct source outputs/hatches remain distinct;
- Neocaridina population/colony provenance does not fabricate exact parents and remains Pair-Builder-conservative.

### Count/provenance operations

Re-exercise count revision, mortality, move, split, merge, life-stage change, feeding, and related cohort operations. Count revision must not silently become mortality; split/merge/move must preserve source provenance and avoid double counting.

## Canonical v0.6 annual-killifish regression

Re-run the complete canonical lifecycle through rendered UI:

1. annual egg-medium collection exists;
2. wetting attempt 1;
3. no inferred hatch immediately after wetting;
4. re-dry attempt 1;
5. distinct wetting attempt 2;
6. still no hatch until explicitly recorded;
7. explicit hatch linked to attempt 2;
8. resulting offspring preserve source output / hatch / wetting-attempt provenance;
9. attempt 1 remains separately re-dried and unlinked to hatch.

Also exercise the mop/plant collection path and confirm collection does not infer hatch or success.

## Responsive/runtime qualification

Use a real browser runtime on the exact SHA-bound HTML. Required widths:

- 320 px;
- 390 px;
- 768 px;
- 1440 px.

At each width verify at minimum:

- exact viewport width achieved;
- no document/body horizontal overflow;
- no relevant dialog/sheet horizontal overflow;
- no page errors;
- no console errors;
- major routed/dialog surfaces remain operable;
- Pair Builder negative-disposition path remains correct;
- selection session, cohort selection, split/merge, and annual-killifish lifecycle remain operable.

The artifact is self-contained. If direct `file://` or loopback navigation is unavailable, independently SHA-bind the exact bytes first and then load those exact decoded bytes into a real Chromium document (for example with `page.set_content()`), documenting the method.

## Scope discipline

Fail if the candidate admits unauthorized scope such as:

- v0.8 dynamic scheduling / attention / capacity planning;
- v0.9 commerce handoff, marketplace listing, sales channel allocation, CRM, or payment behavior;
- backend/API/schema/database/deployment/production changes;
- Android/release authority changes;
- opaque authoritative `best pair` selection;
- genotype inference from phenotype.

## Disposition

Return exactly one primary disposition:

- `PASS` — only if exact binding passes, `V07-SECOND-IR-001` is independently closed, all required v0.7/v0.6 regression gates pass, responsive/runtime qualification passes, and scope discipline passes; or
- `CHANGES_REQUIRED` — for any promotion blocker or regression.

Classify findings as `BLOCKER`, `MAJOR`, `MINOR`, or `POLISH` and give exact reproduction evidence.

Do not promote or merge regardless of PASS. If authorized by the review workflow, write only a durable independent-review receipt on the v0.7 branch and report the exact pre-receipt head reviewed plus any receipt-only commit/head afterward.

Expected final status block on PASS:

```text
HOLISTIC_V0_7_EXACT_BINDING = PASS
HOLISTIC_V0_7_PRODUCT_OBJECTIVE = PASS
HOLISTIC_V0_7_GOAL_HISTORY = PASS
HOLISTIC_V0_7_PHENOTYPE_EVALUATION = PASS
HOLISTIC_V0_7_EVIDENCE_ATTACHMENT = PASS
HOLISTIC_V0_7_SELECTION_SESSION = PASS
HOLISTIC_V0_7_PROGRAM_ISOLATION = PASS
HOLISTIC_V0_7_DISPOSITION_SEMANTICS = PASS
HOLISTIC_V0_7_GENERATION_PRECISION = PASS
HOLISTIC_V0_7_PHENOTYPE_GENOTYPE_BOUNDARY = PASS
HOLISTIC_V0_7_PAIR_BUILDER_AUTHORITY = PASS
HOLISTIC_V0_7_V0_7_REGRESSION = PASS
HOLISTIC_V0_7_V0_6_REGRESSION = PASS
HOLISTIC_V0_7_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_7_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_7_INDEPENDENT_REVIEW = PASS
HOLISTIC_V0_7_PROMOTION_ELIGIBLE = YES_PENDING_FOUNDER_PROMOTION
HOLISTIC_V0_7_CANONICAL = NO
PR_7_MERGE = HOLD
```
