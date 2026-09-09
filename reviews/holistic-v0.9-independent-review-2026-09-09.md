# Draneka Aquarium Breeder — Holistic v0.9 Independent Review

Date: 2026-09-09
Disposition: **CHANGES_REQUIRED**

## Review authority and custody

This review was performed freshly against the exact Drive candidate. Producer validation, PR prose and candidate receipts were not treated as product evidence.

Repository: `nickdevph/draneka-breeder`

PR: `#9 — Holistic v0.9 — Commerce handoff and evidence`

Exact pre-receipt PR head exercised:

`f13d91638ef9e98ef41c4471c8f9e53a4c4bea33`

Base remained canonical v0.8 `main`:

`600d992e20d48f3520311d2fdcb087514d68fc95`

PR #9 remained open and unmerged throughout review.

## Exact v0.9 candidate binding

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-CANDIDATE.html`

Google Drive ID:

`1bEJ9SeXLgL4rjk1RKHmc3VQ_6njaAVxM`

Independent raw retrieval and local measurement:

- MIME: `text/html`
- bytes: `426330`
- SHA-256: `ec434d10167bcddc8d58027d0408a73946af1d41390e419c89a93d68df10ac85`

Result: **PASS — exact binding.**

## Canonical v0.8 predecessor binding

Artifact:

`DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.8-OPERATIONAL-SCALE-BOUNDED-CORRECTION-CANDIDATE.html`

Google Drive ID:

`1Lrdd1OX0I297hS3fBHXOSk6lmAwws3y9`

Independent raw retrieval and local measurement:

- bytes: `391223`
- SHA-256: `524aacda2ada2bbc4f11e72fc989221f9aad2f602851d90a31316200dfbbc040`

Result: **PASS.**

---

# Promotion-blocking findings

## V09-IR-001 — BLOCKER — zero/historical biological source can create positive commerce quantity

**Affected gates:** G1 sale-ready vs biological authority; G6 quantity ownership boundary.

### Exact reproduction

1. Start from fresh seeded Betta cohort `cb` at 76.
2. Perform the canonical split so the original source cohort becomes historical with `active=false` and `count=0`.
3. Open commerce preparation on that historical source cohort.
4. Mark the historical source sale-ready.
5. Open `Prepare AquaticFinder handoff`.
6. The rendered form reports Breeder biological quantity `0`, but the quantity input has `min=1` and `max=1` because the implementation clamps the maximum with `Math.max(1, biologicalQuantity)`.
7. Enter proposed commerce quantity `1` and save.

### Observed

A real structured handoff is created with:

```text
sourceRef = cohort:cb
biologicalQuantitySnapshot = 0
proposedCommerceQuantity = 1
```

The same handoff public facts truthfully say `0 recorded animals` while the commerce proposal simultaneously claims quantity `1`.

### Expected

A source with no current positive biological quantity must not be able to create a positive commerce handoff. Historical/source records may remain available for provenance/reporting, but they cannot own saleable quantity they no longer biologically own.

### Classification

**BLOCKER.** The v0.9 mandate explicitly classifies biological quantity ownership corruption as BLOCKER. This is not merely invalid form presentation; the inconsistent handoff can actually be saved.

---

## V09-IR-002 — BLOCKER — reproductive-output and descendant cohort can simultaneously own the same animals for commerce

**Affected gates:** primary v0.9 product objective; G3 provenance reuse; G6 quantity ownership boundary.

### Exact reproduction

Use fresh seeded Neocaridina state:

- source output `s01` = `August juveniles`;
- recorded output/recruit quantity = 50;
- descendant cohort `cs` explicitly has `spawnId='s01'`;
- current descendant cohort count = 42;
- Program parentage remains `Colony provenance only; parents unknown`.

Then:

1. Mark descendant cohort `cs` sale-ready.
2. Create a handoff for its full current quantity `42`.
3. Independently mark source output `s01` sale-ready.
4. Create another handoff for output quantity `50`.

### Observed

Two independent commerce ownership claims are accepted:

```text
cohort:cs  biological snapshot = 42  proposed = 42
spawn:s01  biological snapshot = 50  proposed = 50
```

The cohort explicitly descends from `s01`, so these are not two independent inventories. The output quantity is a historical recruit/birth observation that has already materialized into the descendant cohort. The candidate permits the same biological animals to be offered through both layers.

### Expected

The handoff model must establish one current biological quantity owner for each saleable unit. For non-egg/livebirth/population outputs that materialize as offspring cohorts, current commerce quantity must come from the current cohort/stock record, not simultaneously from the historical reproductive-output count.

A discrete remaining egg batch may be a distinct quantity owner only for eggs that have not already materialized into descendant offspring; that distinction must be explicit and enforced.

### Classification

**BLOCKER.** This directly violates the primary v0.9 question: preventing duplicate quantity ownership.

---

# Additional finding

## V09-IR-003 — MINOR — `Sale / rehome` selection workspace handoff entry does not render

The candidate states that commerce handoff is contextual from the selection workspace. I recorded a fresh `Sale / rehome` disposition for Atlas through the rendered canonical selection-session flow.

The disposition saved correctly, but `selectionScreen('p1')` did not render the intended `Sale / rehome → commerce-ready handoff` section.

Static/runtime inspection shows the wrapper calls `currentSelectionDisposition(st.id)?.decision`, while canonical `currentSelectionDisposition` expects a stock object and returns the disposition string directly.

This does not bypass biological authority and commerce remains reachable through stock detail/More, so I classify it **MINOR**, not a promotion blocker by itself. It should be corrected with the quantity blockers because it is already within the bounded v0.9 surface.

---

# Independently demonstrated positive behavior

Despite the blockers, the following were independently demonstrated on the exact bytes:

- sale-ready form can explicitly keep a stock fact private;
- private `Sex` was absent from the public handoff facts;
- internal handoff note was not promoted into public facts;
- handoff schema/source identity was explicit (`draneka.aquaticfinder.commerce-handoff.v1`, `stock:atlas`);
- representative commerce actions did not mutate Atlas ancestry or create biological events;
- canonical `V08-IR-001` count-revision negative reproduction remained closed: unrelated `76 → 75` count revision left the grow-out plan `Planned`;
- canonical `V08-IR-002` cancel-then-unrelated-Betta-feed reproduction remained closed: Rachovii lifecycle stayed unresolved and no wetting was fabricated;
- no commerce destination was added to bottom navigation (`Today / Programs / Log / Grow-out / More`);
- representative v0.9/canonical surfaces at exact widths `320 / 390 / 768 / 1440` showed zero document overflow, zero sale-ready-sheet overflow, zero page errors and zero console errors.

These positive findings do not override the quantity-ownership blockers.

---

# Gate disposition

| Gate | Result |
|---|---|
| Exact v0.9 binding | PASS |
| Canonical v0.8 binding | PASS |
| G1 — Sale-ready vs biological authority | **FAIL** |
| G2 — Public/private fact selection | PASS on tested paths |
| G3 — Provenance reuse without invention | **FAIL — duplicate source ownership model** |
| G4 — Structured AquaticFinder handoff | PASS structurally; authority invalidated by G6 |
| G5 — Provenance report | PASS on tested privacy path |
| G6 — Quantity ownership boundary | **FAIL** |
| G7 — Commercial reconciliation | PASS on tested positive path; subject to corrected source authority |
| G8 — Selection / Pair Builder boundary | canonical authority preserved; contextual entry MINOR |
| G9 — v0.8 operational regression | targeted former-defect paths PASS; full PASS not claimed after blockers |
| G10 — v0.7 regression | no authority bypass found on tested path; full PASS not claimed after blockers |
| G11 — v0.6 regression | no new provenance fabrication found on tested path; full PASS not claimed after blockers |
| G12 — v0.5 regression | no biological mutation from tested commerce path; full PASS not claimed after blockers |
| Responsive/runtime | representative exact-width matrix PASS; full promotion matrix deferred until correction |
| Scope discipline | PASS on inspection |
| Anti-overwhelm | PASS except MINOR selection-workspace missing entry |

---

# Required bounded correction

The correction should establish a single current commerce-quantity owner rather than special-casing only the two reproductions.

At minimum:

1. **No positive handoff from zero/unknown current biological quantity.**
   - Do not clamp `0` to an artificial maximum of `1`.
   - Reject handoff creation if current saleable biological quantity is not a known positive value.

2. **Do not treat historical reproductive-output totals as concurrent current inventory when those animals have materialized into offspring cohorts.**
   - Non-egg/livebirth/population output counts are historical reproductive evidence, not a second inventory owner.
   - Current animals should be handed off from current cohort/stock records.
   - Remaining discrete eggs/collections may remain a separate commerce source only for genuinely remaining/unmaterialized quantity.

3. **Historical/inactive/zero-count cohorts may provide provenance/report history but cannot be sale-ready quantity sources.**

4. **Fix the existing selection-workspace `Sale / rehome` commerce entry** using canonical disposition semantics without changing selection authority.

A narrow helper/invariant is preferred, e.g.:

```text
COMMERCE_HANDOFF_ALLOWED
=
CURRENT_SOURCE_OWNS_DISTINCT_BIOLOGICAL_QUANTITY
AND KNOWN_POSITIVE_QUANTITY
AND NO_DUPLICATE_MATERIALIZED_SOURCE_OWNER
```

Do not redesign marketplace/channel operations into Breeder.

---

# Final disposition

**CHANGES_REQUIRED**

```text
HOLISTIC_V0_9_EXACT_BINDING = PASS
HOLISTIC_V0_9_PRODUCT_OBJECTIVE = FAIL
HOLISTIC_V0_9_SALE_READY_BOUNDARY = FAIL
HOLISTIC_V0_9_PUBLIC_PRIVATE_EVIDENCE = PASS_ON_TESTED_PATHS
HOLISTIC_V0_9_PROVENANCE_REUSE = FAIL
HOLISTIC_V0_9_AQUATICFINDER_HANDOFF = STRUCTURALLY_PASS_AUTHORITY_FAIL
HOLISTIC_V0_9_PROVENANCE_REPORT = PASS_ON_TESTED_PATHS
HOLISTIC_V0_9_QUANTITY_OWNERSHIP_BOUNDARY = FAIL
HOLISTIC_V0_9_COMMERCE_RECONCILIATION = PASS_ON_TESTED_PATHS
HOLISTIC_V0_9_SELECTION_PAIRBUILDER_BOUNDARY = PASS_WITH_MINOR_CONTEXTUAL_DEFECT
HOLISTIC_V0_9_V0_8_REGRESSION = TARGETED_PASS_FULL_PASS_NOT_CLAIMED
HOLISTIC_V0_9_V0_7_REGRESSION = TARGETED_PASS_FULL_PASS_NOT_CLAIMED
HOLISTIC_V0_9_V0_6_REGRESSION = TARGETED_PASS_FULL_PASS_NOT_CLAIMED
HOLISTIC_V0_9_V0_5_REGRESSION = TARGETED_PASS_FULL_PASS_NOT_CLAIMED
HOLISTIC_V0_9_RESPONSIVE_MATRIX = REPRESENTATIVE_PASS_FULL_PASS_DEFERRED
HOLISTIC_V0_9_SCOPE_DISCIPLINE = PASS
HOLISTIC_V0_9_ANTI_OVERWHELM = PASS_WITH_MINOR
HOLISTIC_V0_9_INDEPENDENT_REVIEW = CHANGES_REQUIRED
HOLISTIC_V0_9_PROMOTION_ELIGIBLE = NO
HOLISTIC_V0_9_CANONICAL = NO
PR_9_MERGE = HOLD
```

No promotion or merge is authorized by this review.
