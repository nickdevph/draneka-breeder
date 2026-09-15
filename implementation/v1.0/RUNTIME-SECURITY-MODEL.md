
# Breeder v1.0 Runtime Security and RLS Model

Status: CORRECTED IMPLEMENTATION PLAN / SECURITY QUALIFICATION NOT RUN
Physical database: existing Journal Supabase project  
Security rule: Breeder must not inherit broad Journal runtime privileges

## 1. Trust boundaries

1. Core authenticates the user and is the authority for the external owner subject.
2. The Breeder server verifies the Core session through the established server-side session contract.
3. The Breeder server, not the browser, derives owner_user_id.
4. The Breeder server uses a dedicated server-only database credential.
5. PostgreSQL owns Breeder tables and constraints; domain authorization remains server-side and transaction-bound.
6. Journal-owned writes remain behind Journal's service/API boundary.

No browser, Android client, request body, query parameter or caller-controlled GUC is an authorization credential.

## 2. Roles

The planned Journal migration must create or qualify the following after current Journal main is re-read and local sequence 029 is assigned:

~~~text
breeder_runtime       NOLOGIN capability role
breeder_service       LOGIN service role used only by the Breeder server
journal_migrator      existing migration owner
~~~

breeder_service must be NOSUPERUSER, NOCREATEDB, NOCREATEROLE, NOREPLICATION, NOBYPASSRLS, INHERIT, and a direct-login identity. It is a member of breeder_runtime and is not a member of journal_runtime, journal_migrator or journal_recovery_admin.

The exact role names may be adjusted only by the Journal security review; the properties are fixed.

## 3. Grants

breeder_runtime receives only:

- USAGE on public;
- SELECT, INSERT and UPDATE on the admitted breeder_* tables;
- no DELETE, TRUNCATE, REFERENCES, TRIGGER, CREATE or DDL;
- sequence privileges only where the final schema actually uses sequences;
- no EXECUTE on Journal security-sensitive routines;
- no access to Journal Intelligence tables;
- no access to Core tables;
- no direct write privilege on journal_* tables.

Breeder API reads of Journal tanks, livestock or media use an admitted Journal service/API or a Journal-owned read projection. A same-database foreign key may validate existence without granting Breeder table read or write authority.

Journal migration code is owned by journal_migrator. Breeder runtime never runs a migration.

## 4. Owner-scope enforcement

Every Breeder request follows this order:

1. verify the Core session;
2. resolve the canonical owner subject from the verified session;
3. ignore any owner_user_id supplied by the caller;
4. start a database transaction;
5. bind the verified owner to the transaction through the approved server-side owner-scope helper;
6. execute parameterized domain SQL that includes owner predicates;
7. rely on composite foreign keys and forced RLS as defense in depth;
8. commit and read back by owner and entity ID.

The owner-scope helper must fail closed if the scope is absent, malformed or changed during a transaction. It must not accept an end-user supplied authorization token, user ID or logical worker identity. The implementation review must prove that the Breeder login cannot bypass RLS, SET ROLE into a privileged identity, or alter owner scope after binding.

RLS policies on breeder_* relations are explicit SELECT, INSERT and UPDATE policies for breeder_runtime. They require the current server-bound owner scope to equal row.owner_user_id. There is no FOR ALL policy. There is no runtime DELETE policy. A missing scope matches no row.

If the current Journal runtime-role hardening standard requires a different server-bound context mechanism, the Breeder adapter adopts that reviewed standard rather than weakening it.

## 5. Same-owner Journal references

A syntactically valid UUID is never enough.

- Journal migration 029 must prove composite uniqueness for journal_tanks(id, owner_user_id), journal_livestock(id, owner_user_id) and journal_media_assets(id, owner_user_id) before adding composite foreign keys.
- Breeder commands validate the target row through the Journal-owned service/API with the verified owner.
- The database composite FK rejects an owner mismatch even if a service bug supplies a foreign UUID.
- archived Journal rows are treated according to the domain contract; they are never silently substituted for another user's active row.
- any failed scope check returns OWNER_SCOPE_DENIED and creates no biological record.

## 6. Current Journal authority and migration collision

The current Journal main is `897ce087d0d42dac25eabe23b05b00a605f23644`, with local migration tail `028-core-journal-pr5-refresh-token-replacement-index-convergence.sql`. The parent-supplied provider readback reports 34 applied migrations, latest `20260915093928` (`af_pr5_temp_target_recovery_read_20260915_001`).

PR #873 is open non-draft, stale/diverged and unmerged historical work at `829618fe2d3f20a64703021676032be429079fd3`; its claimed migration 024 is not current authority and is not a Breeder dependency. BREEDER-FOUNDATION-001A must bind to current Journal main and use planned local sequence 029, never historical 025. A fresh provider timestamp must be assigned by the Journal migration owner at implementation time, strictly after the supplied provider maximum, then read back.

The provider currently has no Breeder foundation tables; the only matching public table is `public.catalogue_breeder_attributions` with RLS enabled and zero rows. Security advisors currently report 16 mutable-function-search-path warnings. Therefore least-privilege/RLS is a required implementation gate, not a current security PASS.

## 7. Security tests

Required negative tests include:

- unauthenticated request;
- request with a caller-supplied different owner_user_id;
- owner A reading owner B's Program, output, group, receipt or handoff;
- owner A referencing owner B's tank or livestock UUID;
- direct Breeder login attempting Journal table SELECT/INSERT/UPDATE/DELETE;
- direct Breeder login attempting DELETE/TRUNCATE/DDL/role escalation;
- missing, malformed or changed owner scope;
- SET ROLE and session_user mismatch;
- direct execution of Journal guard routines;
- stale revision and duplicate idempotency;
- private media selected for a public handoff;
- zero public media silently replaced by defaults.

A production database admission is blocked by any failed negative test.

## 8. Account lifecycle

The Journal-owned account deletion/export/retention path must include breeder_* tables in the same owner-scoped lifecycle. Deletion must also remove or anonymize selected media associations and commerce snapshots according to policy. No orphaned row may remain readable through a different owner scope.

## 9. Non-effects

This plan does not alter Journal PR #873, create a role, grant a privilege, run SQL or mutate any Supabase project. It is a security design and qualification contract only. The real Core-auth binding remains the current server-side Core session contract; it must be re-read and proven before 001B, and no caller-supplied owner identity is accepted.

## 10. Exact owner-scope binding contract

The first implementation must use one named transaction context and one named helper:

~~~text
transaction setting = app.breeder_owner_user_id
database helper = public.breeder_current_owner_user_id()
~~~

The helper returns UUID or NULL. It returns NULL when the setting is absent, blank or not a canonical UUID. It is owned by journal_migrator, has a fixed search_path, is not executable by PUBLIC, and is executable only as needed by breeder_runtime policy evaluation.

The Breeder server sets the context only after Core-session verification, using a parameterized transaction-local call equivalent to:

~~~sql
SELECT set_config('app.breeder_owner_user_id', $1, true);
~~~

The value is never read from an end-user field. The transaction immediately verifies that public.breeder_current_owner_user_id() equals the owner resolved from the verified Core session. Every mutation and read includes the owner predicate as well as RLS.

RLS policy shape is:

~~~sql
USING (owner_user_id = public.breeder_current_owner_user_id())
WITH CHECK (owner_user_id = public.breeder_current_owner_user_id())
~~~

There are separate SELECT, INSERT and UPDATE policies; no FOR ALL policy. A missing or malformed setting therefore matches no row. The helper and role grants must be covered by the disposable-Postgres verifier before the schema is admitted.

The runtime login is a real LOGIN role with session_user equal to current_user. SET ROLE, role inheritance into Journal capability roles, and client-side setting of the owner context are prohibited by the service boundary and tested as negative cases.
