# Draneka Aquarium Breeder — Holistic v0.9 Second Bounded-Correction Receipt

Date: 2026-09-09
Status: **PRODUCED / PRODUCER-VALIDATED / NON-CANONICAL / PENDING FRESH INDEPENDENT RE-REVIEW**

## Why this receipt exists

A true independent review performed after the historical merge of PR #9 found one previously missed promotion blocker:

`V09-TIR-001 — BLOCKER — private-data exposure`

The review-only receipt is preserved on branch `review/holistic-v0.9-true-independent-2026-09-09` at commit `4e1bf8e392948e78266752a2a13956e503a8291a`.

The historical merge at `80ce9259966ca2600a0c35f4633bbec4016329f3` is therefore governance history only for this correction. It is not treated as qualification evidence. `main` is intentionally not changed by this producer correction.

Because PR #9 is already merged and cannot continue as the active correction container, this branch/PR is an exceptional post-merge remediation for the same v0.9 product scope. It does not create v1.0 scope.

## Exact failing review target rebound before correction

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1OQqLK4aovt4RAfAdKxFnn9n-VB-nUaEX`
- MIME: `text/html`
- Exact bytes: `437100`
- SHA-256: `21736560a33f7ab7a42b46c7691b690b9fb7336638c8fec616da30af345d4327`

The raw Drive object was downloaded again before editing and independently reproduced that exact byte count and SHA-256.

## Exact corrected candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1sZ6TOO25Otne0S5Atbul6s4SRHQMnN-4`
- MIME: `text/html`
- Exact bytes: `437576`
- SHA-256: `74b6912c393948fa3b9bf77f6dd21067cceca620f6d09747af1379791c4677b0`

The corrected object was uploaded as a new immutable Drive file in the same Drive area as the reviewed predecessor. A fresh raw Drive download reproduced the exact `437576` bytes and SHA-256 above.

The failing Drive object was not overwritten.

## Bounded defect and correction

### Failing behavior

The v0.9 commerce profile correctly stored only explicitly selected media IDs, and the handoff `mediaIds` were also correctly filtered. However, the human-readable `photos` public fact called `v09MediaFor(kind,id)` directly and therefore concatenated captions from **all source-linked media**.

That allowed metadata from an unchecked/private photo to appear in:

- `publicFacts.photos`;
- the rendered public handoff preview;
- the generated breeding/provenance report.

### Correction

The correction stays entirely inside the v0.9 public-evidence projection layer:

1. Added `v09SelectedMediaFor(kind,id,mediaIds)` so a supplied media permission set is intersected with the source-linked media set.
2. Extended `v09FactValue` with an optional media-permission scope. `photos` now derives captions only from explicitly permitted IDs when a permission scope is supplied.
3. `v09PublicSnapshot` now always projects photo metadata through the commerce profile's explicit `mediaIds`.
4. `v09ReportMarkup` now uses the profile's explicit `mediaIds` whenever a commerce profile exists, while preserving all-media behavior only for an internal report with no commerce profile/permission context.
5. Reopening a saved profile with an intentionally empty `mediaIds` set now preserves that empty selection instead of default-checking every source-linked photo.
6. Corrected stale HTML metadata so the document title and description identify holistic v0.9 commerce handoff/evidence and this second bounded correction.

No biological quantity, ancestry, provenance, hatch/output, lifecycle, selection, readiness, Pair Builder, operational-attention, reconciliation, navigation, marketplace-scope, backend/API/schema/database, Android/web implementation, deployment, or release logic was changed.

## Producer reproduction and validation

Real headless Chromium was used against both the exact failing bytes and the corrected bytes.

Test setup used two Atlas source-linked media records:

- `PUBLIC SELECTED PHOTO CAPTION`
- `PRIVATE UNSELECTED PHOTO CAPTION`

The commerce profile enabled public facts `identity`, `provenance`, `quantity`, and `photos`, while `mediaIds` permitted only the public photo.

### Failing candidate reproduced

Observed on SHA-256 `21736560...d4327`:

- profile media permission: selected ID only;
- handoff `mediaIds`: selected ID only;
- `publicFacts.photos`: included the selected caption **and** the private/unselected caption;
- rendered handoff preview: included the private/unselected caption;
- provenance report: included the private/unselected caption.

This independently reproduces `V09-TIR-001` before correction.

### Corrected candidate

Observed on SHA-256 `74b6912c...c4677b0`:

- profile media permission: selected ID only;
- handoff `mediaIds`: selected ID only;
- `publicFacts.photos`: exactly `PUBLIC SELECTED PHOTO CAPTION`;
- rendered handoff preview: private caption absent;
- saved handoff public facts: private caption absent;
- provenance report: private caption absent;
- explicitly saved empty media permission set reopens with `0` media checkboxes selected;
- zero page errors;
- zero console errors.

Targeted responsive checks of the corrected sale-ready/privacy path were run at exact CSS widths:

- `320`
- `390`
- `768`
- `1440`

At each width:

- `window.innerWidth` matched the requested width;
- document horizontal overflow = `0`;
- relevant rendered sheet/dialog horizontal overflow = `0`.

## Preserved authority

This producer correction does not reopen or redesign the product model. The previous true independent review found the following independently intact on the failing candidate, and this patch does not modify their implementation paths:

- `V09-IR-001` zero/historical quantity authority;
- `V09-IR-002` materialized-source duplicate quantity ownership;
- `V09-IR-003` Sale / rehome contextual commerce entry;
- sale-ready versus biological authority;
- biological/provenance authority boundaries;
- separate commerce quantity ownership and reconciliation;
- selection/Pair Builder authority;
- holistic v0.8, v0.7, v0.6, and v0.5 behavior;
- contextual commerce scope and anti-overwhelm shape.

Those findings are **not inherited as a new independent PASS** by this producer receipt. The fresh re-review must establish the corrected candidate's result independently.

## Producer gate state

```text
V09_TIR_001_PRODUCER_REPRODUCTION = PASS
V09_TIR_001_PRODUCER_CORRECTION = PASS
V09_TIR_001_PRIVATE_CAPTION_IN_PUBLIC_FACT = ABSENT
V09_TIR_001_PRIVATE_CAPTION_IN_HANDOFF_PREVIEW = ABSENT
V09_TIR_001_PRIVATE_CAPTION_IN_SAVED_HANDOFF = ABSENT
V09_TIR_001_PRIVATE_CAPTION_IN_PROVENANCE_REPORT = ABSENT
V09_TIR_001_EXPLICIT_EMPTY_MEDIA_PERMISSION = PRESERVED

HOLISTIC_V0_9_SECOND_BOUNDED_CORRECTION_EXACT_BINDING = PASS
HOLISTIC_V0_9_SECOND_BOUNDED_CORRECTION_DRIVE_ROUND_TRIP = PASS
HOLISTIC_V0_9_SECOND_BOUNDED_CORRECTION_TARGETED_RESPONSIVE = PASS
HOLISTIC_V0_9_SECOND_BOUNDED_CORRECTION_PRODUCER_VALIDATION = PASS
HOLISTIC_V0_9_READY_FOR_FRESH_INDEPENDENT_REREVIEW = YES
HOLISTIC_V0_9_PROMOTION_ELIGIBLE = NO_PENDING_FRESH_INDEPENDENT_REREVIEW
HOLISTIC_V0_9_CORRECTED_CANONICAL = NO
```

## Authority boundary

This correction changes only holistic prototype candidate bytes and correction/review governance evidence. It does not authorize production implementation, backend/API/schema/database changes, marketplace execution, deployment, Android/web release work, signing, or v1.0+ scope.
