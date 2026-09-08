# Draneka Aquarium Breeder — Holistic v0.7 Iteration

Date: 2026-09-08
Status: **DRAFT / PRODUCING / NON-CANONICAL**
Branch: `prototype/v0.7-selection-line-development`

## Canonical predecessor

Holistic v0.7 begins from the exact repository-canonical holistic v0.6 authority on `main`.

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Google Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Size: `295505 bytes`
- SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical merge commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

v0.6 remains immutable and canonical unless and until an exact v0.7 candidate completes producer validation, fresh independent review, founder promotion, and merge of the v0.7 iteration PR.

## Primary product question

Can the product support the breeder's actual improvement and selection decisions rather than merely documenting reproduction?

## Founder-locked v0.7 objective

Prove **selection and line development** without turning phenotype observations into unsupported genotype claims and without introducing opaque automated pair authority.

The v0.7 candidate must preserve the v0.6 shared breeder core, species overlays, provenance semantics, and uncertainty boundaries while adding only the selection/line-development capability needed to answer the primary question.

## Must prove

1. **Breeding goal**
   - A Program can state a plain-language breeding goal.
   - The goal is visible during evaluation and selection work.
   - Editing the goal does not rewrite past evaluations or historical selection reasons.

2. **Time-stamped phenotype / trait evaluations**
   - A breeder can record an evaluation against an animal or breeder candidate and, where biologically useful, against an offspring group/cohort.
   - Evaluations retain timestamp, observed traits, notes, evaluator-entered rating/assessment, and evidence references.
   - Evaluation wording remains observation/evidence, not genotype inference.

3. **Photo / evidence attachment**
   - Evaluations can retain attached photo/evidence references.
   - Missing evidence remains visibly missing rather than silently implied.

4. **Selection session**
   - A breeder can start a bounded selection session from a Program/generation/cohort context.
   - Candidates can be compared against the current breeding goal and recorded evidence.
   - The session must record why an animal/group was kept or not kept.

5. **Breeder holdback**
   - Selected animals can be marked as breeder holdbacks/candidates without fabricating genotype or future breeding success.
   - Existing lineage/provenance is retained.

6. **Disposition**
   - Non-breeding, sale/rehome, and retire dispositions are explicit breeder decisions.
   - A disposition must not delete ancestry, historical evaluations, or reproductive history.
   - v0.7 may record a breeder disposition label only; marketplace/channel/listing workflow remains v0.9 scope.

7. **Generation / cohort comparison against the goal**
   - A breeder can compare recorded outcomes across at least two generations/cohorts against the stated goal.
   - Comparisons must derive only from recorded evaluations and visible evidence.
   - Missing or uneven evidence must remain visible.

8. **Pair Builder relatedness checks retained**
   - Existing lineage-relatedness authority remains available.
   - Pair Builder may surface relatedness/evidence warnings.
   - It must not issue an opaque authoritative `best pair` recommendation.

## Product rules

- **Phenotype does not prove genotype.** Unknown genetics remain unknown.
- A rating is a breeder-recorded assessment, not a biological fact beyond the recorded observation.
- Selection decisions are historical records and must retain their original goal/evidence context even if the current Program goal later changes.
- Holdback and disposition are breeder decisions, not inferred states.
- Comparison UI must show evidence coverage and uncertainty instead of converting sparse observations into false precision.
- Existing parentage, reproductive-output, hatch, cohort, split/merge, wetting-attempt, and population-provenance semantics remain unchanged.

## Required stress paths

### Betta — individual holdback from controlled ancestry

- Use a Betta Program with evidence-bound known parentage.
- Record multiple phenotype evaluations with photo/evidence references.
- Run a selection session against the Program breeding goal.
- Keep one candidate as a breeder holdback and disposition another as non-breeding/rehome.
- Confirm exact parentage remains unchanged and the selection record does not infer genotype.

### Fancy guppy — line improvement with uncertain sire context

- Use a guppy line where mother/source evidence is stronger than sire evidence.
- Evaluate visible phenotype across multiple candidates/cohorts.
- Compare two generations/cohorts against the goal.
- Confirm the comparison does not resolve uncertain sire/genotype information.

### Medaka — cohort/generation comparison

- Use repeated egg/hatch-derived cohorts.
- Record evaluation coverage across more than one cohort/generation.
- Compare against the Program goal while preserving differing hatch/source provenance.
- Missing evaluations must remain visible rather than treated as neutral/zero scores.

### Neocaridina — population-derived selection

- Select visible phenotype from population-derived recruitment without inventing exact individual parents.
- Promote a selected animal to holdback while preserving population provenance and unknown exact parentage.
- Pair Builder relatedness must remain conservative where source evidence is insufficient.

## UX constraints

- Do not add a new top-level navigation destination merely for v0.7.
- Selection/evaluation should appear contextually from Program, breeder-stock/candidate, cohort/grow-out, and lineage surfaces.
- Frequent evaluation actions should stay compact and mobile-first; advanced notes/evidence may expand progressively.
- Comparison should prioritize a small number of meaningful goal-linked observations rather than a generic analytics dashboard.
- The user must be able to distinguish `Observed`, `Breeder assessment`, `Selection decision`, and `Unknown` states at a glance.

## Explicitly not admitted

This iteration does **not** introduce:

- genotype prediction from phenotype;
- automated or opaque `best pair` authority;
- broad genetics calculators;
- v0.8 dynamic Breeder Round scheduling/attention expansion;
- capacity forecasting or operational allocation planning;
- v0.9 commerce handoff, marketplace listings, channel allocation, or sales CRM;
- new backend/API/schema/database/deployment/production authority;
- Android or web implementation authority.

## Validation gates

The candidate is not promotion-eligible until all of the following are independently exercised on the exact immutable candidate bytes:

- canonical v0.6 regression paths remain intact;
- breeding-goal history behavior;
- timestamped evaluation creation and evidence attachment;
- selection-session decision history;
- holdback and each admitted disposition path;
- Betta exact-parent preservation;
- guppy uncertainty preservation;
- Medaka multi-cohort/generation comparison with missing-evidence handling;
- Neocaridina population-provenance holdback path;
- Pair Builder conservative relatedness behavior;
- phenotype/genotype boundary;
- responsive matrix at 320 / 390 / 768 / 1440;
- no v0.8/v0.9 scope leakage.

## Exit criterion

A breeder can answer, from recorded evidence:

**What did I select for, what did this generation produce, and why did I keep these animals?**

without Draneka pretending phenotype proves genotype or presenting an opaque automated pairing decision.

`HOLISTIC_V0_7_ITERATION_STARTED = YES`

`HOLISTIC_V0_7_CANONICAL_PREDECESSOR = V0_6`

`HOLISTIC_V0_7_CANONICAL = NO`
