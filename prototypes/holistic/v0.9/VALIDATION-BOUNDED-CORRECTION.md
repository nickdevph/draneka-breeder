# Draneka Aquarium Breeder — Holistic v0.9 Bounded Correction Producer Validation

Date: 2026-09-09
Candidate: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-BOUNDED-CORRECTION-CANDIDATE.html`
Drive ID: `1OQqLK4aovt4RAfAdKxFnn9n-VB-nUaEX`
Bytes: `437100`
SHA-256: `21736560a33f7ab7a42b46c7691b690b9fb7336638c8fec616da30af345d4327`

Producer validation is not independent-review evidence.

## Exact binding

- local candidate: `437100` bytes;
- local SHA-256: `21736560a33f7ab7a42b46c7691b690b9fb7336638c8fec616da30af345d4327`;
- fresh raw Drive re-download: `437100` bytes;
- raw Drive SHA-256: exact match;
- JavaScript syntax (`node --check`): PASS.

## V09-IR-001 direct reproduction

Fresh Betta source cohort `cb` began at 76. A canonical `76 = 30 + 46` split was saved so the original source became historical, inactive and count `0`.

Observed on corrected bytes:

- `v09CommerceQuantityAuthority('cohort','cb').allowed=false`;
- opening sale-ready does not create a profile;
- rendered explanation states that no sale-ready quantity is owned by the historical source;
- a deliberately injected stale sale-ready profile cannot expose a handoff quantity form;
- no positive handoff can be saved from the zero/historical source.

Result: **PASS — V09-IR-001 closed in producer validation.**

## V09-IR-002 direct reproduction

Fresh Neocaridina state contains historical reproductive output `s01` and current descendant cohort `cs`.

Observed:

- current cohort `cs` is eligible as the current biological quantity owner;
- reproductive output `s01` is not eligible as a concurrent commerce quantity owner;
- sale-ready quantity UI does not open for `s01`;
- the historical output remains available for provenance/reporting context.

Result: **PASS — duplicate materialized-source ownership blocked.**

## Distinct remaining egg quantity remains valid

Fresh Medaka output `m02` contains 24 recorded eggs and 9 hatched, leaving exactly 15 current unhatched/unmaterialized eggs.

Observed:

- `v09CommerceQuantityAuthority('spawn','m02').allowed=true`;
- authority quantity = `15`;
- a handoff for `2` records `biologicalQuantitySnapshot=15` and `proposedCommerceQuantity=2`;
- original egg count, hatch totals and hatch records remain unchanged.

Result: **PASS — remaining eggs are a distinct current quantity owner rather than duplicate hatched-fish inventory.**

## V09-IR-003 selection contextual entry

Fresh Atlas selection session recorded `Sale / rehome` with a breeder reason.

Observed:

- current disposition = `Sale / rehome`;
- Pair Builder eligibility remains false;
- selection workspace renders `Sale / rehome → commerce-ready handoff`;
- marking the animal sale-ready does not restore breeding eligibility.

Result: **PASS.**

## Privacy/evidence boundary

Fresh Atlas sale-ready flow explicitly kept `Sex` private and saved a commerce handoff with an internal note.

Observed:

- private `Sex` absent from public facts;
- internal handoff note not exposed as a public fact;
- source identity/provenance remain traceable.

Result: PASS.

## Source-linked media hardening

An unrelated media item sharing only Program identity was added in a fresh state. It was not offered as output-specific media for Betta output `b04`.

Result: PASS.

## Canonical v0.8 former-defect regressions

### V08-IR-001

Fresh Betta count revision `76 → 75`, explicitly with no split/move, left grow-out plan `gp-betta-1` in `Planned` state.

Result: PASS.

### V08-IR-002

Fresh Rachovii wetting action was opened then cancelled. A later unrelated detailed Betta feeding left the lifecycle prompt unresolved and created no wetting attempt/hatch.

Result: PASS.

## Responsive/runtime matrix

Browser: Chromium `144.0.7559.96` on Debian GNU/Linux 13.

The exact corrected HTML bytes were exercised at exact CSS widths across representative canonical and corrected commerce surfaces.

| Width | Applied | Document/body overflow | Relevant sheet overflow | Page errors | Console errors |
|---:|---:|---:|---:|---:|---:|
| 320 | 320 | 0 | 0 | 0 | 0 |
| 390 | 390 | 0 | 0 | 0 | 0 |
| 768 | 768 | 0 | 0 | 0 | 0 |
| 1440 | 1440 | 0 | 0 | 0 | 0 |

Result: PASS.

## Scope discipline

No marketplace listing/channel management, pricing optimization, CRM, payment, order, shipping, finance/accounting, public marketplace, broad inventory ERP, backend/API/schema/database/deployment/production mutation, Android/web implementation authority, genotype inference, automatic biological completion or v1.0 scope was introduced.

Result: PASS.

```text
V09_IR_001_PRODUCER_REPRODUCTION = PASS
V09_IR_002_PRODUCER_REPRODUCTION = PASS
V09_IR_003_PRODUCER_REPRODUCTION = PASS
HOLISTIC_V0_9_BOUNDED_CORRECTION_EXACT_BINDING = PASS
HOLISTIC_V0_9_BOUNDED_CORRECTION_PRODUCER_VALIDATION = PASS
HOLISTIC_V0_9_BOUNDED_CORRECTION_RESPONSIVE_SMOKE = PASS
HOLISTIC_V0_9_READY_FOR_FRESH_REVIEW = YES
HOLISTIC_V0_9_CANONICAL = NO
PR_9_MERGE = HOLD
```

The fresh reviewer must independently reproduce both prior BLOCKERs, the contextual defect, all v0.9 authority gates, the full canonical v0.8/v0.7/v0.6/v0.5 regression chain and exact-width runtime matrix on the new exact bytes.
