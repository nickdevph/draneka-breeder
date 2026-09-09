
# Breeder v1.0 Implementation Admission, Collision and Rollback Record

Date: 2026-09-09  
Status: IMPLEMENTATION-READY / PRODUCTION MUTATION NOT AUTHORIZED

## 1. Exact custody

~~~text
CANONICAL_BREEDER_MAIN = 1baee0e1b2a57f056dccc3c6db834b78f88cfede
PLANNING_PR = nickdevph/draneka-breeder#12
PLANNING_HEAD_AT_EXECUTION_START = d4925cb57e98115940c6c9e6d02849644959cdc5

JOURNAL_MAIN = 5f00cf5106e3127a8dfb55ab59407d262f1e8d16
JOURNAL_RUNTIME_RLS_PR = #873
JOURNAL_RUNTIME_RLS_HEAD_AT_REVIEW = 829618fe2d3f20a64703021676032be429079fd3
JOURNAL_RUNTIME_RLS_STATUS = OPEN / NOT MERGED

DATABASE_PROJECT = sjodccpuyaasljcunmug
FIRST_BREEDER_JOURNAL_MIGRATION = 025
~~~

After this document is committed, the planning PR head becomes the reviewed planning head and must be re-read before any independent review conclusion.

## 2. Collision analysis

### Draneka Breeder

PR #12 is the only live Breeder implementation-planning PR observed. It remains documentation-only. No source, migration, deployment or production files are admitted in this planning change.

### AquaticFinder Journal

- PR #873 directly owns the current migration 024, runtime-role/RLS hardening and both Journal bootstrap entrypoints. It is a hard dependency. Breeder 025 must wait for its final exact-head review and merge.
- PR #869 is a stale-base Journal tank-create recovery candidate. It does not collide with Breeder schema, but it must be rebased onto current Journal main before any shared runtime qualification. The foundation slice reads tanks and must use the final Journal tank contract.
- PR #870 routes bounded non-production JI qualification to isolated Neon. It does not create the Breeder production database and must not be used as Breeder persistence.
- PR #864 is a request-scoped JI recovery controller. It is unrelated to Breeder-owned biological tables; its recovery role/token must not be reused by Breeder.
- PR #863 changes mobile-auth runtime privileges. It is not a Breeder migration dependency, but the Breeder Core-session adapter must bind to the final authenticated-session contract rather than duplicate mobile auth.
- Closed JI PRs and existing Journal 001-023 migration history remain historical authority. No existing Journal migration may be rewritten.

### Exact sequencing rule

~~~text
1. Finish exact-head independent review of Journal #873.
2. Merge the final approved 024 line into Journal main.
3. Re-resolve Journal main SHA and migration marker family.
4. Create Journal PR BREEDER-FOUNDATION-001A from that exact Journal main.
5. Add only Journal migration 025 and its focused tests/bootstrap/retention changes.
6. Qualify 001A on disposable Postgres and complete Journal regression gates.
7. Only then implement Breeder 001B and 001C against the qualified contract.
~~~

If #873 changes after this plan, all later package bases are stale until re-bound. If another Journal migration lands first, re-number the Breeder migration after the new final marker; do not reuse 025.

## 3. Package completion terminals

### 001A

~~~text
JOURNAL_MIGRATION_025 = QUALIFIED
BREEDER_ROLE_AND_RLS = QUALIFIED
COMPOSITE_JOURNAL_FKS = QUALIFIED
ACCOUNT_LIFECYCLE = QUALIFIED
ROLLBACK = QUALIFIED
JOURNAL_REGRESSION = PASS
PRODUCTION_MUTATION = NO
~~~

### 001B

~~~text
CORE_SESSION_ADAPTER = QUALIFIED
OWNER_SCOPE = QUALIFIED
DOMAIN_COMMANDS = QUALIFIED
IDEMPOTENCY = QUALIFIED
QUANTITY_AND_PROVENANCE = QUALIFIED
API_READBACK = PASS
PRODUCTION_SOURCE_IMPLEMENTATION = NO
~~~

### 001C

~~~text
CANONICAL_NAVIGATION = PASS
WEB_VERTICAL_SLICE = PASS
RESPONSIVE_320_390_768_1440 = PASS
ACCESSIBILITY = PASS
ERROR_RECOVERY = PASS
CROSS_USER_BROWSER_DENIAL = PASS
PRODUCTION_DEPLOYMENT = NO
~~~

## 4. Rollback units

- 001A: Journal migration 025 plus role/grant/RLS/retention changes and tests. Before data, use the qualified disposable rollback. After data, disable Breeder and repair forward.
- 001B: Breeder domain/API commit set. Disable the feature route and preserve database history.
- 001C: Breeder web commit set. Revert UI/API release as a unit; no database rollback is implied.
- P4 onward: each domain package has its own append-only data contract and forward repair path.

## 5. Stop conditions

Stop immediately and return CHANGES_REQUIRED if:

- the canonical v1.0 artifact or product semantics are not exactly bound;
- a third database or competing migration runner is proposed;
- Core identity is duplicated or caller-controlled;
- Journal-owned records are written directly without an admitted Journal boundary;
- a cross-user UUID reference can succeed;
- quantity or provenance tests fail;
- private media can leak to a public handoff;
- migration marker/base is stale;
- runtime privileges exceed the least-privilege model;
- required Journal/Android/JI regression gates are red;
- production mutation is attempted without explicit Founder admission.

## 6. Founder-gated implementation commission

The next commission after this planning PR is:

~~~text
ROLE = IMPLEMENTATION OWNER
PACKAGE = BREEDER-FOUNDATION-001A
REPOSITORY = nickdevph/aquaticfinder-journal
BASE = final independently reviewed Journal main after PR #873
SCOPE = migration 025 + focused schema/security/retention/bootstrap tests only
DATABASE = disposable/non-production only
PRODUCTION MUTATION = NO
STOP = any stale base, security failure, marker mismatch, Journal regression, or independent review CHANGES_REQUIRED
~~~

001B and 001C must not start until 001A reaches its terminal.

## 7. Admission terminal

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

This is planning admission, not production authorization.
