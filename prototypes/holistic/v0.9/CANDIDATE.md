# Draneka Aquarium Breeder — Holistic v0.9 Candidate

Date: 2026-09-09
Status: **PRODUCED / PRODUCER-VALIDATED / NON-CANONICAL**
PR: `#9` — Holistic v0.9 — Commerce handoff and evidence
Branch: `prototype/v0.9-commerce-handoff-evidence`

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-CANDIDATE.html`
- Google Drive ID: `1bEJ9SeXLgL4rjk1RKHmc3VQ_6njaAVxM`
- MIME: `text/html`
- Exact size: `426330 bytes`
- SHA-256: `ec434d10167bcddc8d58027d0408a73946af1d41390e419c89a93d68df10ac85`

A fresh raw Drive download reproduced the same filename, exact `426330` bytes, and SHA-256 above.

The Drive object is the immutable byte-level review target. It must not be overwritten during review or correction. Any correction must create a new immutable candidate object and new binding inside PR #9.

## Exact canonical predecessor

Holistic v0.9 was produced from repository-canonical v0.8:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1Lrdd1OX0I297hS3fBHXOSk6lmAwws3y9`
- Exact size: `391223 bytes`
- SHA-256: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`
- Canonical merge commit: `600d992e20d48f3520311d2fdcb087514d68fc95`

v0.8 remains canonical until v0.9 independently passes, receives Founder promotion, and PR #9 is merged to `main`.

## Primary product question

Can successful breeding records become sale-ready inventory and trustworthy provenance without duplicate data entry or duplicate quantity ownership?

## Candidate proof surface

### Sale-ready remains separate from biological state

The candidate adds a commerce profile layered on an existing stock, cohort, or reproductive-output record. Opening the sale-ready flow is non-mutating. Saving sale-ready state changes only the commerce profile; it does not add a biological event or change:

- count;
- ancestry;
- hatch/output provenance;
- readiness;
- Pair Builder eligibility;
- selection history;
- lifecycle state;
- Breeder Round attention.

### Explicit public/private evidence selection

The breeder explicitly selects which existing facts and media may leave Breeder. Unchecked facts remain private. Identity is required for a handoff. Unknown evidence remains unknown.

Supported evidence categories include existing identity, species, line, timing/age context, sex where applicable, traits/evaluations, selection disposition, provenance, generation evidence, output identity, biological quantity, and source-linked photos.

### Structured AquaticFinder handoff

The candidate creates a source-linked handoff with schema:

`draneka.aquaticfinder.commerce-handoff.v1`

The handoff records:

- Breeder source type and stable source ID;
- Program context;
- biological quantity snapshot;
- proposed downstream commerce quantity;
- explicitly permitted public fact snapshot;
- selected existing media IDs;
- provenance snapshot;
- optional internal handoff note.

Creating the handoff does not reserve or subtract biological quantity in Breeder.

### Separate quantity ownership

Breeder biological quantity is displayed independently from proposed/allocated/outcome commerce quantity. AquaticFinder reconciliation is represented as a separate commerce ledger.

Reconciliation may record allocation/outcome state such as Allocated, Partially sold, Sold, Returned / released, or Closed, but does not mutate the breeder biological count or ancestry/reproductive history.

### Provenance / breeding report

The candidate can preview a human-readable breeding/provenance report from existing evidence without retyping source identity, timing, traits, lineage/provenance, biological quantity or selected photos.

The report follows the same explicit public/private field permissions as the handoff and does not present private facts merely because the source is sale-ready.

### Contextual product shape

No new bottom-navigation destination is added. Commerce handoff is entered contextually from existing:

- stock/candidate detail;
- cohort/grow-out detail;
- reproductive output/batch context;
- Program context;
- selection workspace;
- More.

The bottom navigation remains:

`Today / Programs / Log / Grow-out / More`

## Required stress paths represented

- **Betta individual:** exact ancestry/evidence with explicit public/private selection and commerce handoff.
- **Medaka grouped cohort:** grouped biological quantity and hatch/output provenance without forced individualization.
- **Medaka reproductive output/batch:** remaining egg/output quantity can be a source without rewriting hatch records.
- **Neocaridina population-derived source:** handoff retains colony/population parentage uncertainty and does not fabricate exact parents.
- **Annual killifish output:** commerce preparation does not create wetting attempts, hatches or lifecycle completion.

## Canonical authority preserved

### v0.8

Commerce actions do not close or suppress operational attention. `V08-IR-001` and `V08-IR-002` remain closed in producer regression.

### v0.7

Current negative selection dispositions remain authoritative for breeding eligibility. Sale-ready state cannot restore Pair Builder eligibility. Historical readiness remains evidence only.

### v0.6

Species/provenance uncertainty remains unchanged, including population-derived and annual-killifish provenance boundaries.

### v0.5

Commerce allocation/reconciliation does not masquerade as count revision, mortality, move, split, merge, stage or feeding.

## Explicit non-scope

The candidate does not introduce:

- marketplace listing-management UI;
- channel allocation management in Breeder;
- pricing optimization;
- sales CRM;
- payment processing;
- order management;
- shipping/fulfilment;
- accounting/finance;
- public marketplace browsing;
- broad inventory ERP;
- genotype inference;
- automatic biological completion;
- backend/API/schema/database/deployment/production mutation;
- Android or web implementation authority;
- v1.0 scope.

Marketplace/channel operations remain the responsibility of Draneka AquaticFinder.

## Qualification state

Producer validation is recorded in `prototypes/holistic/v0.9/VALIDATION.md`.

`HOLISTIC_V0_9_CANDIDATE_PRODUCED = YES`

`HOLISTIC_V0_9_EXACT_BINDING = PASS`

`HOLISTIC_V0_9_DRIVE_ROUND_TRIP = PASS`

`HOLISTIC_V0_9_PRODUCER_VALIDATION = PASS`

`HOLISTIC_V0_9_READY_FOR_FRESH_INDEPENDENT_REVIEW = YES`

`HOLISTIC_V0_9_PROMOTION_ELIGIBLE = NO_PENDING_INDEPENDENT_REVIEW`

`HOLISTIC_V0_9_CANONICAL = NO`
