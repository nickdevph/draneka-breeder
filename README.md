# Draneka Aquarium Breeder

Durable product/design repository for **Draneka Aquarium Breeder**.

This repository preserves reviewed prototype artifacts, product/design evidence, qualification receipts, and future implementation work for the Breeder product.

## Identity boundary

- User-facing product: **Draneka Aquarium Breeder**
- Existing technical/internal ecosystem: **AquaticFinder**
- This repository name is intentionally user-facing: `draneka-breeder`
- Existing AquaticFinder backend/internal identifiers are not renamed by this repository.

## Current prototype authorities

| Surface | Current candidate | Status |
| --- | --- | --- |
| Holistic product/design | `prototypes/holistic/v0.2/DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.2.html` | Ready for independent review |
| Android adaptation | `prototypes/android/v0.1/DRANEKA-AQUARIUM-BREEDER-ANDROID-PROTOTYPE-V0.1.html` | Ready for independent review |
| Historical holistic predecessor | `prototypes/holistic/v0.1/DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.1.html` | Historical provenance |

Prototype artifacts are versioned and should not be overwritten in place. New iterations get new version folders.

## Repository layout

```text
prototypes/
  holistic/
    v0.1/
    v0.2/
  android/
    v0.1/
research/
decisions/
reviews/
docs/
SHA256SUMS
```

Each version folder keeps the exact prototype bytes together with its receipt, qualification evidence, and version-specific notes where available.

## Authority rules

1. A prototype becomes product/design authority only through an explicit Founder/independent-review disposition.
2. A newer prototype does not silently amend an in-flight implementation cycle.
3. Holistic Breeder product semantics are defined separately from Android-specific adaptations.
4. Android adaptations may cover native navigation, system insets, Back behavior, permissions, restoration, notifications, media entry, and offline behavior without redefining the breeder domain model.
5. Journal and Breeder may share account, tank, livestock, water, media, and event identity concepts; duplicate domain events should be avoided.
6. Production backend/API/schema/database/deployment changes require a separate implementation-admission cycle.

## Current product direction

- Breeder requires a web application.
- A dedicated Android client is also being explored.
- Breeder uses a breeder-first information architecture rather than being merely a Journal tab.
- Holistic v0.2 introduces **Breeder Rounds** for fast fish-room operation while retaining contextual Quick Log, cohort accounting, lineage, and shared Journal event identity.

## Integrity

Use `SHA256SUMS` to bind prototype and evidence files to exact bytes. Do not replace files inside an existing version directory; add a new version instead.
