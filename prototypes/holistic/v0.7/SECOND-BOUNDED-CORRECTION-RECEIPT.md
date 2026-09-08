# Producer Second Bounded-Correction Receipt — Holistic v0.7

Date: 2026-09-08
Status: **SECOND_BOUNDED_CORRECTION_PRODUCED / NON-CANONICAL**
PR: `#7`

## Founder-authorized correction boundary

This correction responds only to the fresh independent-review findings against the prior bounded-correction candidate:

1. `Non-breeding` and `Retire` decisions did not override stale breeding-readiness state in Pair Builder eligibility.
2. mixed filial labels such as recorded `F1 × F2` were incorrectly converted to a precise `F3` label.
3. Programs without a seeded `goalHistory` entry lost their initial goal from the dedicated goal-history ledger on first edit.

No v0.8/v0.9 scope, navigation redesign, backend/API/schema/database/deployment mutation, Android implementation authority, or canonical promotion is admitted.

## Prior reviewed candidate preserved

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `1WCEPsAM35WsGo-y5IdJ0w5pSNBXHV_Hg`
- Size: `330298 bytes`
- SHA-256: `6c47d96330fca26dd7d2c2d9d1f7dcc2ba0753b283d23f19415793cca9bc0186`
- Independent review disposition: `CHANGES_REQUIRED`

The prior Drive object was not overwritten.

## New immutable second bounded-correction candidate

- Artifact: `DRANEKA-AQUARIUM-BREEDER-HOLISTIC-PROTOTYPE-V0.7-SELECTION-LINE-DEVELOPMENT-SECOND-BOUNDED-CORRECTION-CANDIDATE.html`
- Drive ID: `13LbZKVuq02tk2Vmhb4mBvWipChpv_V7r`
- Drive URL: `https://drive.google.com/file/d/13LbZKVuq02tk2Vmhb4mBvWipChpv_V7r/view`
- Exact size: `332362 bytes`
- SHA-256: `f82ef39241b36c0325ff918b9e95b447a964b4426ca2fe530c70e86e3b329930`

A fresh raw Drive re-download returned exactly `332362` bytes and independently hashed to the same SHA-256 above.

## Correction 1 — disposition authority

Breeding readiness remains a separate historical assessment; the correction does not silently rewrite `ready=true` to false. Instead, current selection disposition now participates in downstream breeding eligibility.

Current blocking dispositions are:

- `Non-breeding`;
- `Sale / rehome`;
- `Retire`.

`Holdback` does not block an already-ready individual, but it also does not create breeding readiness. Pair Builder still requires explicit readiness plus its existing individual/provenance constraints.

The same current-disposition boundary is also applied when existing stock is chosen for a new or edited breeding arrangement, preventing an explicit negative selection decision from being bypassed through another pairing surface.

## Correction 2 — conservative filial-generation semantics

The prior implementation used `max(parent filial number) + 1`, which turned `F1 × F2` into `F3`.

The correction removes that rule. Automatic filial advancement now occurs only when both exact recorded parents:

- are present as two records;
- carry the same precise `F<n>` label; and
- carry the same recorded line text.

Otherwise the result remains explicitly uncertain, for example:

`Generation not established · recorded parents F1 × F2`

The cohort-selection path and named-offspring promotion path continue to use this single conservative helper. Exact parent identity remains preserved independently from the generation label.

## Correction 3 — initial goal-history ledger

Fresh seed data now includes the previously absent initial goal-history records for the Sterbai, killifish and Apistogramma Programs.

A runtime migration also seeds any persisted Program that has a current goal but no goal-history entry, using the Program start/pairing date as the historical effective date where available.

New Programs created with a non-empty goal now create their initial `goalHistory` record at Program creation. `saveGoal` additionally contains a defensive backfill before appending a changed goal if a legacy Program somehow still lacks an initial ledger record.

Existing evaluation and selection goal snapshots remain immutable.

## Regression boundary retained

The correction intentionally leaves the independently passing areas unchanged, including Program isolation, phenotype/genotype separation, evidence attachment, ancestry uncertainty, Betta relatedness warnings, guppy unknown-sire handling, Medaka distinct hatch provenance, Neocaridina population-derived provenance, count/provenance operations, and the full v0.6 killifish mop/wetting/re-dry/second-wetting/explicit-hatch model.

`HOLISTIC_V0_7_SECOND_BOUNDED_CORRECTION_PRODUCED = YES`

`HOLISTIC_V0_7_SECOND_BOUNDED_CORRECTION_DRIVE_ROUND_TRIP = PASS`

`HOLISTIC_V0_7_CANONICAL = NO`

`PR_7_MERGE = HOLD`
