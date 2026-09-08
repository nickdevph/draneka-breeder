# Draneka Aquarium Breeder — Holistic v0.5 Iteration

Date opened: 2026-09-08
Status: **CANDIDATE PRODUCED / READY_FOR_INDEPENDENT_REVIEW / NON-CANONICAL**
Branch: `prototype/v0.5-cohort-egg-batch-population-operations`
PR: `#4` — Holistic v0.5 — Cohort / egg-batch / population operations

## Canonical predecessor

v0.5 starts from the exact founder-promoted holistic v0.4 authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.4-BOUNDED-CORRECTION-CANDIDATE.html`
- SHA-256: `4f82843586c630d3e7542def1632feb8e5c5e766b7d9909e8e41d69b41163a16`
- Size: `242549 bytes`
- Google Drive ID: `19EXK4Gh5Da2_W_5HuUU-ws7feON7qMV7`
- Authority record: `prototypes/holistic/v0.4/AUTHORITY.md`
- Founder decision: `decisions/0005-promote-holistic-v0.4.md`

The v0.4 artifact remains immutable canonical authority while PR #4 is open.

## Current v0.5 candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.5-CANDIDATE.html`
- SHA-256: `762eb3837f0a137c9b0a5f99e83afc28e481f494098804ac1ad992fb34881bb2`
- Size: `257138 bytes`
- Google Drive ID: `132jlSrFTAyEoc_PrTd4MPzUk9SV0CYha`
- Candidate binding: `prototypes/holistic/v0.5/CANDIDATE.md`
- Producer validation: `prototypes/holistic/v0.5/VALIDATION.md`
- Producer disposition: `HOLISTIC_V0_5_PRODUCER_VALIDATION = PASS`

The uploaded Drive object was re-downloaded and matched the validated local candidate byte-for-byte.

## Primary product question

Can the breeder manage dozens or hundreds of offspring, eggs, or recruits without individual-record overhead or ancestry loss?

## Required / embodied scope

v0.5 is bounded to group-scale offspring, egg-batch, and population operations:

- exact / estimated count with uncertainty;
- move;
- split;
- lineage-safe merge;
- differing-provenance merge without ancestry erasure;
- explicit life-stage change;
- loss / mortality adjustment;
- photo / observation;
- quick care / feeding event where relevant;
- selected-offspring promotion into individually tracked breeder candidates;
- ancestry/provenance preservation through split and promotion;
- egg batch -> downstream offspring group;
- multiple hatch-derived groups from one egg batch;
- partial / repeated hatch observations;
- population / colony recruitment where exact parentage is unavailable.

## Product rule

`Cohort` remains the default offspring / grow-out primitive where it fits, but egg batches and continuous populations are first-class semantics and are not forced into conventional cohort ancestry.

A merge must preserve all relevant source provenance. The v0.5 candidate limits merges to active groups within one Breeding Program and retains the union of source output and source hatch identifiers. Where exact ancestry cannot be resolved after combination, it remains ambiguous rather than being fabricated.

## Locked predecessor guarantees

v0.5 must not weaken canonical v0.4:

1. Program remains lightweight durable context, not mandatory ceremony.
2. Event-first Program creation remains atomic.
3. Exact ancestry is asserted only where evidence supports it.
4. Unknown/group/population parentage remains explicitly incomplete at exact-parent level.
5. Betta known-pair lineage remains exact.
6. Multiple Medaka egg batches remain independently addressable.
7. One egg batch may support multiple hatch observations / offspring groups.
8. Population-derived Neocaridina stock retains source-population provenance without fabricated sire/dam or pair history.
9. Moves, splits, and v0.5 merges preserve source provenance.
10. Tanks remain locations/environmental context rather than lineage owners.
11. Suggestion, scheduled action, completed action, observation, and derived state remain distinct.
12. Routine UX remains breeder-native and anti-overwhelm.

## Required stress paths

### Betta
Known-pair spawn -> offspring group -> split -> move -> selected holdback / breeder candidate, with exact ancestry preserved.

### Medaka
Egg batch -> partial hatch A + partial hatch B -> multiple offspring groups -> merge/split/move/life-stage operations -> provenance-safe downstream state.

### Neocaridina
Population recruitment -> population-derived group operation -> split/move/count adjustment -> selected breeder candidate, while exact parent IDs remain unknown and source-population provenance remains intact.

### Merge safety
The candidate includes an immediately exercisable same-output / different-hatch Medaka merge and supports differing-output merge while retaining all contributing source IDs. Estimated quantity propagates conservatively.

## UX budget

- Frequent tank-side group operations remain a few contextual actions.
- No new top-level navigation destination was added.
- Offspring remain grouped until individual identity creates value.
- Uncertainty is visible without turning default surfaces into architecture documentation.

## Explicitly deferred

- detailed grading systems;
- broad analytics and reports;
- sophisticated capacity forecasting;
- multi-channel commerce;
- full species-overlay UI;
- predictive genetics / authoritative best-pair decisions;
- individual records for every fry or shrimplet;
- hardware / automation expansion;
- cross-Program cohort merge.

## Candidate / review workflow

This version is governed by `decisions/0006-prototype-iteration-pr-canonicalization-model.md` and `PROTOTYPE-ITERATION-WORKFLOW.md`.

Completed:

- candidate artifact produced;
- exact bytes / SHA-256 / Drive object bound;
- Drive round-trip rebound;
- producer validation passed.

Remaining:

- fresh independent review of the exact candidate;
- bounded correction inside the same PR if required, with a new immutable candidate binding;
- independent PASS on the final exact candidate;
- founder promotion of that exact reviewed candidate;
- merge of PR #4 to `main`, which is the repository canonicalization event.

## Exit criterion

A breeder can maintain real grow-out, egg-batch, and population-derived offspring through moves, splits, merges, partial hatches, count/loss changes, life-stage changes, and promotion without losing lineage or drowning in forms.

`HOLISTIC_V0_5_ITERATION = READY_FOR_INDEPENDENT_REVIEW`

`HOLISTIC_V0_5_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_5_CANONICAL = NO`
