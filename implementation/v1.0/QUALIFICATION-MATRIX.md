
# Breeder v1.0 Test and Qualification Matrix

Status: CORRECTED IMPLEMENTATION PLAN / FRESH INDEPENDENT REVIEW REQUIRED
Qualification target: implementation admission, not prototype-only confidence

## 1. Required evidence classes

| Class | Required proof |
| --- | --- |
| Domain unit | deterministic command and invariant tests |
| PostgreSQL | migration, constraints, triggers, RLS and transaction tests |
| Security | least privilege, owner isolation, cross-user references, no credential leakage |
| Integration | Core session, Journal references/API, committed readback |
| Browser | Playwright workflows at 320/390/768/1440 |
| Accessibility | keyboard, focus, semantic labels, modal/sheet recovery |
| Regression | canonical v1.0 plus v0.5-v0.9 representative fixtures |
| Operations | idempotency, concurrency, retries, dependency failure and rollback |
| Journal regression | full relevant Journal suite when its bootstrap, roles or schema changes |

A screenshot, static HTML prototype or passing mock-only test is not sufficient.

## 2. Canonical biological fixtures

### Betta

- legacy output b02: 80 eggs, 52 materialized, remaining 28, historical commerce blocked;
- legacy output b03: 100 eggs, 61 materialized, remaining 39, historical commerce blocked;
- legacy output b04: 100 eggs, 84 materialized, remaining 16, only 16 can be commerce-authoritative;
- no scalar/structured double count.

### Medaka

- m01: 18 eggs, 2 removed, 12 legacy hatch, remaining 4;
- m02: 24 eggs, 9 structured hatch, remaining 15;
- multiple independent egg batches and repeated hatch observations preserve distinct provenance.

### Neocaridina

- population-derived source;
- parents unknown;
- recruitment and selection retain source-population provenance;
- no exact parent or generation claim is fabricated.

### Annual killifish

- wetting attempt 1, re-dry, wetting attempt 2;
- hatch is tied to the exact attempt;
- development observation, wetting action and hatch fact remain distinct.

## 3. Security and database gates

Run on disposable Postgres:

- Journal-owned migration applies from the exact current Journal main at implementation admission, after local migration prefix 028 and as planned local sequence 029;
- a fresh provider timestamp is assigned after provider version 20260915093928 and is read back after apply; this plan claims no provider application;
- marker/precondition rejects a wrong Journal base or migration collision;
- migration is idempotent;
- rollback/compensating script is proven before data;
- runtime role has SELECT/INSERT on admitted relations and column-scoped UPDATE only on mutable context/projection relations;
- direct UPDATE of append-only facts, output/group operations, provenance, observations, dispositions, quantity ledger, handoff history or committed receipts is denied by grant, RLS policy and the database no-update guard;
- RLS is enabled and forced;
- owner A cannot read or write owner B;
- cross-user Journal tank/livestock/media composite FKs fail;
- missing owner scope fails closed;
- Breeder login cannot access Journal Intelligence or Core tables;
- no runtime DELETE/TRUNCATE/DDL;
- account deletion/export/retention includes breeder_*;
- private media cannot enter public handoff.

The current provider readback has no Breeder foundation tables; `public.catalogue_breeder_attributions` is the only matching public table, with RLS enabled and zero rows. Security advisors report 16 mutable-function-search-path warnings, so no security PASS may be inferred from this plan.

## 4. Domain and concurrency gates

- original output minus removed minus materialized hatch equals remaining;
- no negative output or group quantity;
- split conservation;
- merge conservation;
- loss only changes affected group;
- move/stage/observation do not change quantity;
- provenance is conserved across split/merge/promotion;
- exact parent claims require evidence;
- disposition changes current eligibility;
- suggestion completion does not create a biological observation;
- duplicate same-hash idempotency returns original readback;
- duplicate different-hash idempotency conflicts;
- create commands may omit expected revision and establish revision 1;
- updates and commands against mutable existing state reject a missing expected revision;
- output creation before any offspring group writes an output operation source plus `OUTPUT_CREATED` ledger row with no group operation reference;
- single-target mutable commands reject a stale expected revision;
- group mutable commands require an exact canonical `expectedRevisions` vector containing every affected existing group, reject missing/extra/duplicate entries, and reject the whole transaction when any one group is stale;
- the persisted `expected_group_revisions` operation representation matches the validated request vector;
- concurrent split/merge cannot overspend quantity or deadlock;
- transaction rollback leaves no partial biological state.

Deferred P7 commerce reconciliation gates, excluded from the 001A foundation and 001B service/API slices:

- AquaticFinder owns commercial allocation and outcome receipts; Breeder stores only validated immutable acceptance evidence;
- allocation and outcome quantities are non-negative;
- cumulative allocation cannot exceed the acknowledged allocation, and cumulative outcome cannot exceed the acknowledged allocation or accepted allocation available for that outcome, unless an explicit approved exception reference, reason and approval receipt is present;
- duplicate external reference with the same request hash returns the original receipt, while a different hash conflicts;
- duplicate owner/idempotency key follows the same-hash replay and different-hash conflict rule;
- negative, over-limit or conflicting receipts do not write `breeder_quantity_ledger` or mutate biological history.

## 5. API and browser gates

- authenticated Core session required;
- all foundation endpoints return owner-scoped data only;
- invalid UUIDs do not disclose existence;
- domain error codes are stable;
- committed readback survives page refresh;
- first vertical slice works at all four widths;
- no horizontal overflow;
- no clipped or unreachable primary action;
- keyboard/focus/Escape paths pass;
- empty, loading, validation, dependency failure and retry states pass;
- second-account cross-user denial passes in browser E2E.

The required first vertical E2E sequence is: real Core-authenticated shell -> Today -> Programs -> create Program -> record output -> explicit hatch -> create offspring group -> link same-owner Journal tank -> refresh -> exact committed readback. The browser must never receive database credentials or choose owner identity.

## 6. Journal regression rule

Any Journal PR carrying local migration sequence 029 or changing bootstrap, roles, grants, account deletion or shared Journal relations must run:

- focused Breeder migration/security tests;
- Journal runtime-role verifier;
- Journal database-guard and disposable-database isolation tests;
- relevant Journal full test/build suite;
- relevant Android/JI regression gates required by the current Journal shared-boundary review;
- exact-head independent review.

A Breeder PR cannot claim shared-database readiness while the corresponding Journal PR is unmerged, the real Core-auth binding is unresolved, or required gates are red.

## 7. Admission evidence bundle

Each implementation package must publish:

~~~text
exact base SHA
exact head SHA
changed-file inventory
migration/role target
test commands and counts
negative security results
browser width results
regression disposition
rollback unit
production mutation = NO or explicitly admitted
~~~

Production migration and deployment require a separate Founder-gated evidence bundle after P8.
