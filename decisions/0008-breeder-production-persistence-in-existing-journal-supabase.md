# Decision 0008 — Breeder production persistence in existing Journal Supabase

Date: 2026-09-09
Status: **FOUNDER-LOCKED FOR IMPLEMENTATION PLANNING**

## Decision

Draneka Aquarium Breeder production persistence will use the **existing AquaticFinder Journal Supabase project**.

```text
BREEDER_PRODUCTION_DATABASE_PROJECT = EXISTING_JOURNAL_SUPABASE
JOURNAL_SUPABASE_PROJECT_REF = sjodccpuyaasljcunmug
NEW_SUPABASE_PROJECT = NO
CORE_SUPABASE_PROJECT = UNCHANGED
```

The existing AquaticFinder Core Supabase project remains separate and continues to own account, identity and session responsibilities. This decision does not merge Core and Journal persistence.

## Exact product authority

Implementation planning is derived from the canonical holistic v1.0 product/design authority:

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1zpWYG4igEMRm_Bv2HZJMgKrfXhVwL8c0`
- Bytes: `458038`
- SHA-256: `4746694d3c40ec03177fb07723248e3373963894c94e66061b676ae3dbc2ab5d`
- Canonical repository merge: `1baee0e1b2a57f056dccc3c6db834b78f88cfede`

This decision does not alter those prototype bytes or authorize product redesign.

## Existing platform boundary preserved

Current AquaticFinder persistence remains:

```text
AquaticFinder Core Supabase
  account / profile / identity / session / shared Core data

AquaticFinder Journal Supabase
  Journal data + media
  + Breeder production data
```

No third Supabase project is to be introduced for Breeder unless a later explicit Founder architecture decision supersedes this record.

## Database ownership model

The Journal Supabase project is a shared physical PostgreSQL boundary, but domain authority remains explicit.

### Journal-owned records

Journal remains authoritative for existing shared aquarium records, including:

- `journal_tanks`;
- `journal_livestock`;
- Journal entries/events and observations;
- water-parameter records and freshness;
- Monitoring Cases;
- Journal media assets and private media storage;
- existing FollowUp/Schedule infrastructure;
- Journal Intelligence work data.

Breeder must not duplicate these records merely to gain local ownership.

### Breeder-owned records

Breeder will own breeding-specific records required by canonical v1.0, including the eventual production representation of:

- Breeding Programs;
- breeder-stock membership/context;
- parentage and breeding-source context;
- reproductive outputs;
- explicit hatch/recruitment observations;
- offspring/grow-out groups;
- lineage/provenance edges;
- count, move, split, merge, mortality/loss and life-stage operations where they mutate Breeder biological state;
- selection sessions and phenotype evaluations;
- holdback/non-breeding/sale-rehome/retire dispositions;
- breeder-specific lifecycle suggestions and Breeder Round projections;
- commerce handoff evidence and reconciliation records that remain within the canonical Breeder/AquaticFinder boundary.

The exact table decomposition is an implementation-plan concern and is not frozen by this decision.

## Shared identity and references

Because Breeder and Journal will live in the same PostgreSQL database:

- Breeder may reference Journal tank UUIDs directly.
- Breeder may reference Journal livestock UUIDs directly where an individually tracked breeder animal is represented by `journal_livestock`.
- Cross-user references must fail closed even when a referenced UUID exists.
- Breeder must preserve Journal authority for the referenced record; a foreign key does not transfer ownership of the Journal entity to Breeder.
- Core user identity remains an external persistence boundary. No cross-database foreign key to Core is introduced.

Breeder records should follow the existing owner-scoped Journal pattern with a stable `owner_user_id` and explicit authorization checks.

## One migration authority for the shared database

There must not be two independent migration systems targeting the Journal Supabase project.

The `nickdevph/aquaticfinder-journal` repository remains the migration and database-runtime governance authority for that physical database. Breeder schema/RLS/runtime-role migrations must therefore enter through the Journal database migration path, even when the resulting tables are Breeder-owned domain records.

The `nickdevph/draneka-breeder` repository owns Breeder product/application contracts and implementation, but must not introduce a competing production migration runner for the same Journal database.

This rule exists to prevent migration-order collisions, conflicting role grants, duplicate bootstrap authority and inconsistent production schema state.

## Logical table namespace

The implementation should follow the current Journal database convention unless a reviewed database plan proves otherwise:

```text
public.journal_*
public.breeder_*
```

A new PostgreSQL schema is not required merely to separate the domains. Logical separation is provided through table naming, service boundaries, role grants, RLS/owner scoping and domain contracts.

## Runtime access

Breeder must not receive broad Journal database privileges merely because it shares the project.

The planned runtime model is:

- a dedicated Breeder runtime database role/credential scoped to required `breeder_*` operations and explicitly admitted Journal reads;
- a Breeder-specific connection setting may point to the same Journal Supabase host/database while using that restricted role;
- browser/mobile clients never receive privileged PostgreSQL or Supabase service credentials;
- Journal-owned writes should use Journal's canonical service/API path when one exists rather than bypassing Journal domain validation with direct Breeder SQL.

A separate runtime role or connection secret does **not** constitute a new Supabase project or database.

## Media default

No new media platform is admitted by this decision. The implementation plan should first attempt to reuse the existing private Journal media asset/storage system with explicit Breeder associations and the canonical public/private evidence-selection boundary. A separate bucket may be considered only if required by storage-policy or lifecycle evidence; it would still remain in the same Journal Supabase project.

## Scheduling default

Breeder should not duplicate the existing Journal scheduling engine by default. The implementation plan should map breeder obligations to existing Journal FollowUp/Schedule contracts where semantically compatible, while keeping lifecycle suggestions and Breeder Round projection logic distinct from recorded biological facts.

## Security and privacy requirements

Before any production migration is admitted, the plan must prove:

- owner isolation for every Breeder record;
- cross-user Journal tank/livestock reference rejection;
- least-privilege Breeder runtime grants;
- RLS/runtime-role behavior consistent with current Journal hardening;
- account deletion/export/retention treatment for Breeder data;
- no private media leakage into public/commerce handoff evidence;
- no biological quantity mutation through commerce reconciliation;
- no direct client access to privileged database credentials.

## Non-effects

This decision does not:

- create tables or migrations;
- mutate the production Journal Supabase project;
- create a new Supabase project;
- change Core ownership;
- move Journal data;
- rename existing environment variables;
- authorize production deployment;
- authorize v1.1 product scope;
- authorize subscriptions, marketplace management, payments, orders or shipping;
- authorize Android or web production implementation by itself.

Implementation remains gated by the separate implementation plan and subsequent bounded implementation/review authority.

```text
BREEDER_JOURNAL_SUPABASE_DECISION = LOCKED
BREEDER_NEW_SUPABASE_PROJECT = PROHIBITED_UNLESS_FOUNDER_SUPERSEDES
BREEDER_DATABASE_MIGRATION_AUTHORITY = AQUATICFINDER_JOURNAL_REPOSITORY
BREEDER_PRODUCT_APPLICATION_AUTHORITY = DRANEKA_BREEDER_REPOSITORY
CORE_DATABASE_BOUNDARY = UNCHANGED
PRODUCTION_DATABASE_MUTATION = NOT_AUTHORIZED_BY_THIS_DECISION
```