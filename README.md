# Draneka Aquarium Breeder

Durable product/design repository for **Draneka Aquarium Breeder**.

This repository preserves prototype authority, product/design evidence, qualification receipts, and future implementation work for the Breeder product.

## Identity boundary

- User-facing product: **Draneka Aquarium Breeder**
- Existing technical/internal ecosystem: **AquaticFinder**
- Existing AquaticFinder backend/internal identifiers are not renamed by this repository.

## Current prototype authorities

| Surface | Current authority | Status |
| --- | --- | --- |
| Holistic product/design | **v0.3 lineage** | **Founder-promoted canonical** |
| Android adaptation | Android v0.1, derived from holistic v0.2 | Historical/current Android design evidence; **not v0.3 lineage parity** |
| Holistic predecessor | v0.2 Breeder Rounds | Superseded as current holistic authority; retained for provenance |

Exact v0.3 authority binding:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.3.html`
- SHA-256: `a1432480caefa231b08435464e1bd53f606788817bd39c3738687153667548c4`
- Size: `218919 bytes`
- Durable Drive object: `1uR58MSOE3_B6P7BwTBEUHMxAaKX-pElv`
- Authority record: `prototypes/holistic/v0.3/AUTHORITY.md`
- Founder decision: `decisions/0002-promote-holistic-v0.3-lineage.md`

## Product direction locked by holistic v0.3

Breeder remains a breeder-first product with a required web application and a dedicated Android client direction. Holistic v0.3 retains Breeder Rounds and the cohort-first operating model and adds the canonical lineage loop:

`Spawn -> Cohort -> Selection -> Breeding Stock -> Pairing Check -> Next Reproductive Event`

Lineage rules include:

- ancestry is derived from recorded reproductive events rather than manually maintained;
- cohorts carry lineage;
- cohort splits preserve ancestry but do not create a new generation;
- selected/promoted breeders inherit ancestry automatically;
- Pair Builder checks known relatedness and shows common-ancestor paths;
- incomplete records use `No known common ancestor`, never a false `unrelated` claim;
- unknown sire/mother and group-spawn parentage are first-class;
- phenotype does not imply genotype;
- only a reproductive event advances ancestry/generation.

## Authority rules

1. Reviewed/promoted prototype versions are immutable; revisions use new version numbers.
2. A newer holistic prototype does not silently amend an implementation cycle.
3. Holistic product semantics are separate from client-specific Android/web adaptation details.
4. Android v0.1 cannot claim parity with holistic v0.3 until lineage convergence is explicitly performed and reviewed.
5. Journal and Breeder may share account, tank, livestock, water, media, and event identity concepts; duplicate domain events should be avoided.
6. Production backend/API/schema/database/deployment changes require a separate implementation-admission cycle.

## Current implementation state

- Breeder web production implementation: **not started/admitted by this prototype promotion**
- Breeder Android source implementation: **not started/admitted by this prototype promotion**
- Existing Journal Android implementation authority: **unchanged**

The prototype repository is product/design authority and provenance, not automatic production implementation authority.
