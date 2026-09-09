# Draneka Aquarium Breeder — Holistic v1.0 Bounded-Correction Candidate

Date: 2026-09-09
Status: **PRODUCED / PRODUCER-VALIDATED / NON-CANONICAL / PENDING FRESH INDEPENDENT RE-REVIEW**
Branch: `prototype/v1.0-simplify-and-qualify`

## Exact corrected candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0`
- MIME: `text/html`
- Exact bytes: `458038`
- SHA-256: `4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d`

The corrected candidate is a new immutable Drive object. The independently reviewed failing v1.0 object was not overwritten.

## Independently reviewed failing predecessor

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-CANDIDATE.html`
- Google Drive ID: `18egQ7iZ5jCyDJxoHQ9a1SvI2PIdfigos`
- Exact bytes: `456195`
- SHA-256: `8c65ef2f2121d71ba29d4bb7d73bf21bc7b1ad71c684df1abe458b8f477b8909`
- Independently reviewed producer head: `9c635b04259eb243e5e11e10cdf8a84453b32d41`
- Independent review receipt commit: `c6ad074c4fa15e7275fbf2cd3c6e945182383eab`
- Independent disposition: `CHANGES_REQUIRED`

## Canonical predecessor

Canonical product/design authority remains corrected holistic v0.9 until this corrected v1.0 candidate independently passes, receives Founder promotion, and PR #11 merges:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1sZ6TOO25Otne0S5Atbul6s4SRHQMnN-4`
- Exact bytes: `437576`
- SHA-256: `74b6912c393948fa3b9bf77f6dd21067cceca620f6d09747af1379791c4677b0`
- Canonical merge commit: `2b2953a62561a21cb03fcb4c42e14bf03c1cd46b`

## Bounded correction scope

This correction addresses only the five findings in the independent v1.0 receipt.

1. **V10-IR-001 — legacy reproductive-output quantity authority**
   - legacy scalar `hatched` and structured `hatches[]` are normalized into one materialized-hatch authority;
   - legacy scalar hatch quantity is subtracted from remaining reproductive output;
   - when a first new structured hatch is appended to a legacy record, the legacy scalar is preserved as an explicit baseline rather than lost or double-counted;
   - legacy hatch observations render as observed rather than `Not observed`;
   - historical reproductive outputs cannot acquire positive new commerce quantity.

2. **V10-IR-002 — Program text-search recovery**
   - zero-result live text search now uses Program terminology;
   - `Reset search and filters` is restored and returns to the default active Program list.

3. **V10-IR-003 — wide primary terminology**
   - the 1440px sidebar primary destination is `Log`, matching narrow layouts and the mandated five destinations.

4. **V10-IR-004 — 320px Commerce-history reflow**
   - long commerce schema/status/ledger content is allowed to shrink and wrap inside the sheet rather than forcing horizontal overflow.

5. **V10-IR-005 — stale Settings identity**
   - Settings identifies holistic v1.0 and the exact bounded-correction artifact.

No new breeder domain capability, biological inference, commerce domain, backend/API/schema/database authority, production implementation, Android/web release work, deployment, signing, or later-version scope is introduced.

## Producer validation boundary

The producer lane has reproduced the five failing paths against the correction and run bounded construction/runtime checks. Those checks are producer evidence only. They do not constitute independent qualification and must not be inherited by the fresh reviewer.

See:

- `prototypes/holistic/v1.0/VALIDATION.md`
- `prototypes/holistic/v1.0/BOUNDED-CORRECTION-RECEIPT.md`
- `prototypes/holistic/v1.0/BOUNDED-CORRECTION-INDEPENDENT-REVIEW-MANDATE.md`

```text
HOLISTIC_V1_0_BOUNDED_CORRECTION_CANDIDATE_PRODUCED = YES
HOLISTIC_V1_0_BOUNDED_CORRECTION_EXACT_BINDING = 458038_BYTES / 4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d
HOLISTIC_V1_0_INDEPENDENT_REVIEW = PENDING_FRESH_REREVIEW
HOLISTIC_V1_0_PROMOTION_ELIGIBLE = NO_PENDING_FRESH_INDEPENDENT_REREVIEW
HOLISTIC_V1_0_CANONICAL = NO
```