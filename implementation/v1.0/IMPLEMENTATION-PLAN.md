
# Draneka Aquarium Breeder v1.0 — Production Implementation Plan

Date: 2026-09-09  
Status: **IMPLEMENTATION-READY PLANNING / NO PRODUCTION MUTATION / NO PRODUCTION SOURCE IMPLEMENTATION**

This plan is the execution contract for implementing the exact canonical holistic v1.0 product. It freezes the boundaries below so implementation can proceed without reopening foundational architecture.

## 1. Exact product authority

~~~text
ARTIFACT =
DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html

DRIVE_ID =
1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0

BYTES = 458038
SHA256 = 4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d

CANONICAL_REPOSITORY = nickdevph/draneka-breeder
CANONICAL_MERGE = 1baee0e1b2a57f056dccc3c6db834b78f88cfede
HOLISTIC_V1_0_CANONICAL = YES
~~~

The exact artifact behavior is product authority. This plan does not redesign it.

The independent v1.0 product review established the following implementation-facing behavior:

- primary navigation is exactly Today / Programs / Log / Grow-out / More;
- Program search has deterministic recovery;
- quantity is singular and does not double-count scalar and structured hatch observations;
- historical/materialized reproductive outputs cannot regain positive commerce authority;
- split, merge, move, stage, loss and count semantics preserve quantity and provenance;
- phenotype is observation, not genotype;
- suggestions, scheduled actions, completed actions, observations and derived state remain distinct;
- public/private media selection is explicit, including explicit zero-public-media;
- commerce reconciliation never rewrites biological history;
- representative Betta, Medaka, Neocaridina and annual-killifish workflows are evidence-bounded.

## 2. Founder-locked database and repository boundary

~~~text
BREEDER_PRODUCTION_DATABASE_PROJECT = EXISTING_JOURNAL_SUPABASE
JOURNAL_SUPABASE_PROJECT_REF = sjodccpuyaasljcunmug
NEW_SUPABASE_PROJECT = NO
CORE_SUPABASE_PROJECT = UNCHANGED

PHYSICAL_DATABASE_MIGRATION_AUTHORITY = nickdevph/aquaticfinder-journal
BREEDER_PRODUCT_APPLICATION_AUTHORITY = nickdevph/draneka-breeder
~~~

Core remains a separate persistence boundary for account, profile, identity and session authority. Journal remains the physical PostgreSQL home for Journal-owned data and future Breeder-owned data. No cross-database foreign keys or cross-database transactions are introduced.

Decision 0008 is the locked architecture decision. Breeder must not add a second production migration runner, migration registry or bootstrap path against the Journal database.

Detailed records:

- implementation/v1.0/SCHEMA-DOMAIN-MODEL.md
- implementation/v1.0/RUNTIME-SECURITY-MODEL.md
- implementation/v1.0/API-SERVICE-CONTRACT.md
- implementation/v1.0/WEB-ARCHITECTURE.md
- implementation/v1.0/QUALIFICATION-MATRIX.md
- implementation/v1.0/IMPLEMENTATION-ADMISSION.md

## 3. Final system shape

~~~mermaid
flowchart TD
  Core["AquaticFinder Core identity/session authority"] --> Auth["server-side Core session adapter"]
  Auth --> Web["Draneka Breeder web client"]
  Web --> API["Breeder API/domain service"]
  API --> BRole["restricted breeder runtime role"]
  BRole --> JS["existing Journal Supabase Journal + breeder_* tables"]
  API --> JAPI["Journal-owned service/API for Journal writes and admitted reads"]
  API --> Handoff["structured commerce handoff"]
  Handoff --> Commerce["AquaticFinder commerce allocation/listing/order authority"]
~~~

The browser and Android clients never receive PostgreSQL credentials. The Breeder service resolves the authenticated Core subject server-side, then performs owner-scoped domain operations against the shared Journal database.

## 4. Frozen ownership matrix

| Domain fact or capability | Authority | Breeder rule |
| --- | --- | --- |
| Account, profile, identity, session | Core | consume verified Core session; no duplicate identity authority |
| Tank identity and location | Journal | reference Journal tank; never duplicate tanks |
| Ordinary livestock identity | Journal | reference Journal livestock where applicable |
| Water, feeding, maintenance, ordinary observations | Journal | use Journal service/API; no direct Breeder table writes |
| Journal media and private storage | Journal | reuse through an admitted media adapter |
| FollowUp/Schedule infrastructure | Journal | bind only where semantics match; do not duplicate scheduler |
| Breeding Programs | Breeder | Breeder-owned durable record |
| Breeder-stock membership/context | Breeder | Breeder-owned; Journal livestock is a reference |
| Parentage/source context | Breeder | evidence-bounded; unknown remains unknown |
| Reproductive outputs and hatches | Breeder | Breeder-owned biological authority |
| Offspring/grow-out groups | Breeder | Breeder-owned; current tank is a Journal reference |
| Quantity and operation ledger | Breeder | one biological quantity authority |
| Provenance/lineage | Breeder | append-only evidence links and source snapshots |
| Phenotype/evaluations | Breeder | observation only; never genotype inference |
| Selection/disposition | Breeder | current eligibility is derived from current history |
| Lifecycle suggestions/Breeder Round | Breeder | projection/attention; never a biological fact |
| Commerce evidence/handoff/reconciliation | Breeder | explicit evidence-bounded handoff; no biological rewrite |
| Listings, channels, orders, payment, shipping, commercial allocation | AquaticFinder commerce | outside Breeder v1.0 |

A foreign key to a Journal row does not transfer ownership of that Journal row.

## 5. Required invariants

The following are implementation contracts, not UI suggestions.

### Quantity

- one biological quantity authority per reproductive output and offspring group;
- scalar/legacy and structured hatch observations are materialized once;
- remaining output is original minus removed minus materialized hatch quantity, never a second independent scalar;
- split conserves quantity across source and children;
- merge conserves quantity and preserves all source provenance;
- loss/mortality reduces only the affected current group;
- move, feeding, observation and stage change do not change quantity;
- an inactive, historical or fully materialized output cannot regain positive commerce authority;
- commerce allocation and reconciliation are separate from biological quantity.

### Provenance

- every descendant retains output and hatch source IDs;
- split adds a derivation edge without deleting parent history;
- merge preserves every source edge or fails closed;
- individual promotion preserves known source provenance;
- unknown/group/population ancestry cannot become exact sire/dam;
- generation labels require sufficient evidence;
- annual killifish hatch provenance includes the exact wetting attempt;
- historical records are immutable for biological mutation.

### Fact/action

~~~text
suggestion != scheduled action != completed action != observation != derived state
~~~

Completing a check does not assert the biological fact being checked. A suggestion may be dismissed or deferred without creating a fact.

### Selection and privacy

- phenotype remains an observation;
- current incompatible disposition removes current pairing eligibility;
- selection goals preserve history and snapshots;
- private media never becomes public implicitly;
- zero selected public media remains zero;
- only explicitly selected and Journal-authorized public evidence enters a handoff;
- commerce reconciliation cannot modify breeding history.

## 6. Migration and shared-database sequencing

Journal main is currently:

~~~text
nickdevph/aquaticfinder-journal
main = 5f00cf5106e3127a8dfb55ab59407d262f1e8d16
current main migration = 023-journal-ji-browser-result-handoff
~~~

Journal PR #873 is the active runtime-role/RLS hardening candidate:

~~~text
PR #873
base = 5f00cf5106e3127a8dfb55ab59407d262f1e8d16
head = 829618fe2d3f20a64703021676032be429079fd3
migration = 024-journal-ji-runtime-role-rls-hardening
state = OPEN / NOT MERGED
~~~

No Breeder database migration may be based on or compete with the unmerged #873 line. After #873 reaches its independently reviewed final head and merges, the first Breeder migration is frozen as:

~~~text
025-journal-breeder-foundation.js
025-journal-breeder-foundation.sql
~~~

The migration must:

1. require the Journal marker family from final version 024;
2. execute only as journal_migrator or an explicitly admitted migration actor;
3. execute through both current Journal bootstrap entrypoints;
4. create only the minimum breeder_* foundation tables, constraints, roles, grants, RLS and account-retention hooks needed by BREEDER-FOUNDATION-001;
5. never rewrite an existing Journal migration;
6. include disposable-Postgres qualification and a pre-data rollback proof;
7. remain non-production until a separate Founder production-admission gate passes.

The Breeder repository owns no production migration file or runner. Its PRs may contain contracts, domain code, UI and integration tests only.

## 7. Implementation-ready domain/service boundary

Breeder writes are intent/domain commands, not raw table CRUD. The initial versioned API is /api/v1.

Frozen initial commands:

~~~text
createProgram
recordReproductiveOutput
recordHatchObservation
createOffspringGroup
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
~~~

Every command resolves the owner from a verified Core session, validates all same-owner references, checks an expected revision where state can race, uses an idempotency key, performs one database transaction, returns committed readback and emits an auditable command receipt.

Journal-owned writes—feeding, water tests, ordinary observations, media creation and schedule completion—call Journal's canonical service or API. Breeder may persist an explicit Breeder-to-Journal binding, but does not bypass Journal domain validation.

## 8. Web architecture decision

The initial production web app is a separate authenticated React application in nickdevph/draneka-breeder, using the existing ecosystem's proven React/Vite/Node shape:

- React 19 + TypeScript;
- Vite 8;
- server-side Node API/domain service;
- pg against the same Journal Supabase database using a restricted server-only credential;
- Playwright browser qualification;
- Vercel deployment only after implementation admission.

The canonical IA remains:

~~~text
Today
Programs
Log
Grow-out
More
~~~

No new primary navigation destination is introduced. The authenticated shell, responsive states, forms, loading/empty/error/recovery states, keyboard paths and media adapter are specified in WEB-ARCHITECTURE.md.

Core session reuse is an adapter boundary: the browser presents the existing authenticated session; the Breeder server verifies it through the existing Core session contract or an authenticated service-to-service introspection path. No endpoint accepts a caller-supplied owner_user_id as authority.

## 9. Data migration and existing users

Initial Breeder release is prospective.

- Existing Journal tanks, livestock, events and media may be referenced as existing facts after owner-scope validation.
- No Program, parentage, reproductive output, hatch, generation or breeding history is inferred from generic Journal history.
- No automatic backfill is authorized.
- Any future backfill requires a separate Founder decision, explicit evidence mapping and independent migration review.
- Account deletion/export/retention must include Breeder-owned rows through the Journal-owned lifecycle path.

## 10. Implementation packages

| Package | Owner/repository | Dependency | Completion gate |
| --- | --- | --- | --- |
| P0 / PLAN-001 | Draneka Breeder PR #12 | canonical v1.0 + live Journal inspection | this plan and independent review PASS |
| BREEDER-FOUNDATION-001A | Journal PR after #873 | final merged Journal 024 | schema, role, RLS, FK, retention and disposable-DB PASS |
| BREEDER-FOUNDATION-001B | Breeder repository | 001A qualified on disposable DB | auth adapter, domain commands, idempotency and API PASS |
| BREEDER-FOUNDATION-001C | Breeder repository | 001B API | Today/Programs/output/hatch/group/tank web slice and readback PASS |
| P4-GROWOUT-002 | Breeder + Journal only where needed | foundation slice | count/move/split/merge/loss/stage/provenance PASS |
| P5-SELECTION-003 | Breeder | grow-out provenance | evaluation, goals, disposition and Pair Builder guardrails PASS |
| P6-ROUND-004 | Breeder + Journal schedule adapter | selection/domain foundation | projection/action/fact separation and schedule integration PASS |
| P7-COMMERCE-005 | Breeder + AquaticFinder contract | stable biological model | explicit evidence, handoff and non-mutating reconciliation PASS |
| P8-HARDENING-006 | both repositories as needed | all v1.0 surfaces | responsive/a11y/security/regression PASS |
| P9-ADMISSION-007 | Founder-gated | P8 | production migration/deployment admission PASS |
| P10-ANDROID-008 | separate Android admission | stable web/domain contract | Android convergence/review only after P9 or separate Founder admission |

Each package is one rollback unit. A package cannot silently absorb a later package or alter canonical v1.0 semantics.

## 11. First executable package — frozen mandate

~~~text
PACKAGE = BREEDER-FOUNDATION-001
SUBPACKAGES = 001A Journal foundation, 001B service/API, 001C web slice
STATUS = FROZEN FOR IMPLEMENTATION COMMISSION
~~~

### 001A — Journal database foundation

Implement only:

- breeder_programs;
- minimum owner-scoped parentage/source context;
- breeder_reproductive_outputs;
- breeder_hatch_observations;
- breeder_offspring_groups;
- breeder_group_provenance;
- breeder_group_operations;
- breeder_quantity_ledger;
- breeder_command_receipts;
- same-owner composite references to Journal tanks and optional Journal livestock;
- dedicated Breeder runtime capability/login role;
- RLS, grants, owner-scope helper, account deletion/export/retention hooks;
- migration marker/bootstrapping and tests.

Do not implement selection, Pair Builder, commerce, Android, AI, marketplace operations, or new navigation.

### 001B — service/API

Prove:

~~~text
verified Core session
  -> owner-scoped create/read Program
  -> parent/source context
  -> record reproductive output
  -> explicit hatch/recruitment
  -> create offspring group
  -> assign/reference Journal tank
  -> transaction commit
  -> committed readback
~~~

The service must reject cross-user tank/livestock UUIDs, duplicate idempotency with a different request hash, stale revisions, invalid quantities and unsupported provenance claims.

### 001C — web

Implement only the canonical authenticated shell and the vertical slice screens needed to create and read the above records. UI work starts only after 001A disposable database and security qualification passes. The first package is not production-deployed by this planning PR.

## 12. Qualification strategy

Every package must use the matrix in QUALIFICATION-MATRIX.md. Required dimensions include:

- unit and domain invariants;
- disposable Postgres migrations and rollback;
- owner isolation/RLS and cross-user composite-FK failures;
- least-privilege runtime-role verification;
- transaction, concurrency and idempotency;
- API integration and committed readback;
- Playwright E2E at 320, 390, 768 and 1440 CSS widths;
- keyboard/focus/accessibility;
- loading, empty, error and recovery;
- canonical v1.0 and v0.5-v0.9 regression fixtures;
- Journal regression whenever shared Journal code, migration bootstrap, roles or owned tables change;
- fresh security review before production database admission.

Prototype screenshots or HTML behavior alone are not implementation evidence.

## 13. Rollback and failure strategy

- Before production data exists, 025 may use a tested compensating/down script on a disposable target.
- After Breeder data exists, do not drop tables or delete history to roll back code.
- Disable the server-side Breeder feature flag, stop new commands, preserve append-only data and deploy the last qualified application.
- Repair forward with a new Journal migration; never rewrite 025.
- A failed cross-domain write leaves no half-created biological record. Journal API calls are outside Breeder biological transactions and use explicit pending or failed receipts if a future workflow needs compensation.
- A failed media/publication handoff cannot change quantity or lineage.
- A stale or conflicting idempotency key returns a deterministic conflict and does not retry a mutation.
- A concurrency conflict returns REVISION_CONFLICT and requires fresh readback.
- Production migration/deployment is stopped on any security, rollback, regression, private-media, provenance or quantity failure.

## 14. Implementation-admission checklist

Implementation may begin only when all are true:

~~~text
CANONICAL_V1_0_BOUND = PASS
BREEDER_DATABASE_PROJECT = EXISTING_JOURNAL_SUPABASE
NEW_SUPABASE_PROJECT = NO
CORE_BOUNDARY_PRESERVED = PASS
JOURNAL_BREEDER_OWNERSHIP_MATRIX = FROZEN
DATABASE_MIGRATION_AUTHORITY = FROZEN
SCHEMA_PLAN = IMPLEMENTATION_READY
RUNTIME_SECURITY_MODEL = IMPLEMENTATION_READY
API_SERVICE_BOUNDARY = IMPLEMENTATION_READY
WEB_ARCHITECTURE = IMPLEMENTATION_READY
MIGRATION_AND_ROLLBACK_PLAN = IMPLEMENTATION_READY
TEST_AND_QUALIFICATION_PLAN = IMPLEMENTATION_READY
CURRENT_JOURNAL_COLLISION_ANALYSIS = PASS
FIRST_EXECUTABLE_PACKAGE = FROZEN
INDEPENDENT_PLANNING_REVIEW = PASS
PRODUCTION_DATABASE_MUTATION = NO
PRODUCTION_SOURCE_IMPLEMENTATION = NO
BREEDER_V1_0_IMPLEMENTATION_READY = YES
~~~

This means implementation work is admitted as the next Founder-gated activity. It does not itself authorize production migration, deployment, release or Android work.

## 15. Non-effects

This planning PR does not:

- create or alter Supabase projects;
- execute migrations;
- mutate production databases;
- implement production API, UI or Android source;
- deploy services;
- change Journal runtime-role/security code;
- merge Journal PR #873;
- infer existing Breeder history;
- add marketplace management, payments, orders, shipping, CRM, genotype inference, predictive pairing authority, hardware integration or other v1.1 scope.
