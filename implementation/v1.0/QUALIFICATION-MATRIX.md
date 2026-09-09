
# Breeder v1.0 Test and Qualification Matrix

Status: IMPLEMENTATION-READY PLAN  
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

- migration applies from current Journal base plus final 024;
- marker precondition rejects wrong base;
- migration is idempotent;
- rollback/compensating script is proven before data;
- runtime role has only admitted grants;
- RLS is enabled and forced;
- owner A cannot read or write owner B;
- cross-user Journal tank/livestock/media composite FKs fail;
- missing owner scope fails closed;
- Breeder login cannot access Journal Intelligence or Core tables;
- no runtime DELETE/TRUNCATE/DDL;
- account deletion/export/retention includes breeder_*;
- private media cannot enter public handoff.

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
- stale revision conflicts;
- concurrent split/merge cannot overspend quantity or deadlock;
- transaction rollback leaves no partial biological state.

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

## 6. Journal regression rule

Any Journal PR carrying 025 or changing bootstrap, roles, grants, account deletion or shared Journal relations must run:

- focused Breeder migration/security tests;
- Journal runtime-role verifier;
- Journal database-guard and disposable-database isolation tests;
- relevant Journal full test/build suite;
- Android/JI regression gates required by the final Journal 024 review;
- exact-head independent review.

A Breeder PR cannot claim shared-database readiness while the corresponding Journal PR is unmerged or its required gates are red.

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
