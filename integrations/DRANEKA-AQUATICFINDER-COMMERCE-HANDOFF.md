# Draneka Breeder -> Draneka AquaticFinder Commerce Handoff

Date: 2026-09-08
Status: Product boundary / future integration contract

## Boundary

**Draneka Aquarium Breeder** owns breeding truth and breeder operations.

**Draneka AquaticFinder** owns commerce-channel truth and marketplace operations.

Breeder should never require the breeder to recreate lineage, identity, photos, age, quantity, grade, or provenance merely to list livestock for sale.

AquaticFinder should never rewrite ancestry, reproductive events, cohort history, or breeder selection evidence.

## Expected user flow

1. Breeder completes a selection/availability decision in Draneka Breeder.
2. One or more individuals or a cohort-derived batch are marked `sale-ready`.
3. The breeder chooses which facts/media may be exposed publicly.
4. Breeder creates a commerce handoff object.
5. Draneka AquaticFinder turns that object into one or more marketplace-specific listing drafts.
6. AquaticFinder evaluates current marketplace policy/eligibility before offering publish actions.
7. AquaticFinder manages publish/update/pause/end, quantity allocation, channel pricing, orders/reservations, and listing status.
8. Sales/dispositions can flow back to Breeder as commercial outcomes without mutating historical breeding records.

## Minimum handoff payload concept

The eventual API/schema may differ, but product semantics should preserve:

- breeder account/source identity;
- source program ID;
- source individual/cohort/batch IDs;
- species scientific/common names;
- variety/strain/line name where public;
- sex and confidence when known;
- age/date-of-birth/hatch and confidence when known;
- quantity available;
- breeder-defined grade/trait labels;
- selected public phenotype facts;
- public lineage/provenance summary;
- breeder/source attribution preferences;
- location/fulfilment origin at an appropriate privacy level;
- photos/media selected for commerce;
- care/shipping notes authored or approved by the breeder;
- sale-ready timestamp;
- revocation/withdrawal state.

## Marketplace manager design

AquaticFinder's initial commerce value proposition should be **one inventory/listing workspace that adapts listings to multiple supported marketplaces**.

Expected capabilities:

- reusable source listing/profile;
- channel-specific draft generation;
- marketplace category/attribute mapping;
- title and description variants;
- photo selection/order per channel;
- price and quantity per channel;
- publish/update/end where supported by official APIs;
- central status/external listing ID tracking;
- oversell prevention and quantity reconciliation;
- channel-specific shipping profiles;
- policy eligibility and warnings;
- seller-controlled final publish action;
- order/reservation reconciliation later.

## Policy-aware publishing is mandatory

Marketplace support cannot be represented as a simple compatibility matrix hard-coded forever.

At publish time, AquaticFinder should evaluate:

- item type (fish, shrimp, snail, plant, eggs, food/culture, equipment, etc.);
- species/protected status where relevant;
- seller jurisdiction;
- destination jurisdiction;
- marketplace category/policy;
- shipping method constraints;
- current API capability.

The UI should distinguish:

- `Eligible to publish`
- `Eligible with requirements`
- `Not eligible on this marketplace`
- `Policy requires review`
- `Integration cannot publish automatically`

## Current marketplace research snapshot — 2026-09-08

### eBay

Current eBay live-animal policy allows a limited set of live animals including **tropical fish**, with sellers responsible for permits and safe overnight shipping. Not every aquatic animal is automatically included merely because tropical fish are permitted.

The eBay Inventory API supports inventory items, offers, publishing, quantity updates, and listing management. This makes eBay a plausible first automated commerce channel for eligible aquarium products.

References:

- Live animals policy: https://www.ebay.com/help/policies/prohibited-restricted-items/live-animals-policy?id=4327
- Inventory API overview: https://developer.ebay.com/api-docs/sell/inventory/static/overview.html

### Etsy

Etsy's prohibited-items policy effective 2026-08-11 explicitly prohibits **live animals**. Therefore live-fish/shrimp syndication to Etsy must not be offered.

Etsy still has an Open API capable of listing and inventory management for permitted products. It may therefore be relevant to other AquaticFinder inventory classes only where those classes meet Etsy's current marketplace and creativity standards.

References:

- Prohibited Items Policy: https://www.etsy.com/ca/legal/policy/prohibited-items-policy-effective/1475031537022
- Open API listings tutorial: https://developers.etsy.com/documentation/tutorials/listings/

## Initial marketplace-priority recommendation

Do not choose channels only because sellers commonly mention them. Prioritize channels using four gates:

1. the target aquarium item is permitted;
2. the marketplace has sufficient seller demand;
3. an official/stable integration path exists;
4. the integration materially removes duplicate listing work.

The first AquaticFinder prototype should prove the **policy-aware multi-channel listing model** before attempting a large connector catalog.

## Non-goals for Breeder

Breeder must not become responsible for:

- marketplace OAuth/setup;
- marketplace policy parsing;
- channel fees;
- SEO/title optimization per marketplace;
- order inboxes;
- buyer messaging;
- postage labels;
- channel analytics;
- returns/disputes;
- cross-channel stock reconciliation.

Those are Draneka AquaticFinder responsibilities.
