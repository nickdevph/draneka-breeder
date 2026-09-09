# Draneka Aquarium Breeder — Holistic v1.0 Candidate

Date: 2026-09-09
Status: **PRODUCED / NON-CANONICAL / PENDING INDEPENDENT REVIEW**
Branch: `prototype/v1.0-simplify-and-qualify`

## Exact candidate binding

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V1.0-SIMPLIFY-QUALIFY-CANDIDATE.html`
- Google Drive ID: `18egQ7iZ5jCyDJxoHQ9a1SvI2PIdfigos`
- MIME: `text/html`
- Exact bytes: `456195`
- SHA-256: `8c65ef2f2121d71ba29d4bb7d73bf21bc7b1ad71c684df1abe458b8f477b8909`

The candidate is a new immutable Drive object. It does not overwrite the canonical v0.9 artifact.

## Exact canonical predecessor

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.9-COMMERCE-HANDOFF-EVIDENCE-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Google Drive ID: `1sZ6TOO25Otne0S5Atbul6s4SRHQMnN-4`
- Exact bytes: `437576`
- SHA-256: `74b6912c393948fa3b9bf77f6dd21067cceca620f6d09747af1379791c4677b0`
- Canonical merge commit: `2b2953a62561a21cb03fcb4c42e14bf03c1cd46b`

## Bounded producer changes

No new breeder domain capability was introduced.

The candidate changes only simplify/qualify surfaces:

1. **Primary navigation parity**
   - narrow and wide layouts use the same primary destinations: `Today / Programs / Log / Grow-out / More`;
   - redundant desktop-only primary shortcuts for Breeding stock and Intelligence were removed;
   - Commerce remains contextual rather than becoming primary navigation.

2. **Today simplification**
   - the daily surface focuses on planned attention, active Programs and Journal connection;
   - repeated educational parentage content was removed from the daily surface;
   - `Start Breeder Round` and `Log what happened` remain direct actions.

3. **More consolidation**
   - tools are grouped under `Daily work & records`, `Breeding decisions & evidence`, and `Connections & setup`;
   - the standalone Commerce row is removed from More because commerce remains reachable from source records and the Journal/AquaticFinder connection.

4. **Terminology**
   - `Breeder Round` capitalization is normalized;
   - Program-level `More` is labelled `Tools`;
   - Grow-out screen title aligns with primary navigation terminology.

5. **Recovery**
   - Program search/filter empty state can reset to default active Programs;
   - Grow-out filtered-empty state can return to all groups;
   - missing-record state provides explicit routes to Today and Programs.

6. **Accessibility affordances**
   - skip-to-main-content link;
   - visible focus treatment;
   - 44 px minimum targets on common action/navigation controls;
   - form-error live/alert semantics;
   - existing dialog focus/return behavior is retained.

7. **Qualification surfaces**
   - v1.0 guide records frequent-task interaction targets;
   - mobile/web parity boundary is explicit;
   - independent breeder usability review and implementation-admission evidence are mandatory review outputs rather than producer PASS claims.

## Explicit authority boundary

The candidate does not authorize or add backend/API/schema/database changes, Android/web production implementation, production AquaticFinder integration, deployment, signing, release or any v1.1+ scope.

Canonical v0.9 remains authoritative unless and until this exact candidate independently passes, receives Founder promotion, and the v1.0 iteration PR merges to `main`.

`HOLISTIC_V1_0_CANDIDATE_PRODUCED = YES`

`HOLISTIC_V1_0_EXACT_BINDING = 456195_BYTES / 8c65ef2f2121d71ba29d4bb7d73bf21bc7b1ad71c684df1abe458b8f477b8909`

`HOLISTIC_V1_0_PROMOTION_ELIGIBLE = NO_PENDING_INDEPENDENT_REVIEW`

`HOLISTIC_V1_0_CANONICAL = NO`