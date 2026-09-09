# ROLE = INDEPENDENT DRANEKA AQUARIUM BREEDER V0.9 SECOND BOUNDED-CORRECTION REVIEWER

Perform a **fresh independent review** of the exact corrected v0.9 candidate identified below.

Do **not** inherit PASS claims from:

- the producer;
- producer validation;
- the earlier v0.9 independent reviews;
- the true-independent review that found `V09-TIR-001`;
- Founder prose;
- PR descriptions;
- correction receipts;
- the historical merge of PR #9;
- earlier conversation context.

Establish the result independently from the exact artifact under review.

Do not redesign or modify the prototype. Do not promote it. Do not merge the remediation PR. Do not mutate Drive candidate bytes. Do not mutate backend, API, schema, database, deployment, production, Android/web implementation, release state, or v1.0+ scope.

## 1. Exact candidate under review

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`

Google Drive ID:

`1sZ6TOO25Otne0S5Atbul6s4SRHQMnN-4`

Expected MIME:

`text/html`

Expected exact bytes:

`437576`

Expected SHA-256:

`74b6912c393948fa3b9bf77f6dd21067cceca620f6d09747af1379791c4677b0`

Independently download and hash the raw Drive object. A metadata match alone is insufficient.

## 2. Failing predecessor for differential reproduction

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-BOUNDED-CORRECTION-CANDIDATE.html`

Google Drive ID:

`1OQqLK4aovt4RAfAdKxFnn9n-VB-nUaEX`

Expected exact bytes:

`437100`

Expected SHA-256:

`21736560a33f7ab7a42b46c7691b690b9fb7336638c8fec616da30af345d4327`

Use it only as the exact failed predecessor and differential reference. Do not treat its former promotion/merge status as proof of correctness.

## 3. Governance context

Historical `main` at correction start:

`80ce9259966ca2600a0c35f4633bbec4016329f3`

Historical PR #9 was merged before the later true-independent review found `V09-TIR-001`. Treat that merge only as governance history. The corrected v0.9 candidate is non-canonical and not promotion-eligible until this fresh independent review passes and a Founder disposition explicitly promotes the exact corrected bytes.

Review-only receipt for the blocker:

- branch: `review/holistic-v0.9-true-independent-2026-09-09`
- receipt: `reviews/holistic-v0.9-true-independent-review-2026-09-09.md`
- receipt commit: `4e1bf8e392948e78266752a2a13956e503a8291a`

That receipt defines the prior defect but is not evidence that this correction closes it.

## 4. Mandatory blocker reproduction — V09-TIR-001

Independently reproduce the public/private photo-evidence boundary through the rendered candidate.

At minimum:

1. Use a valid commerce-capable source such as the Betta individual or active Betta cohort.
2. Add at least two source-linked photos with unmistakably different captions/metadata, e.g. one intended public and one intended private.
3. Open sale-ready evidence permissions.
4. Enable `Selected photo evidence` as a public fact.
5. Explicitly select only one photo and leave the other unchecked.
6. Save the sale-ready profile.
7. Confirm the stored profile media permission contains only the selected media ID.
8. Open the AquaticFinder handoff.
9. Inspect the rendered public handoff snapshot before save.
10. Save a structured handoff and inspect both `mediaIds` and `publicFacts.photos`.
11. Generate the breeding/provenance report.

Required result:

- only explicitly selected media IDs may leave Breeder;
- `publicFacts.photos` may contain caption/metadata only for those selected IDs;
- the rendered handoff preview may contain caption/metadata only for those selected IDs;
- the saved handoff may contain no metadata from unselected media;
- the provenance report may contain caption/metadata only for selected media;
- unchecked/private media caption, date, ID, or other human-readable metadata must not leak through any parallel public projection.

Also test an explicitly empty media permission set. Save no selected media, reopen permissions, and verify the UI does not silently reselect all source-linked media. If `Selected photo evidence` remains enabled with zero selected media, the public projection must represent absence without exposing source-media metadata.

Any leak of an unchecked media caption/metadata is a **BLOCKER — private-data exposure**.

## 5. Previously reported v0.9 defects

Freshly establish that these remain closed:

### V09-IR-001 — historical/zero quantity authority

After a real split makes a source historical/inactive at quantity 0:

- new sale-ready quantity authority must be blocked;
- stale commerce-profile state must not bypass handoff guards;
- historical provenance/reporting may remain available;
- no positive commerce quantity may be fabricated.

### V09-IR-002 — duplicate materialized-source ownership

Reproduce both sides:

- a reproductive output whose quantity has materialized into a current offspring cohort must not become a concurrent commerce owner;
- a genuinely remaining unmaterialized egg/output quantity may remain a distinct owner only for the exact remaining amount;
- uncertainty such as population-derived parentage must remain uncertainty.

### V09-IR-003 — Sale / rehome contextual entry and breeding authority

A stock record with current `Sale / rehome` disposition must:

- retain historical readiness only as history;
- remain blocked from breeding-stock selection and Pair Builder;
- expose the contextual commerce handoff entry;
- remain blocked from Pair Builder after becoming sale-ready;
- recover safely from stale requested-parent state.

## 6. Commerce/biological authority gates

Independently verify that sale-ready creation, cancellation, handoff creation and reconciliation do not mutate biological:

- quantity;
- ancestry;
- hatch/output provenance;
- selection evidence;
- readiness;
- lifecycle state;
- unrelated Breeder Round attention.

Verify commerce quantity remains semantically separate from biological quantity and that reconciliation states such as Allocated, Partially sold, Sold, Returned / released and Closed update commerce history only.

A previously created handoff must remain reconcilable as commerce history even if a later real breeder operation makes the biological source historical.

## 7. Provenance gates

Freshly exercise representative canonical provenance paths, including:

- controlled Betta ancestry;
- guppy unknown-sire uncertainty;
- Medaka output/hatch separation;
- Neocaridina population provenance without fabricated exact parents;
- annual-killifish wetting/re-dry/later-wetting/explicit-hatch authority;
- mop/plant collection without inferred hatch.

Commerce preparation must not fabricate parentage, genotype, hatch, lifecycle completion, or output identity.

## 8. Selection / Pair Builder gates

Freshly confirm:

- `Non-breeding`, `Retire`, and `Sale / rehome` block current breeding authority while historical readiness can remain recorded;
- `Holdback` remains readiness-neutral;
- stale requested parents cannot resurrect a currently ineligible animal;
- sale-ready commerce state never restores breeding eligibility.

## 9. Canonical regression gates

Re-run enough of each canonical layer to establish independently that the correction did not alter earlier authority:

### v0.8 operational scale

At minimum re-establish the two former failure paths:

- unrelated count revision, mortality, feeding, or stage-change operations must not execute a planned grow-out split; only the exact matching split may execute it;
- unrelated operations must not resolve an annual-killifish wetting dependency; only the matching wetting operation may resolve it, and wetting alone must not fabricate hatch.

Also inspect operational-attention/schedule/lifecycle/capacity semantics sufficiently to detect collateral regression.

### v0.7 selection and line development

Re-establish current-disposition authority, goal/evaluation evidence behavior, Pair Builder relationship/generation behavior, and population-derived provenance boundaries.

### v0.6 species/provenance

Re-establish the species-specific provenance behaviors represented by Betta, guppy, Medaka, Neocaridina, annual killifish, and mop/plant collection.

### v0.5 cohort operations

Re-establish count revision, mortality, whole-group move, split, merge, stage change, and detailed feeding as distinct biological operations with quantity/provenance conservation.

## 10. Responsive/runtime qualification

Use real Chromium or equivalent browser execution against the exact SHA-bound corrected bytes.

Exercise exact CSS widths:

`320 / 390 / 768 / 1440`

At minimum include the critical v0.9 surfaces and dialogs:

- sale-ready/privacy selection;
- selected-media UI including an empty selection;
- handoff preview/save;
- provenance report;
- reconciliation;
- stock/cohort/output commerce states;
- Sale / rehome selection context;
- Pair Builder;
- representative v0.8/v0.7/v0.6/v0.5 regression surfaces.

Record:

- exact `window.innerWidth`;
- document/body horizontal overflow;
- relevant dialog/sheet horizontal overflow;
- page errors;
- console errors.

## 11. Scope discipline

The bottom navigation must remain:

`Today / Programs / Log / Grow-out / More`

Commerce must remain contextual. The correction must not introduce marketplace-management, pricing, CRM, payments, orders, shipping, finance, public marketplace browsing, broad ERP, genotype inference, automatic biological authority, backend/API/schema/database authority, production implementation, or v1.0+ scope.

Confirm the document metadata now identifies v0.9 rather than stale v0.8/v0.7 text; metadata hygiene is not itself a product redesign gate.

## 12. Disposition

Return exactly one primary disposition:

- `PASS`
- `CHANGES_REQUIRED`
- `FAIL`

Do not use a producer receipt, prior review, historical promotion, PR description, or merge commit as qualification evidence.

If PASS, report the exact independently measured corrected binding and explicitly state:

```text
V09_TIR_001 = CLOSED
HOLISTIC_V0_9_PUBLIC_PRIVATE_EVIDENCE = PASS
HOLISTIC_V0_9_AQUATICFINDER_HANDOFF = PASS
HOLISTIC_V0_9_PROVENANCE_REPORT = PASS
HOLISTIC_V0_9_TRUE_INDEPENDENT_REREVIEW = PASS
HOLISTIC_V0_9_PROMOTION_ELIGIBLE = YES_PENDING_FOUNDER_PROMOTION
HOLISTIC_V0_9_CORRECTED_CANONICAL = NO_PENDING_FOUNDER_PROMOTION_AND_MERGE
```

A PASS does not itself promote or merge the candidate.
