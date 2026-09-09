# Draneka Aquarium Breeder — Holistic v0.9 Iteration

Date: 2026-09-09
Status: **ACTIVE / NON-CANONICAL / PRODUCT-DESIGN PROTOTYPE ONLY**
Branch: `prototype/v0.9-commerce-handoff-evidence`
Canonical base: `main` at `600d992e20d48f3520311d2fdcb087514d68fc95`
Canonical predecessor: holistic v0.8 operational scale

## Primary product question

Can successful breeding records become sale-ready inventory and trustworthy provenance without duplicate data entry or duplicate quantity ownership?

This is the single governing product question for holistic v0.9.

## Mandatory proof scope

The v0.9 candidate must prove all of the following through the holistic prototype:

1. **Sale-ready biological source**
   - An individually tracked animal may be explicitly marked sale-ready.
   - A cohort/batch/population-derived sale unit may be explicitly marked sale-ready where its semantics support it.
   - Sale-ready is a breeder-entered commercial disposition/state layered on top of existing biological records; it must not rewrite ancestry, reproductive output, hatch, selection, mortality, move, split, merge, stage, schedule or lifecycle history.

2. **Explicit public/private fact selection**
   - The breeder explicitly controls which recorded facts may leave Breeder in a commerce handoff or provenance report.
   - Private notes, internal selection rationale, uncertainty details or operational history are not made public merely because the source becomes sale-ready.
   - Missing/unknown evidence remains missing/unknown and cannot be silently filled for commerce presentation.

3. **Evidence and provenance reuse**
   - Existing breeder-record photos/evidence may be selected for the handoff without re-entry.
   - Permissible lineage/provenance may be attached from existing authority.
   - Exact parentage, uncertain parentage, population-derived provenance, hatch/output identity and generation labels must retain their existing evidence boundaries.

4. **Structured handoff to Draneka AquaticFinder**
   - Breeder produces a structured commerce-ready handoff from existing records.
   - The handoff includes stable breeder-source identity and an immutable/source-linked evidence snapshot sufficient for downstream AquaticFinder commerce work.
   - The prototype demonstrates the handoff contract/product boundary only; it does not mutate production APIs, schemas, databases or deployed services.

5. **Breeding / spawn / provenance report**
   - The breeder can generate a human-readable provenance/breeding report from existing records without retyping identity, ancestry, age/timing, traits/evaluations, biological quantity or selected photos.
   - Report content must distinguish recorded fact, breeder assessment, selection decision and unknown/uncertain evidence.

6. **Quantity ownership boundary**
   - Breeder retains biological quantity authority.
   - AquaticFinder commerce allocation is a separate downstream quantity/state concept.
   - A commerce handoff must not subtract, reserve, sell, ship or otherwise mutate the biological cohort count merely because quantity is proposed for commerce.
   - Any demonstrated downstream allocation/outcome is represented as separate commerce reconciliation evidence, not as ancestry or breeder-stock mutation.

7. **Commercial reconciliation boundary**
   - A downstream outcome may reconcile back to the breeder source as commercial history/status.
   - Reconciliation must not rewrite parentage, reproductive output, hatch provenance, selection evidence or historical biological quantities/events.
   - Commercial state and biological state remain separately explainable.

## Required stress paths

The v0.9 candidate must demonstrate the handoff model across materially different existing canonical semantics:

- **Betta individual holdback / selected breeder candidate** — exact ancestry and evaluation evidence, with explicit sale-ready/public fact selection.
- **Medaka cohort/batch** — batch/hatch provenance and grouped quantity without forcing individual identity.
- **Neocaridina population-derived selection** — population provenance with no fabricated exact parents.
- **Annual killifish** — wetting/hatch attempt provenance remains precise if a resulting cohort becomes sale-ready.

At least one path must exercise a quantity handoff where the breeder biological quantity remains unchanged while a separate commerce allocation is represented downstream.

## Canonical predecessor protections

### v0.8 operational attention

Preserve all canonical v0.8 behavior, including:

- dynamic Breeder Round authority;
- recurring schedules;
- due != done semantics;
- lifecycle suggestion vs biological fact boundary;
- capacity unknown/known semantics;
- grow-out plan vs real mutation boundary;
- critical culture dependencies;
- explainability/history;
- the closed `V08-IR-001` and `V08-IR-002` causal-resolution defects.

Commerce state must not close, execute, satisfy or suppress unrelated breeder operational attention unless the breeder explicitly performs the corresponding existing breeder action.

### v0.7 selection and line development

Preserve:

- goal history and historical goal snapshots;
- phenotype/evidence rather than genotype authority;
- explicit missing evidence;
- disposition authority and Pair Builder eligibility boundaries;
- Holdback readiness neutrality;
- ancestry and Program identity isolation;
- population-derived provenance.

Sale-ready must not restore breeding eligibility for `Non-breeding`, `Retire`, or `Sale / rehome` animals or bypass Pair Builder authority.

### v0.6 species/provenance

Preserve Betta, guppy, Medaka, Neocaridina, annual-killifish and mop/plant provenance/uncertainty semantics exactly.

### v0.5 cohort operations

Preserve count revision, mortality, move, split, merge, stage and feeding semantics. Commerce allocation must not masquerade as any of these biological operations.

## Explicit boundary — AquaticFinder owns marketplace operations

The following are **not admitted** into Draneka Breeder v0.9:

- eBay/Etsy/marketplace listing-management UI;
- channel allocation management inside Breeder;
- pricing optimization;
- sales CRM;
- customer messaging;
- payment processing;
- order management;
- shipping/fulfilment workflow;
- accounting/finance;
- public marketplace browsing;
- broad inventory ERP.

Those commerce-channel operations belong to Draneka AquaticFinder.

Breeder's responsibility ends at producing and reconciling a trustworthy, source-linked commerce handoff.

## UX gates

- Do not add a new permanent top-level navigation destination unless the bounded question cannot be answered contextually.
- Sale-ready and handoff actions should enter from existing Program, cohort, stock/candidate, selection/disposition and evidence/provenance contexts.
- Public/private selection must be explicit but not form-heavy.
- The breeder must be able to understand what will leave Breeder before handoff.
- Commercial state must remain visually distinguishable from biological state.
- Existing anti-overwhelm, uncertainty and Program-friction gates remain binding.

## Prototype-only authority

This iteration authorizes only holistic product/design prototype work and its review artifacts.

It does **not** authorize:

- Android implementation;
- web implementation;
- backend/API/schema/database mutation;
- production AquaticFinder integration;
- deployment;
- release/signing;
- marketplace integration;
- payment/order/shipping implementation;
- v1.0 scope.

## Exit criterion

A breeder can finish selection in Breeder and create a commerce-ready handoff without retyping identity, ancestry, age/timing, traits, biological quantity or photos, while AquaticFinder separately owns channel allocation and sales state.

The breeder can later understand commercial reconciliation without any loss or rewriting of biological history/provenance.

## Governance

This iteration follows `PROTOTYPE-ITERATION-WORKFLOW.md`:

1. v0.9 branch from canonical v0.8;
2. one v0.9 PR;
3. immutable candidate binding;
4. producer validation;
5. fresh independent review;
6. bounded corrections, if needed, remain in the same PR with new immutable candidate bytes;
7. Founder promotion of exact independently reviewed bytes;
8. merge to `main` is the canonicalization event.

Until those gates complete:

`HOLISTIC_V0_9_CANONICAL = NO`

`HOLISTIC_V0_8_CANONICAL = YES`
