# Draneka Aquarium Breeder — Holistic v1.0 Independent Review Receipt

Date: 2026-09-09
Role: **Independent holistic v1.0 reviewer**
Disposition: **CHANGES_REQUIRED**

This receipt records a fresh review of the exact SHA-bound v1.0 candidate. Producer construction validation, producer runtime claims, prior PASS claims and prior usability judgments were not used as review evidence.

## 1. Exact binding

### Candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-CANDIDATE.html`
- Google Drive ID: `18egQ7iZ5jCyDJxoHQ9a1SvI2PIdfigos`
- MIME: `text/html`
- Exact bytes independently downloaded: `456195`
- Independent SHA-256: `8c65ef2f2121d71ba29d4bb7d73bf21bc7b1ad71c684df1abe458b8f477b8909`
- HTML: self-contained in static inspection; no `fetch`, XHR, WebSocket, external script/image/style URL or other outbound network target was found, apart from the SVG XML namespace.

### PR #11

At review start and again immediately before receipt creation:

- state: `open`
- draft: `true`
- merged: `false`
- base: `main`
- base SHA: `2b2953a62561a21cb03fcb4c42e14bf03c1cd46b`
- producer branch: `prototype/v1.0-simplify-and-qualify`
- exact reviewed producer head: `9c635b04259eb243e5e11e10cdf8a84453b32d41`

The producer head did not move during review.

### Canonical predecessor used for differential checks

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1sZ6TOO25Otne0S5Atbul6s4SRHQMnN-4`
- Exact bytes independently downloaded: `437576`
- Independent SHA-256: `74b6912c393948fa3b9bf77f6dd21067cceca620f6d09747af1379791c4677b0`
- canonical merge: `2b2953a62561a21cb03fcb4c42e14bf03c1cd46b`

## 2. Runtime method

Runtime qualification used Chromium `144.0.7559.96` in headless mode through Chrome DevTools Protocol.

Because the review environment blocks direct `file://`, localhost and data-URL navigation, each clean run:

1. opened a fresh `about:blank` target;
2. injected the exact independently SHA-bound HTML bytes with `Page.setDocumentContent`;
3. evaluated the exact inline script bodies extracted from those same bytes with `Runtime.evaluate` so the self-contained prototype executed;
4. set exact CSS viewport widths with device metrics;
5. exercised interactions with real Chromium mouse/keyboard input and inspected rendered layout, focus, state and console/page errors.

The tested widths were exactly `320 / 390 / 768 / 1440` CSS px.

## 3. Findings

### V10-IR-001 — BLOCKER — reproductive-output commerce quantity can double-own already materialized biological output

**Affected gates:** v0.9 authority regression, breeder usability.

**Reproduction / evidence:**

1. Open the seeded Betta `Spawn 04` reproductive-output record.
2. The record contains a historical scalar hatch observation of `84` from `100` recorded eggs, and the linked cohort was created from those 84 fry.
3. The rendered record nevertheless says `Fry hatched — Not observed`, says `100 recorded eggs remain available`, labels the source `Eligible source`, and exposes `Mark remaining output sale-ready` for quantity 100.
4. Independent recomputation is 16 remaining, not 100.
5. The same compatibility failure occurs for legacy Medaka output `m01`: 18 eggs - 2 removed - 12 already hatched = 4 remaining, while the candidate helper exposes 16.
6. Historical legacy outputs `b02` and `b03` are also allowed positive commerce quantity because the reproductive-output authority does not reject `historical=true`.
7. The newer structured-hatch output `m02` computes correctly at 15 remaining.

Independent quantity table:

| Output | Historical | Eggs | Removed | Legacy scalar hatched | Structured hatched | Independently remaining | Candidate helper | Commerce authority |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| b02 | yes | 80 | 0 | 52 | 0 | 28 | 80 | allows 80 |
| b03 | yes | 100 | 0 | 61 | 0 | 39 | 100 | allows 100 |
| b04 | no | 100 | 0 | 84 | 0 | 16 | 100 | allows 100 |
| m01 | no | 18 | 2 | 12 | 0 | 4 | 16 | allows 16 |
| m02 | no | 24 | 0 | 9 | 9 | 15 | 15 | allows 15 |

**Root boundary:** `hatchRecords`/remaining-output authority consumes structured `hatches[]` but not legacy scalar `hatched`, while the spawn/reproductive-output commerce authority has no historical-source rejection.

The same legacy-compatibility behavior is reproducible in the canonical v0.9 predecessor; therefore this is not claimed as a newly introduced v1.0 code regression. It still fails the v1.0 mandate's required independent re-run of corrected v0.9 commerce authority and is promotion-blocking because v1.0 cannot be qualified while exposing conflicting/current positive quantity ownership.

### V10-IR-002 — MAJOR — Program search empty-state recovery disappears

**Affected gates:** discoverability, recovery, terminology.

**Reproduction:**

1. Open Programs.
2. Type a search that returns zero Programs.
3. Instead of the v1.0 recovery action `Reset search and filters`, the rendered result is the older `No matching projects` / `Try another project name or species` state.
4. The reset action is absent and terminology regresses from `Programs` to `projects`.

Status-filter empty recovery independently retains `Reset search and filters`, and Grow-out filtered-empty recovery independently retains `Show all groups`.

### V10-IR-003 — MAJOR — wide primary-navigation nomenclature does not match the required five destinations

**Affected gates:** simplification, mobile/web parity, terminology.

**Reproduction:**

- At `320 / 390 / 768`, rendered primary navigation is exactly `Today / Programs / Log / Grow-out / More`.
- At `1440`, the desktop primary sidebar is `Today / Programs / Quick Log / Grow-out / More`.

The action still opens Quick Log in one click, but the mandate requires the primary destination label itself to be exactly `Log` at every width.

### V10-IR-004 — MAJOR — Commerce evidence history dialog horizontally overflows at 320 px

**Affected gates:** accessibility/reflow, responsive matrix.

**Reproduction:**

1. At exact width `320`, open a source record, prepare commerce evidence, then open `Commerce evidence history`.
2. Document-level overflow remains zero, but the dialog sheet has `scrollWidth - clientWidth = 18px` horizontal overflow.
3. The same dialog has zero horizontal overflow at `390 / 768 / 1440`.
4. The overflow is driven by the long commerce-handoff schema/status content not fully reflowing inside the narrow sheet.

### V10-IR-005 — MINOR — Settings retains stale prototype version text

**Affected gate:** terminology/qualification clarity.

At every tested width Settings renders `Version 0.2 · candidate for independent product/design review` even though the bound artifact is holistic v1.0.

## 4. Simplification, discoverability and task cost

The candidate does materially simplify the structure:

- Today focuses on daily attention, active Programs and the Journal connection.
- More groups existing capabilities by job.
- No standalone permanent Commerce destination appears in More.
- Commerce evidence remains contextual from eligible source records.
- Program `Tools` exposes the expected existing capability without introducing a new authority domain.
- No removed redundant surface made the checked canonical capabilities unreachable.

However exact wide primary nomenclature and Program-search recovery fail the mandatory contract, so simplification/discoverability cannot pass overall.

Actual interaction counts from clean state at every tested width:

| Task | Actual actions | Target | Result |
|---|---:|---:|---|
| Global primary Log -> Quick Log | 1 | 1 | PASS |
| Today -> Start Breeder Round | 1 | 1 | PASS |
| Program heading -> Program-context Quick Log | 1 | 1 | PASS |
| Grow-out -> existing active group | 2 | <=2 | PASS |
| More -> Pair Builder | 2 | <=2 | PASS |
| Source record -> sale-ready/public evidence | contextual direct source flow | no commerce dashboard first | PASS |

## 5. Empty/error/recovery

Independently exercised:

- Program search no-results -> **FAIL** as V10-IR-002.
- Program status no-results -> reset path works.
- Grow-out stage no-results -> `Show all groups` works.
- missing/unavailable route -> Today and Programs recovery works without mutation.
- real split -> source becomes historical/zero, descendants retain source output, exact quantity conservation holds, matching planned split alone becomes Executed.
- real merge -> quantity conserved; prior groups become historical; merged group retains both source group IDs, reproductive-output ID and hatch IDs; historical record routes to merged descendant.
- completed Program logging -> recovery to current living Grow-out remains available.
- zero-quantity historical cohort -> positive commerce handoff remains blocked while provenance/reporting remains available; forced stale sale-ready profile still cannot create a handoff.
- invalid commerce reconciliation outcome greater than allocated quantity -> visible/assertive alert appears and no reconciliation or unrelated biological mutation occurs.

## 6. Accessibility

Independently exercised in Chromium:

- visible `3px` keyboard focus treatment is present on primary/common controls;
- the v1.0 `Skip to main content` control becomes visible on keyboard focus and moves focus to `MAIN#main`;
- common actions/forms are keyboard reachable;
- modal opening focuses inside the dialog, makes background app inert, uses `role=dialog`/`aria-modal=true`, traps traversal inside representative modal content, closes with Escape, removes inertness and returns focus to the invoking `Log` control;
- logical form errors are visible and expose `role=alert` plus `aria-live=assertive`;
- representative Today, Programs, Grow-out, More, Program Tools, commerce evidence, Pair Builder and Settings headings/labels are understandable;
- no representative keyboard trap was found;
- primary/navigation/common action targets met 44px intent except the inline `See all` control measured approximately `42.8 x 44px`;
- the Commerce evidence history dialog also fails narrow reflow at 320px as V10-IR-004.

Because the mandatory target/reflow qualification is not fully met, the accessibility gate is FAIL even though focus, skip, modal and error-announcement behavior otherwise passed.

## 7. Mobile/web parity and terminology

Authority-bearing surfaces remain available on both narrow and wide layouts; no desktop-only biological/commerce authority was observed. The exact primary naming requirement fails at 1440 (`Quick Log` vs `Log`), Program search falls back to `projects`, and Settings contains stale `Version 0.2` text. Therefore parity/terminology do not pass.

## 8. Independent breeder usability

Representative workflows were completed without using producer validation as a guide:

- **Betta:** Program/lineage, selection/disposition, Pair Builder, retained stock, sale-ready/public evidence and handoff were navigable. Selection and Pair Builder authority held. The Spawn 04 output view is not trustworthy because it simultaneously carries an 84-fry historical hatch/cohort record yet tells the breeder hatch was not observed and 100 eggs remain sale-ready.
- **Medaka:** repeated collections, multi-hatch records, grouped offspring and merge provenance were preserved. New structured batch `m02` computes remaining quantity correctly, but legacy batch `m01` presents 16 remaining instead of 4.
- **Neocaridina:** population/colony provenance and selection were preserved without invented exact parents or a fabricated controlled-generation label.
- **Annual killifish:** first wetting, re-dry, second wetting and explicit observed hatch remained distinct; wetting did not imply hatch and hatch provenance bound to the actual wetting attempt.

Because Betta/Medaka source records visibly contradict known biological materialization and expose excess commerce quantity, independent breeder usability is FAIL.

## 9. Canonical v0.9 authority re-run

### Passed v0.9 paths

- selected/public media only appears in public facts, report and handoff;
- injected private/unselected source media did not leak;
- explicit empty media selection stayed empty in public facts/report/handoff;
- historical zero-quantity offspring groups are blocked from positive commerce quantity;
- `Non-breeding`, `Retire`, and `Sale / rehome` override historical readiness for breeding-stock/Pair Builder authority;
- `Holdback` remains readiness-neutral;
- stale Pair Builder parent selection recovers to an eligible parent and the now-ineligible stock disappears from options;
- commerce reconciliation changes commerce status/allocation/outcome records without mutating biological quantity, ancestry, cohorts, source outputs, selection sessions or unrelated biological events;
- invalid reconciliation is mutation-safe.

### Failed v0.9 path

- reproductive-output singular quantity ownership fails for legacy scalar hatch fixtures and historical reproductive outputs as V10-IR-001.

Therefore the mandatory v0.9 regression/authority gate is FAIL.

## 10. Canonical v0.8 regression

PASS. Independently verified:

- count revision, mortality, feeding and stage change do not execute a planned split;
- only the matching real split executes the matching Grow-out plan;
- unrelated observations do not close lifecycle dependencies;
- wetting does not imply hatch;
- schedule completion, deferral and skip remain operational and do not fabricate biological events;
- known/unknown capacity context remains evidence-bounded;
- culture dependency state remains operational and does not imply feeding.

## 11. Canonical v0.7 regression

PASS. Independently verified:

- current negative dispositions control breeding eligibility;
- stale Pair Builder parents recover safely;
- goal history appends without rewriting prior snapshots;
- phenotype observation does not infer genotype;
- controlled Betta parentage/generation remains precise;
- Neocaridina population-derived selection keeps exact parents empty and generation unestablished;
- merge/selection boundaries remain Program-scoped.

## 12. Canonical v0.6 regression

PASS. Independently verified representative:

- Betta exact controlled pair parentage;
- guppy mother-known/sire-unknown uncertainty;
- Medaka multiple-hatch provenance and hatch-ID retention through merge;
- Neocaridina population provenance without invented parents;
- annual-killifish wetting/re-dry/wetting/hatch semantics;
- mop/plant collection creates reproductive output without automatic hatch.

## 13. Canonical v0.5 regression

PASS. Independently exercised representative biological operations:

- count revision changes adjustment rather than mortality;
- mortality changes loss accounting separately;
- feeding leaves quantity unchanged;
- stage change preserves quantity/provenance;
- whole-group move preserves group identity/provenance;
- split conserves quantity and preserves source output;
- merge conserves quantity and retains provenance;
- historical sources are blocked from ordinary biological mutation.

## 14. Responsive/runtime matrix

| Width | `window.innerWidth` | Document horizontal overflow | Relevant dialog overflow | Page/console errors | Result |
|---:|---:|---:|---:|---|---|
| 320 | 320 | 0 | Commerce evidence history: 18px | none observed | FAIL |
| 390 | 390 | 0 | 0 | none observed | PASS |
| 768 | 768 | 0 | 0 | none observed | PASS |
| 1440 | 1440 | 0 | 0 | none observed | FAIL — primary label is `Quick Log` |

Representative Today, Programs, Log, Grow-out, More, Program Tools, Pair Builder, sale-ready/public evidence, handoff/reconciliation, recovery and Settings surfaces were exercised at every width.

## 15. Scope discipline

PASS.

PR #11 changes only:

- `prototypes/holistic/v1.0/CANDIDATE.md`
- `prototypes/holistic/v1.0/INDEPENDENT-REVIEW-MANDATE.md`
- `prototypes/holistic/v1.0/ITERATION.md`
- `prototypes/holistic/v1.0/VALIDATION.md`

No marketplace management, pricing optimization, CRM, payment/order/shipping/fulfilment, finance/accounting, public marketplace browsing, broad ERP, genotype inference, automatic breeding-pair authority, backend/API/schema/database change, Android/web production implementation, deployment/release or v1.1+ scope was introduced or authorized by the reviewed candidate/PR.

## 16. Production implementation-admission matrix

| Area | Prototype behavior independently proven? | Canonical authority source | Production implementation exists? | Additional implementation/qualification required | Admission disposition |
|---|---|---|---|---|---|
| Navigation / screen hierarchy | PARTIAL — task cost passes; wide label and search recovery fail | v1.0 candidate constrained by canonical v0.9 | Not established by this review | Correct v1.0 findings; then production UI implementation + responsive QA | HOLD |
| Breeder data model semantics | PARTIAL — v0.5-v0.8 semantics hold; reproductive-output quantity compatibility fails | canonical v0.9-v0.5 | Not established | Normalize legacy/current output authority; production model/API tests | HOLD |
| Biological operations | YES for tested prototype paths | canonical v0.5 plus later preserved authority | Not established | Separate production implementation and mutation/conservation qualification | NOT ADMITTED |
| Lineage / provenance | YES for representative Betta/guppy/Medaka/Neocaridina/killifish paths | canonical v0.6-v0.7 | Not established | Separate production persistence/API/UI provenance qualification | NOT ADMITTED |
| Selection / Pair Builder | YES for tested disposition/stale-parent/uncertainty paths | canonical v0.7 and corrected v0.9 disposition boundary | Not established | Separate production implementation + eligibility regression tests | NOT ADMITTED |
| Breeder Round / scheduling | YES for tested operational semantics | canonical v0.8 | Not established | Separate production scheduler/notification/state implementation qualification | NOT ADMITTED |
| Commerce handoff / public evidence | PARTIAL — privacy projection/reconciliation pass; quantity authority fails | corrected canonical v0.9 | Not established | Fix quantity ownership; then implement + qualify API/authz/public projection/reconciliation | HOLD |
| Accessibility | PARTIAL — focus/skip/dialog/error semantics pass; 320 reflow and one sub-44px inline target fail | v1.0 qualification requirements | Not established | Correct findings; production WCAG/keyboard/touch/reflow testing | HOLD |
| Android parity | Prototype is not Android implementation evidence | separate Android implementation authority | Not established by this review | Implement separately and qualify Android UX/data/authority parity | NOT ADMITTED |
| Web parity | Prototype cross-width behavior partly proven only | v1.0 prototype design authority after correction/promotion | Not established by this review | Production web implementation + browser/responsive/accessibility QA | NOT ADMITTED |
| Backend / API / schema / database | No production behavior claimed | separate backend authority | Not established | Explicit architecture, migrations/contracts, data-integrity/security tests | NOT ADMITTED |
| AquaticFinder integration | Prototype handoff boundary only; no live integration | canonical v0.9 commerce contract boundary | Not established | Production API/integration, identity/authorization, failure/retry and reconciliation qualification | NOT ADMITTED |
| Production security / privacy | Prototype projection semantics only; selected/private media gate tested | canonical v0.9 privacy/evidence boundary | Not established | Authn/authz, tenant isolation, storage/transport/logging/privacy/security review | NOT ADMITTED |
| Deployment / release | No | separate release authority | No evidence in this review | Build/sign/deploy/release gates and operational qualification | NOT ADMITTED |

The implementation-admission evidence requirement itself is satisfied by this matrix. It does not grant production authority.

## 17. Smallest bounded correction

Do not redesign or expand scope. The smallest bounded correction is:

1. **Reproductive-output quantity compatibility/authority:** make one authoritative remaining-output calculation cover both legacy scalar `hatched` records and structured `hatches[]`; subtract already materialized hatch quantity everywhere the current remaining quantity is rendered/reported/handoff-eligible; reject historical reproductive outputs from positive new commerce quantity. Re-run at least `b02 / b03 / b04 / m01 / m02` plus public/private evidence and reconciliation gates.
2. **Programs empty-search recovery:** retain v1.0 Program terminology and a visible `Reset search and filters` action when text search returns zero results.
3. **Wide primary label:** render exact primary destination `Log`, not `Quick Log`, at 1440/wide layout.
4. **320 commerce-history reflow:** make Commerce evidence history contents wrap/reflow with zero horizontal sheet overflow at 320px; preserve keyboard/focus behavior.
5. **Qualification text:** update stale Settings `Version 0.2` text to the exact v1.0 candidate identity/version.
6. Re-run the mandatory affected gates plus the full required responsive matrix on a newly bound corrected artifact/head.

No implementation of these corrections was performed by the reviewer.

## 18. Final gate state

```text
HOLISTIC_V1_0_EXACT_BINDING = PASS
HOLISTIC_V1_0_SIMPLIFICATION = FAIL
HOLISTIC_V1_0_DISCOVERABILITY = FAIL
HOLISTIC_V1_0_INTERACTION_COST = PASS
HOLISTIC_V1_0_RECOVERY = FAIL
HOLISTIC_V1_0_ACCESSIBILITY = FAIL
HOLISTIC_V1_0_MOBILE_WEB_PARITY = FAIL
HOLISTIC_V1_0_TERMINOLOGY = FAIL
HOLISTIC_V1_0_BREEDER_USABILITY = FAIL
HOLISTIC_V1_0_V0_9_REGRESSION = FAIL
HOLISTIC_V1_0_V0_8_REGRESSION = PASS
HOLISTIC_V1_0_V0_7_REGRESSION = PASS
HOLISTIC_V1_0_V0_6_REGRESSION = PASS
HOLISTIC_V1_0_V0_5_REGRESSION = PASS
HOLISTIC_V1_0_RESPONSIVE_MATRIX = FAIL
HOLISTIC_V1_0_SCOPE_DISCIPLINE = PASS
HOLISTIC_V1_0_IMPLEMENTATION_ADMISSION_EVIDENCE = PASS
HOLISTIC_V1_0_INDEPENDENT_REVIEW = CHANGES_REQUIRED
HOLISTIC_V1_0_PROMOTION_ELIGIBLE = NO
HOLISTIC_V1_0_CANONICAL = NO_PENDING_FOUNDER_PROMOTION_AND_MERGE
```

Final disposition: **CHANGES_REQUIRED**.
