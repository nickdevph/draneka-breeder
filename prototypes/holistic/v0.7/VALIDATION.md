# Producer Validation — Holistic v0.7 Selection and Line Development Candidate

Date: 2026-09-08
Role: Producer validation
Disposition: **PASS / READY_FOR_FRESH_INDEPENDENT_REVIEW / NON-CANONICAL**
PR: `#7`

## Exact candidate under validation

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-CANDIDATE.html`
- Google Drive ID: `1Nh9wctld-lfE5doncPbpNdteRGQVupZw`
- Exact size: `330316 bytes`
- SHA-256: `d25500aa46ff36eaac29fa5856552ac1caffb93f8ff0407b330a1aba3032c5c0`

A fresh raw Drive re-download independently measured `330316` bytes and hashed to the exact SHA-256 above. The Drive object is not to be overwritten.

## Runtime method

The exact candidate bytes were exercised in executable Chromium through Playwright at exact viewport widths `320`, `390`, `768`, and `1440` px. Runtime page errors and console errors were captured. Route and dialog dimensions were checked for horizontal overflow.

JavaScript syntax was separately checked with Node and passed.

## Responsive/runtime matrix

At every required width:

- routed surfaces exercised: `85`;
- route render failures: `0`;
- document horizontal-overflow failures: `0`;
- dialog horizontal-overflow failures: `0`;
- page errors: `0`;
- console errors: `0`.

The 85-route matrix retains the complete v0.6 route coverage and adds the seven Program-scoped v0.7 selection workspaces.

## Functional assertions

The following 26 assertions passed at **each** of `320 / 390 / 768 / 1440`:

1. Goal edit creates history.
2. Historical evaluation goal snapshot is not rewritten.
3. New evaluation saves the current goal snapshot.
4. Photo evidence is attached explicitly.
5. Evaluation does not mutate ancestry.
6. Selection session records Holdback / Non-breeding / Sale-rehome / Retire decisions.
7. Selection session retains its goal snapshot.
8. Selection decisions preserve ancestry.
9. Sale/rehome disposition does not create commerce/live-exit behavior.
10. Pair Builder retains sibling relatedness checks.
11. Pair Builder contains no opaque `best pair` authority.
12. Medaka two-cohort comparison renders.
13. Medaka insufficient evidence remains explicit.
14. Medaka distinct hatch provenance remains intact.
15. Neocaridina holdback retains population/colony provenance.
16. Population-derived Neocaridina holdback remains Pair Builder-ineligible where exact ancestry evidence is insufficient.
17. Holdback does not infer breeding readiness.
18. Guppy selection does not invent a sire.
19. Killifish mop-method switch creates no biological record.
20. Mop/plant collection remains separate from hatch.
21. Wetting attempt 1 does not infer hatch.
22. Re-dry provenance remains distinct and does not infer hatch.
23. Second wetting receives distinct attempt identity.
24. Annual hatch is explicit and links to selected attempt 2.
25. Annual cohort retains both hatch and wetting-attempt provenance.
26. Final mutated state retains zero horizontal overflow.

All 26 assertions passed at all four required widths.

## v0.7 semantic gates

### Goal history

PASS. Current Program goal edits append history. Existing evaluation/session `goalSnapshot` values remain unchanged.

### Phenotype/genotype boundary

PASS. Phenotype evaluation is recorded as breeder observation/assessment. No workflow promotes phenotype to genotype. Unknown genetics and uncertain ancestry remain unknown.

### Evidence

PASS. Evaluations retain explicit evidence references. Missing evidence remains visible. Seeded prototype evidence is labelled synthetic/demo evidence and is not presented as biological/genetic proof.

### Selection decisions

PASS. Holdback, non-breeding, sale/rehome, retire, and undecided are explicit breeder decisions with reasons. Decision history is retained.

### Commerce boundary

PASS. `Sale / rehome` is only a breeder disposition label. No marketplace listing, channel allocation, commerce quantity, sales status, or v0.9 handoff was introduced.

### Pair Builder boundary

PASS. Existing lineage-relatedness warnings remain. Exact sibling relationships remain detectable. Population/group-derived incomplete ancestry remains conservative. No authoritative `best pair` recommendation is introduced.

### Species/provenance stress

PASS.

- Betta exact-parent evidence survives evaluation and selection.
- Guppy sire uncertainty remains unresolved after evaluation/selection.
- Medaka multi-hatch/source provenance remains distinct during cohort comparison.
- Neocaridina population/colony provenance remains present after selected-offspring promotion, evaluation, and holdback; exact parents remain unknown.
- v0.6 killifish mop/plant and structured annual wetting provenance paths remain intact.

## Scope discipline

PASS. No new top-level navigation destination is introduced. Selection/evaluation remains contextual. No v0.8 dynamic Breeder Round/capacity work, v0.9 commerce handoff, backend/API/schema/database/deployment, production, Android, or web implementation authority is admitted.

## Producer disposition

`HOLISTIC_V0_7_JAVASCRIPT_SYNTAX = PASS`

`HOLISTIC_V0_7_RESPONSIVE_MATRIX = PRODUCER_PASS`

`HOLISTIC_V0_7_FUNCTIONAL_ASSERTIONS = 26_OF_26_PASS_AT_ALL_REQUIRED_WIDTHS`

`HOLISTIC_V0_7_DRIVE_ROUND_TRIP = PASS`

`HOLISTIC_V0_7_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_7_READY_FOR_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_7_CANONICAL = NO`

Producer PASS is not an independent-review PASS. The exact candidate must receive fresh independent review before any founder promotion or merge.