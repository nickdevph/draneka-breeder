# Draneka Aquarium Breeder v1.0 — Production Implementation Plan

Date: 2026-09-09
Status: **PLANNING / NO PRODUCTION MUTATION / NO SOURCE IMPLEMENTATION YET**

## 1. Objective

Implement the canonical holistic v1.0 Draneka Aquarium Breeder product as a production-capable application while preserving its reviewed biological, provenance, quantity, privacy and Journal/AquaticFinder boundaries.

The implementation must converge to the canonical product/design authority rather than reinterpret it.

Canonical authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0`
- Bytes: `458038`
- SHA-256: `4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d`
- Canonical merge: `1baee0e1b2a57f056dccc3c6db834b78f88cfede`

## 2. Locked database decision

Decision 0008 is binding for this plan:

```text
BREEDER_PRODUCTION_DATABASE = EXISTING_JOURNAL_SUPABASE
JOURNAL_SUPABASE_PROJECT_REF = sjodccpuyaasljcunmug
NEW_SUPABASE_PROJECT = NO
CORE_SUPABASE = UNCHANGED
```

Breeder will share the existing Journal PostgreSQL database while remaining a separate logical domain.

## 3. Repository and authority split

### `nickdevph/draneka-breeder`

Owns:

- canonical Breeder product/application behavior;
- Breeder web application source;
- Breeder service/API behavior and domain orchestration;
- API/domain contracts consumed by Breeder clients;
- Breeder-specific deterministic domain tests;
- responsive/accessibility implementation qualification;
- Android client work later, if separately admitted.

### `nickdevph/aquaticfinder-journal`

Owns the physical Journal Supabase database migration path and shared Journal-domain contracts, including:

- additive `breeder_*` table migrations;
- database constraints/indexes;
- RLS/runtime-role grants and least-privilege enforcement;
- shared Journal table changes required for safe Breeder references;
- account deletion/retention/export integration affecting the shared database;
- Journal-owned API behavior if Breeder must write a Journal-owned record;
- database bootstrap/migration qualification for the shared physical database.

### Rule

No Breeder production code path may establish a second independent migration authority for the Journal database.

## 4. Runtime architecture

Target shape:

```text
                 AquaticFinder Core
               identity / session
                       |
                       v
               authenticated user
                       |
          +------------+------------+
          |                         |
          v                         v
   Journal service/API       Breeder service/API
          |                         |
          |                 restricted Breeder
          |                   runtime role
          |                         |
          +------------+------------+
                       |
                       v
            Existing Journal Supabase

        public.journal_*    public.breeder_*
```

Browser and Android clients must not connect directly to PostgreSQL with privileged credentials.

A planned `BREEDER_DATABASE_URL` may point to the same Journal Supabase database using a dedicated least-privilege Breeder runtime role. This is configuration separation, not a separate database.

## 5. Domain authority matrix

| Concern | Canonical owner | Breeder behavior |
| --- | --- | --- |
| Account/session identity | Core | consume existing authenticated identity |
| Tank identity/location | Journal | reference `journal_tanks`; do not duplicate |
| User-entered livestock identity | Journal | reference `journal_livestock` where applicable |
| Water parameters | Journal | read/display context; Journal remains write owner |
| Generic feeding/maintenance/observation | Journal | invoke Journal canonical write path when recorded |
| Journal media | Journal | reuse media identity/storage where qualified |
| Breeding Program | Breeder | canonical Breeder write |
| Parentage/breeding source | Breeder | canonical Breeder write |
| Reproductive output | Breeder | canonical Breeder write |
| Hatch/recruitment observation | Breeder | canonical Breeder write |
| Offspring/grow-out biological group | Breeder | canonical Breeder write; current tank references Journal |
| Biological quantity/provenance | Breeder | canonical Breeder write |
| Selection/phenotype evaluation | Breeder | canonical Breeder write |
| Holdback/disposition | Breeder | canonical Breeder write |
| Scheduled obligation | Journal scheduling where semantically compatible | Breeder binds/projects rather than duplicates scheduling engine |
| Lifecycle suggestion | Breeder | derived/suggestion only; never biological fact |
| Commerce-ready evidence | Breeder | prepare immutable/evidence-bounded handoff |
| Marketplace allocation/order/sale | AquaticFinder commerce | outside Breeder ownership |

## 6. Initial persistence model — planning candidate

The exact schema is not yet implementation-authorized, but the first schema design should evaluate the following normalized set rather than copying prototype state blobs into one table:

```text
breeder_programs
breeder_program_stock
breeder_parentage_contexts
breeder_parentage_members
breeder_reproductive_outputs
breeder_hatch_observations
breeder_offspring_groups
breeder_offspring_group_sources
breeder_group_operations
breeder_selection_sessions
breeder_selection_evaluations
breeder_dispositions
breeder_schedule_bindings
breeder_lifecycle_suggestions
breeder_commerce_handoffs
breeder_commerce_handoff_media
breeder_commerce_reconciliations
```

Every owner-scoped table should use UUID identity, `owner_user_id`, timestamps and explicit lifecycle/history semantics consistent with the domain contract.

### Required direct Journal relationships

Candidate same-database references include:

- `current_tank_id -> journal_tanks.id`;
- breeder-stock livestock reference -> `journal_livestock.id` when an individual is Journal-tracked;
- selected media relation -> `journal_media_assets.id` where the existing media contract is reused;
- schedule binding -> existing Journal schedule identity if the scheduling contract qualifies.

A UUID existing in Journal is not sufficient: the implementation must prove that the referenced record is owned by the same authenticated user.

## 7. Invariants that become executable contracts

The implementation must encode the prototype's qualification rules as database/service tests.

### Quantity

- remaining reproductive output cannot exceed original biological quantity;
- legacy/materialized hatch quantities are counted exactly once;
- split conserves quantity;
- merge conserves quantity;
- mortality/loss subtracts only the recorded loss;
- move/feed/observation/stage changes do not silently alter quantity;
- historical/inactive reproductive outputs cannot regain positive new commerce authority;
- commerce allocation/reconciliation cannot mutate Breeder biological quantity.

### Provenance

- split descendants retain all source output/hatch provenance;
- merges preserve all relevant source provenance or fail closed;
- exact parents are recorded only when supported;
- group/population-derived offspring do not gain fabricated exact parents;
- controlled-generation labels require sufficient parent evidence;
- annual-killifish hatch provenance remains linked to the exact wetting attempt;
- historical source groups are immutable for biological mutation.

### Fact/action separation

The implementation must keep distinct:

```text
suggestion
scheduled action
completed action
observation
canonical biological fact
projection/derived state
```

Completing a task cannot manufacture the biological fact the task was intended to check.

### Privacy

- private media remains private by default;
- explicit zero-public-media selection remains zero;
- only explicitly permitted evidence enters public report/handoff material;
- no hidden default may repopulate deselected private evidence.

## 8. Implementation sequence

### Phase P0 — Planning and contract freeze — CURRENT

Deliverables:

1. lock Decision 0008;
2. bind canonical v1.0 product authority;
3. map every v1.0 state-changing interaction to a domain owner;
4. map shared Journal dependencies;
5. define initial API/resource vocabulary;
6. produce schema proposal and RLS threat model;
7. identify exact Journal migration/runtime-role collision state before implementation;
8. define qualification datasets for Betta, Medaka, Neocaridina and annual killifish;
9. define cross-repository execution order.

No production or source implementation is admitted by P0.

Exit gate:

```text
P0_ARCHITECTURE_BOUND = YES
P0_SCHEMA_PROPOSAL_REVIEWED = YES
P0_SECURITY_MODEL_REVIEWED = YES
P0_FIRST_IMPLEMENTATION_PACKAGE_DEFINED = YES
```

### Phase P1 — Shared database foundation

Repository owner: `aquaticfinder-journal`.

Implement only the minimum additive persistence/security foundation required for the first vertical slice.

Expected work:

- initial `breeder_*` schema migrations;
- constraints and indexes;
- least-privilege Breeder runtime database role;
- owner-scoped RLS/authorization behavior;
- safe Journal tank/livestock references;
- migration/bootstrap marker updates if required by current Journal conventions;
- account deletion/retention treatment;
- disposable database tests;
- rollback proof.

No production application UI is required for this package.

Production migration remains separately gated.

### Phase P2 — Breeder domain service/API foundation

Repository owner: `draneka-breeder` with Journal integration contracts as needed.

Implement:

- authenticated request boundary;
- owner-scoped Program CRUD;
- parentage/breeding-source contract;
- reproductive-output contract;
- explicit hatch/recruitment contract;
- offspring-group contract;
- deterministic quantity/provenance service functions;
- idempotency for state-changing operations;
- transactional readback;
- typed validation and stable error codes.

No broad UI expansion during this phase.

### Phase P3 — First real end-to-end web slice

Implement the smallest production slice that proves the architecture:

```text
Today
 -> Programs
 -> Program
 -> record reproductive output
 -> record explicit hatch/recruitment
 -> create/view offspring group
 -> link current Journal tank
 -> Quick Log / observation path
 -> return to Today/Breeder Round projection
```

This slice must use real persistence and real authenticated ownership checks.

The goal is not feature completeness. The goal is proving that one canonical biological lifecycle works end to end without duplicate Journal data or prototype-only state.

### Phase P4 — Grow-out operations and provenance

Add:

- count revision;
- mortality/loss;
- move;
- life-stage observation;
- split;
- lineage-safe merge;
- historical-source immutability;
- multiple hatches from one reproductive output;
- repeated-collection and population-derived workflows;
- wetting/re-drying/wetting/hatch attempt provenance.

This phase carries the v0.5/v0.6 biological regression suite into production tests.

### Phase P5 — Selection and line development

Add:

- breeding goals/history;
- phenotype evaluations and evidence;
- selection sessions;
- individual holdbacks;
- non-breeding/sale-rehome/retire disposition;
- Pair Builder eligibility/relatedness guardrails;
- generation evidence rules.

Phenotype remains observational; genotype is never inferred without evidence.

### Phase P6 — Breeder Round and operational attention

Integrate:

- Journal schedules/occurrences where semantically compatible;
- breeder-specific lifecycle suggestions;
- breeder-created bindings/context;
- defer/skip/suppress behavior;
- exception/risk attention;
- clear separation between due, done, observed and biologically true.

Breeder Round remains a projection/attention surface rather than a second source of biological truth.

### Phase P7 — Commerce handoff and reconciliation

Implement the existing bounded commerce integration only after the biological model is stable:

- mark eligible stock sale-ready;
- explicit public/private evidence selection;
- structured handoff payload;
- provenance report;
- biological quantity snapshot;
- separate commerce allocation state;
- reconciliation that never rewrites lineage or biological quantity.

Marketplace listing management, payment, order and shipping remain outside Breeder.

### Phase P8 — Production hardening and qualification

Required gates:

- migration idempotence and rollback;
- cross-user security/RLS negative tests;
- least-privilege role review;
- account deletion/export/retention tests;
- canonical v1.0 workflow regression;
- Betta/Medaka/Neocaridina/killifish domain regression;
- 320/390/768/1440 responsive matrix;
- keyboard/focus/accessibility qualification;
- zero private-media leakage;
- quantity/provenance invariant suite;
- API error/retry/idempotency tests;
- production-readiness review before any live migration/deployment.

### Phase P9 — Android client convergence — separately admitted

Android should consume the same Breeder API/domain contracts rather than creating a second persistence implementation. Android is not part of the first database/web convergence package unless separately prioritized.

## 9. First implementation package recommendation

After P0 planning review, the first executable package should be deliberately small:

```text
BREEDER-FOUNDATION-001

Database:
  breeder_programs
  minimum parentage/source representation
  breeder_reproductive_outputs
  breeder_hatch_observations
  breeder_offspring_groups
  provenance/source links required by that path

Shared references:
  journal_tanks
  optional journal_livestock parent references

Service/API:
  create/list/read Program
  record reproductive output
  record explicit hatch/recruitment
  create/read offspring group

UI:
  none until persistence/API qualification passes
```

Do not start with Pair Builder, commerce, analytics, AI, broad species overlays or Android.

## 10. API design rules

The service contract should be intent/domain oriented rather than exposing raw table CRUD.

Examples of eventual commands:

```text
createProgram
recordReproductiveOutput
recordHatchObservation
reviseGroupCount
recordMortality
moveOffspringGroup
splitOffspringGroup
mergeOffspringGroups
recordStageObservation
recordSelectionEvaluation
applyDisposition
prepareCommerceHandoff
reconcileCommerceOutcome
```

Each state-changing command must:

1. resolve authenticated owner;
2. validate all referenced Journal/Breeder records are in scope;
3. validate expected current state/revision where needed;
4. apply one transaction;
5. preserve provenance and quantity invariants;
6. return committed readback;
7. be safe under retry/idempotency rules.

## 11. Journal integration rules

### Reads

Breeder may read admitted Journal records needed for contextual display and validation, using least privilege.

### Writes

If the user records a Journal-owned event such as a generic feeding, water test or ordinary observation, Breeder should call the Journal-owned domain/API path where feasible rather than writing `journal_*` tables directly.

Breeder-specific biological writes remain in `breeder_*` records.

### Timeline projection

The eventual Breeder timeline may project Journal and Breeder events together, but projection does not merge their authorities.

## 12. Media plan

Initial preference:

- reuse `journal_media_assets` and the private Journal media pipeline;
- use explicit Breeder association records;
- retain the canonical explicit public/private selection step for commerce evidence;
- do not copy the same binary solely because it is used by Breeder.

This must be separately verified against current Journal media retention/security behavior before implementation.

## 13. Environment and qualification strategy

Production target is the existing Journal Supabase project only.

Before live migration:

- schema and domain tests run against disposable/non-production PostgreSQL infrastructure;
- migration targets must be guarded against accidental production writes;
- any qualification route that touches the real Journal project requires explicit bounded authority;
- the production database must not be used as a casual development sandbox.

No additional production Supabase project is required by this plan.

## 14. Planning questions that remain intentionally open

These are not blockers to the locked database decision, but P0 must resolve them before source implementation:

1. exact Breeder web runtime/deployment placement and URL;
2. exact mechanism for reusing Core authentication in the separate Breeder application runtime;
3. final table decomposition and revision/history strategy;
4. whether current Journal schedule tables can support all breeder obligations without semantic distortion;
5. exact media reuse adapter and whether a same-project dedicated bucket is necessary;
6. final API transport/versioning convention;
7. whether Journal should expose read projections/views for Breeder instead of direct table SELECT privileges;
8. production feature-flag/activation strategy.

None of these questions reopens the decision to use the existing Journal Supabase project.

## 15. Explicit non-goals during convergence

Do not add during v1.0 implementation convergence unless separately authorized:

- v1.1 product features;
- a third Supabase project;
- marketplace-management UI;
- payment/order/shipping systems;
- broad CRM;
- automatic best-pair authority;
- unsupported genetics inference;
- duplicate Journal tanks/livestock/water/media systems;
- duplicate scheduling engine without evidence;
- subscription gating merely because implementation is underway;
- AI-generated canonical biological facts.

## 16. Planning terminal

The present planning branch is allowed to define and review implementation architecture only.

```text
CANONICAL_PRODUCT_AUTHORITY = HOLISTIC_V1_0
BREEDER_DATABASE_DECISION = EXISTING_JOURNAL_SUPABASE_LOCKED
NEW_SUPABASE_PROJECT = NO
IMPLEMENTATION_PHASE = P0_PLANNING
PRODUCTION_SCHEMA_MUTATION = NO
PRODUCTION_SOURCE_IMPLEMENTATION = NO
FIRST_EXECUTABLE_PACKAGE = BREEDER-FOUNDATION-001_PENDING_P0_REVIEW
```
