# Draneka Aquarium Breeder — Holistic Prototype Iteration Workflow

This workflow is mandatory beginning with holistic v0.5.

## Repository meaning

- `main`: canonical or historical authority only.
- `prototype/vX.Y-*`: active non-canonical holistic iteration work.
- Pull request: durable container for the complete version iteration, including candidates, corrections, review receipts, and final promotion state.

## Lifecycle

```text
canonical main
  -> create prototype/vX.Y-<scope>
  -> open draft PR to main
  -> produce immutable candidate
  -> bind filename + size + SHA-256 + durable object
  -> producer validation
  -> independent review
     -> if corrections required: correct in same PR and bind a new immutable candidate
     -> repeat independent review as needed
  -> exact candidate becomes promotion-eligible
  -> founder promotes exact reviewed artifact
  -> mark PR ready to merge
  -> merge PR to main
  -> version becomes repository-canonical
```

## Version rule

One holistic version uses one branch and one PR.

Review corrections do not create another PR. They create later commits and a new immutable candidate binding inside the same PR.

A new holistic version gets a new branch and PR.

## Required PR evidence before merge

The PR must contain or durably reference:

1. exact canonical predecessor binding;
2. bounded product question and allowed scope;
3. exact candidate artifact binding;
4. producer validation receipt;
5. independent review receipt(s);
6. correction receipts when applicable;
7. final exact artifact binding;
8. founder promotion decision;
9. explicit statement that implementation/backend/deployment authority is unchanged unless separately admitted.

## Merge semantics

For v0.5 and later, founder promotion is necessary but not sufficient for repository canonicality. The version becomes canonical only when the promoted iteration PR is merged to `main`.

The exact artifact SHA-256 is still the byte-level product/design payload authority; the merge establishes which byte-bound artifact `main` recognizes as canonical.

## Failure behavior

- Independent review `PASS_WITH_CORRECTIONS` or `CHANGES_REQUIRED`: keep PR open; correct within same PR.
- Review `FAIL`: keep or close PR based on founder disposition; never merge a failed candidate as canonical.
- Founder declines promotion: do not merge as canonical.
- A candidate superseded inside the PR remains immutable historical evidence.

## v0.4 transition

Holistic v0.4 is the final transition exception because it was independently reviewed and founder-promoted before this workflow was adopted. Its authority remains valid on `main`; no synthetic retroactive PR is required.

See `decisions/0006-prototype-iteration-pr-canonicalization-model.md`.
