# Independent Review Mandate — Holistic v0.7 Second Bounded Correction

## Role

Act as a fresh independent reviewer of the exact v0.7 second bounded-correction candidate below.

Do **not** inherit PASS claims from the producer, prior independent review, Founder disposition, durable receipts, or earlier conversation context.

Do not redesign or modify the prototype. Do not promote it. Do not merge PR #7. Do not mutate backend, API, schema, database, deployment, production, Android, release, or later-version product scope.

Your task is to determine independently whether the three promotion blockers identified in the previous review are actually closed without regression to the Founder-approved v0.7 objective or canonical v0.6 breeding/provenance behavior.

## Exact candidate under review

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`

Google Drive ID:

`13LbZKVuq02tk2Vmhb4mBvWipChpv_V7r`

Expected bytes:

`332362`

Expected SHA-256:

`f82ef39241b36c0325ff918b9e95b447a964b4426ca2fe530c70e86e3b329930`

First independently retrieve the Drive object and calculate its byte count and SHA-256. Stop with `CHANGES_REQUIRED` if exact binding fails.

## Canonical predecessor

v0.6 remains canonical:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.6-RESPONSIVE-CORRECTED-CANDIDATE.html`
- Drive ID: `1iLH7iU_2Ik6k37Y-eL9C0qfQmrqi30e_`
- Size: `295505 bytes`
- SHA-256: `bc0ef50c26c96614574fbfd14f18f88dab2a98b99ab2b222ea3e5624059a9c70`
- Canonical merge commit: `f38b9546665df806ab2fe3b91749abcb4ba020fe`

The previously reviewed v0.7 bounded-correction candidate is historical evidence only:

- Drive ID: `1WCEPsAM35WsGo-y5IdJ0w5pSNBXHV_Hg`
- Size: `330298 bytes`
- SHA-256: `6c47d96330fca26dd7d2c2d9d1f7dcc2ba0753b283d23f19415793cca9bc0186`
- Previous independent disposition: `CHANGES_REQUIRED`

## Mandatory blocker retests

### G1 — disposition semantics and Pair Builder authority

Exercise a real selection session through the candidate UI using an individual that already has recorded breeding readiness.

Required assertions:

- `Holdback` alone must not create readiness for a not-ready animal.
- a ready animal with current `Non-breeding` disposition must become unavailable/ineligible in Pair Builder.
- a ready animal with current `Retire` disposition must become unavailable/ineligible in Pair Builder.
- also verify `Sale / rehome` cannot bypass the same negative-disposition breeding boundary.
- a later/current `Holdback` decision on an otherwise-ready animal must not be treated as a negative disposition by itself.
- readiness history and selection disposition must remain semantically separate; the implementation need not erase historical readiness merely to enforce current eligibility.

Check the same explicit negative-disposition boundary cannot be bypassed through the ordinary breeding-arrangement stock chooser.

### G2 — unsupported filial-generation precision

Construct a controlled-pair path with exact recorded individual parents carrying different filial labels, specifically an `F1 × F2` stress path.

Required assertions:

- the reproductive/cohort path must not derive `F3` merely from `max(parent F)+1`;
- cohort-selection generation must remain uncertain/conservative unless a supported exact filial designation exists;
- promoting an offspring through the normal UI to a named stock record must not manufacture `F3` from the mixed `F1 × F2` parents;
- exact parent identity must remain preserved even when filial generation is uncertain;
- population/group parentage must remain conservative and must not gain exact filial precision.

Also verify the candidate has not broadly broken supported same-line, same-filial controlled-pair behavior that was previously represented by the Betta fixture.

### G3 — initial goal-history ledger completeness

Required assertions:

- every seeded Program with a non-empty current goal has at least one dedicated `goalHistory` record before any edit;
- specifically inspect the killifish Program that previously lacked a seeded goal-history entry;
- edit a goal and verify the previous goal remains in `goalHistory` while the new goal is appended;
- existing evaluation and selection-session goal snapshots remain unchanged;
- create a new Program with a non-empty goal through the normal UI and verify its initial goal is immediately present in `goalHistory` before later edits.

## Full v0.7 regression boundary

Re-exercise the areas that independently passed previously. At minimum verify:

- cross-Program selection isolation despite same species/line text;
- phenotype/evaluation versus genotype boundary;
- explicit evidence attachment and missing-evidence handling;
- selection reasons and immutable goal snapshots;
- Betta exact ancestry and known-relationship Pair Builder warnings;
- guppy known-mother / unknown-sire uncertainty;
- Medaka distinct hatch/source provenance and comparison uncertainty;
- Neocaridina population-derived conservative parentage and pairing behavior;
- no opaque authoritative `best pair` output;
- count revision remains distinct from recorded mortality;
- move, split, merge, mortality, life-stage update and quick feeding preserve count/provenance semantics.

## Mandatory canonical v0.6 killifish regression

Run the full annual-killifish path and confirm the following remain distinct and correctly linked:

1. mop/plant or egg-medium collection;
2. first wetting attempt;
3. re-drying;
4. distinct second wetting attempt;
5. explicit hatch observation;
6. resulting offspring cohort/source provenance.

No wetting event may silently become a hatch, and re-dry/second wetting must not collapse provenance.

## Browser/runtime and responsive qualification

Run the exact candidate in a real browser runtime. Required widths:

- `320px`
- `390px`
- `768px`
- `1440px`

Exercise the major routed/dialog surfaces used in the prior review, including the corrected selection, stock, Pair Builder, Program creation/edit, cohort-selection and goal-history paths.

At each width verify:

- requested `window.innerWidth` is actually achieved;
- no document/body horizontal overflow;
- no dialog horizontal overflow;
- no page errors;
- no console errors;
- no promotion-blocking usability regression.

Do not inherit the predecessor responsive PASS for these new SHA-bound bytes.

## Scope discipline

Fail if the correction introduces unrelated redesign or admits v0.8 dynamic operational scheduling/capacity work, v0.9 commerce handoff/listing/channel allocation, backend/API/schema/database/deployment mutation, Android/web implementation changes, promotion, or merge.

## Required disposition

Return one of:

`PASS`

or

`CHANGES_REQUIRED`

If `CHANGES_REQUIRED`, classify every finding as `BLOCKER`, `MAJOR`, `MINOR`, or `POLISH` and identify the exact path that reproduces it.

If `PASS`, explicitly report exact artifact binding, all three blocker retests, the v0.7 regression boundary, the full v0.6 killifish regression, responsive/browser matrix, scope discipline, exact PR head reviewed, and confirm PR #7 remains open/unmerged and v0.6 remains canonical.

Expected final state before Founder promotion:

```text
HOLISTIC_V0_7_EXACT_BINDING = PASS
HOLISTIC_V0_7_DISPOSITION_SEMANTICS = PASS
HOLISTIC_V0_7_GENERATION_PRECISION = PASS
HOLISTIC_V0_7_GOAL_HISTORY = PASS
HOLISTIC_V0_7_V0_7_REGRESSION = PASS
HOLISTIC_V0_7_V0_6_REGRESSION = PASS
HOLISTIC_V0_7_RESPONSIVE_MATRIX = PASS
HOLISTIC_V0_7_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_7_INDEPENDENT_REVIEW = PASS
HOLISTIC_V0_7_PROMOTION_ELIGIBLE = YES
HOLISTIC_V0_7_CANONICAL = NO
PR_7_MERGE = HOLD
```

Independent PASS alone does not authorize promotion or merge.
