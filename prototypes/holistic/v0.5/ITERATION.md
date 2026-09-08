# Draneka Aquarium Breeder — Holistic v0.5 Iteration

Date opened: 2026-09-08
Status: **DRAFT / PRODUCING / NON-CANONICAL**
Branch: `prototype/v0.5-cohort-egg-batch-population-operations`

## Canonical predecessor

v0.5 starts from the exact founder-promoted holistic v0.4 authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.4-BOUNDED-CORRECTION-CANDIDATE.html`
- SHA-256: `4f82843586c630d3e7542def1632feb8e5c5e766b7d9909e8e41d69b41163a16`
- Size: `242549 bytes`
- Google Drive ID: `19EXK4Gh5Da2_W_5HuUU-ws7feON7qMV7`
- Authority record: `prototypes/holistic/v0.4/AUTHORITY.md`
- Founder decision: `decisions/0005-promote-holistic-v0.4.md`

The v0.4 artifact is immutable predecessor authority.

## Primary product question

Can the breeder manage dozens or hundreds of offspring, eggs, or recruits without individual-record overhead or ancestry loss?

## Required scope

v0.5 must prove, within the existing breeder-native operating surface:

- count / estimate with uncertainty;
- move;
- split;
- lineage-safe merge;
- merge of groups with differing ancestry/provenance without ancestry erasure;
- life-stage change;
- loss / mortality adjustment;
- photo / observation;
- quick feeding / care event where relevant;
- promotion of selected offspring into individually tracked breeder candidates;
- ancestry preserved through cohort splits and promotion;
- pre-hatch egg batch -> downstream offspring group;
- one egg batch producing more than one hatch-derived offspring group;
- partial hatch;
- repeated hatch observations / attempts where relevant;
- population / colony recruitment where exact cohort assignment is unavailable.

## Product rule

`Cohort` remains the default offspring / grow-out primitive where it fits, but egg batches and continuous populations are first-class semantics and must not be falsely represented as conventional cohorts.

A merge must preserve all relevant source provenance. If the prototype cannot preserve provenance safely, the merge must be rejected rather than erase ancestry evidence.

## Locked predecessor guarantees

v0.5 must not weaken these canonical v0.4 guarantees:

1. Program remains lightweight durable context, not mandatory ceremony.
2. Event-first Program creation remains atomic.
3. Exact ancestry is asserted only where evidence supports it.
4. Unknown/group/population parentage remains explicitly incomplete at exact-parent level.
5. Betta known-pair lineage remains exact.
6. Multiple Medaka egg batches remain independently addressable.
7. One egg batch may support multiple hatch observations / offspring groups.
8. Population-derived Neocaridina stock retains source-population provenance without fabricated sire/dam or pair history.
9. Moves and splits preserve source-output / source-hatch provenance.
10. Tanks remain locations/environmental context rather than lineage owners.
11. Suggestion, scheduled action, completed action, observation, and derived state remain distinct.
12. Routine UX remains breeder-native and anti-overwhelm.

## UX budget

- Frequent tank-side group operations should take only a few taps.
- Do not open a full edit form unless details are actually needed.
- Do not add a new top-level navigation destination merely because v0.5 adds operations.
- Keep offspring grouped until individual identity creates value.
- Uncertainty must be visible without turning the surface into architecture documentation.

## Explicitly deferred

- detailed grading systems;
- broad analytics and reports;
- sophisticated capacity forecasting;
- multi-channel commerce;
- full species-overlay UI;
- predictive genetics / authoritative best-pair decisions;
- individual records for every fry or shrimplet;
- hardware / automation expansion.

## Required stress paths

The v0.5 candidate must at minimum demonstrate:

### Betta
Known-pair spawn -> offspring group -> split -> move -> selected holdback / breeder candidate, with exact ancestry preserved.

### Medaka
Egg batch -> partial hatch A + partial hatch B -> multiple offspring groups -> independent move/split operations -> provenance-safe downstream state.

### Neocaridina
Population recruitment -> population-derived offspring/group operation -> split/move/count adjustment -> selected breeder candidate, while exact parent IDs remain unknown and source-population provenance remains intact.

### Merge safety
At least one same-provenance merge and one differing-provenance merge case must be exercised. The latter must either preserve all source provenance visibly and structurally or be rejected.

## Candidate / review workflow

This version is governed by `decisions/0006-prototype-iteration-pr-canonicalization-model.md` and `PROTOTYPE-ITERATION-WORKFLOW.md`.

- One v0.5 branch.
- One v0.5 PR.
- Any bounded corrections stay in that same PR.
- Every reviewed candidate is immutable and separately byte-bound.
- v0.5 does not become canonical through candidate creation, validation, review PASS, or founder promotion alone.
- After founder promotion, merge of this v0.5 PR to `main` is the repository canonicalization event.

## Exit criterion

A breeder can maintain real grow-out, egg-batch, and population-derived offspring through moves, splits, merges, partial hatches, count/loss changes, and promotion without losing lineage or drowning in forms.

`HOLISTIC_V0_5_ITERATION = OPEN`

`HOLISTIC_V0_5_CANONICAL = NO`
