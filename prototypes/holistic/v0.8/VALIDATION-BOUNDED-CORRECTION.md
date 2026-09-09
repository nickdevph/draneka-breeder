# Draneka Aquarium Breeder — Holistic v0.8 Bounded Correction Producer Validation

Date: 2026-09-08
Candidate: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-BOUNDED-CORRECTION-CANDIDATE.html`
Drive ID: `1Lrdd1OX0I297hS3fBHXOSk6lmAwws3y9`
Bytes: `391223`
SHA-256: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`

Producer validation is not independent review evidence.

## Exact binding

- Local frozen candidate: `391223` bytes.
- Local SHA-256: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`.
- Drive metadata: `391223` bytes.
- Raw Drive re-download: `391223` bytes.
- Raw Drive re-download SHA-256: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`.
- JavaScript syntax (`node --check` on extracted script): PASS.

## V08-IR-001 targeted reproduction

Fresh seed state:

- Betta cohort `cb` starts at `76` in tank `tb`.
- `gp-betta-1` is `Planned` for an explicit split of `30` to `tr2`.

Reproduced the reviewer path through the rendered count-revision form:

1. Recorded `76 → 75`.
2. Reason: `Full recount; no move or split occurred`.
3. Saved event type remained `count`.
4. Event text explicitly retained the `-1` as an unexplained count revision, not mortality.
5. Cohort remained active in `tb` with count `75`.
6. Grow-out plan remained `Planned`.
7. No `Executed` history was appended.

Result: **PASS — V08-IR-001 reproduction closed.**

Fresh seed matching-operation check:

1. Opened the canonical split form on the planned source cohort.
2. Saved an explicit `30 + 46 = 76` split.
3. The 30-animal child was placed in planned target `tr2`.
4. Source became historical.
5. Both children retained source-output provenance.
6. Only then did the plan become `Executed`.
7. Execution history records the exact matching split event ID and plan target/quantity.

Result: **PASS — intended plan execution still works only from matching canonical mutation.**

## V08-IR-002 targeted reproduction

Fresh seed state:

1. Opened lifecycle prompt `life-killi-wet`.
2. Chose `Record wetting attempt`.
3. Confirmed the specialized wetting form opened with pending intent for that exact prompt/type.
4. Cancelled the wetting form.
5. Confirmed pending lifecycle intent was cleared.
6. Recorded an unrelated detailed Betta feed event.
7. Rachovii lifecycle prompt remained `done=false`.
8. No lifecycle-history resolution entry was created.

Result: **PASS — V08-IR-002 reproduction closed.**

Matching-record check:

1. Reopened `life-killi-wet` → `Record wetting attempt`.
2. Saved an explicit Rachovii wetting observation against `p6` / `k01`.
3. Exactly one wetting attempt was created.
4. No hatch was created.
5. Lifecycle prompt became done only after that matching wetting record.
6. Lifecycle history linked the exact wetting event ID and recorded that the event matched the prompt context.

Result: **PASS — intended lifecycle resolution remains functional.**

## Canonical regression smoke

### v0.7 Pair Builder authority

Using rendered selection-session flow, ready Atlas was set to `Non-breeding` with an explicit reason.

- historical `ready=true` remained;
- `breedingStockSelectable(Atlas)=false`;
- `pairBuilderEligible(Atlas)=false`;
- Atlas was absent from Pair Builder options;
- requested stale Atlas selection normalized to currently eligible parents.

Result: PASS.

### v0.6 annual-killifish provenance

Fresh sequence:

1. wetting attempt 1;
2. re-dry attempt 1;
3. wetting attempt 2;
4. explicit 7-fry hatch linked to attempt 2.

Observed:

- two distinct wetting attempt IDs;
- attempt 1 remained `re-dried` with no hatch IDs;
- attempt 2 received the hatch ID;
- resulting hatch record and cohort retained attempt-2 provenance.

Result: PASS.

### v0.5 count/mortality separation

Fresh Betta cohort:

- count revision `76 → 75` produced a `count` event and did not add mortality;
- explicit mortality of `2` then produced a `mortality` event, count `75 → 73`, and loss ledger increased by exactly 2.

Result: PASS.

The first independent review already passed the broader canonical v0.7/v0.6/v0.5 matrix. The fresh reviewer must still rerun the mandated regressions on the new exact bytes; this producer smoke does not replace that review.

## Responsive/runtime correction matrix

Browser: Chromium `144.0.7559.96` on Debian GNU/Linux 13.

The exact corrected HTML bytes were loaded into Chromium and the corrected grow-out and lifecycle sheets were exercised at exact CSS widths:

| Width | Applied | Document/body overflow | Corrected sheet overflow | Page errors | Console errors |
|---:|---:|---:|---:|---:|---:|
| 320 | 320 | 0 | 0 | 0 | 0 |
| 390 | 390 | 0 | 0 | 0 | 0 |
| 768 | 768 | 0 | 0 | 0 | 0 |
| 1440 | 1440 | 0 | 0 | 0 | 0 |

Result: PASS.

## Scope discipline

No new product scope was introduced. The correction changes only how an existing operational plan/prompt is permitted to transition to resolved/executed state.

- No automatic biological completion.
- No automatic move/split/selection/cull/sale/rehome authority.
- No genotype inference.
- No generic task-management/ERP surface.
- No v0.9 commerce workflow.
- No backend/API/schema/database/deployment/production mutation.
- No Android/web implementation authority.

Result: PASS.

```text
V08_IR_001_PRODUCER_REPRODUCTION = PASS
V08_IR_002_PRODUCER_REPRODUCTION = PASS
HOLISTIC_V0_8_BOUNDED_CORRECTION_EXACT_BINDING = PASS
HOLISTIC_V0_8_BOUNDED_CORRECTION_PRODUCER_VALIDATION = PASS
HOLISTIC_V0_8_BOUNDED_CORRECTION_RESPONSIVE_SMOKE = PASS
HOLISTIC_V0_8_BOUNDED_CORRECTION_READY_FOR_FRESH_REVIEW = YES
HOLISTIC_V0_8_CANONICAL = NO
PR_8_MERGE = HOLD
```