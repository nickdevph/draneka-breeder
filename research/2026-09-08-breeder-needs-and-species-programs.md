# Breeder needs and species-specific program research

Date: 2026-09-08
Status: Durable product research; informs future prototype revisions but is not prototype authority

## Executive conclusion

Draneka Aquarium Breeder should model a breeding operation, not merely tanks with breeding notes.

The stable product backbone should be:

`Breeding Program -> Breeder Stock -> Pairing / Parent Group -> Reproductive Event -> Cohort -> Grow-out / Split -> Selection -> Holdback / Disposition -> Next Generation or Commerce Handoff`

The strongest usability architecture is **one stable breeding core plus species/reproductive overlays**. The overlay changes milestones, suggested work, vocabulary, timing guidance, and optional fields while preserving the same core object model and navigation.

This avoids both failure modes:

- a universal rigid checklist that does not fit real breeding biology; and
- dozens of species-specific mini-apps that overwhelm the breeder and fragment data.

## Cross-species breeder needs

### 1. Program continuity

Breeders need to preserve the chain from parent stock to reproductive event, offspring cohort, selection, holdback, and subsequent generations. Tanks and jars change; ancestry and program identity should not.

### 2. Cohort-first offspring tracking

Individual records are appropriate for breeders and selected holdbacks, but not for every egg/fry/shrimplet. Cohorts require first-class operations: estimate/count, move, split, merge, stage change, survival/loss, photo, feeding, selection, and promotion of selected individuals.

### 3. Fast operational logging

Breeder software loses to notebooks/spreadsheets when normal work takes too many taps. Routine breeder actions should be optimized for tank-side capture and progressive disclosure.

### 4. Dynamic work rather than fixed checklists

Breeder Round should be assembled from recurring husbandry, lifecycle milestones, explicit breeder schedules, and exception/risk triggers. Species templates may suggest work but must never mark an event complete without breeder evidence.

### 5. Selection as a historical process

Selection is not a single field. A breeder may evaluate the same animal or cohort differently over time. Trait/grade evaluations should therefore be timestamped and evidence-backed, with the selection decision recorded separately.

### 6. Lineage with uncertainty

Known parentage should derive from reproductive events. Group spawning, unknown sire/dam, incomplete ancestry, and locality/strain provenance must be first-class rather than forced into false certainty.

### 7. Evidence and reporting

Aquarium-club Breeder Award Programs commonly require proof of spawning, species/variant identity, photos, and survival to a juvenile milestone such as 60 days. Draneka can eventually generate spawn/provenance reports from normal operating records instead of asking breeders to recreate history afterward.

## Species-program architecture

Use two layers:

### Layer A — reproductive archetype

Examples:

- bubble-nest / anabantoid
- livebearer
- externally collected adhesive eggs
- mop/plant-spawning killifish
- soil/annual killifish
- cave/substrate brood with parental care
- mouthbrooder
- cave-spawning catfish
- egg scatterer / substrate egg layer
- caridean shrimp colony/selective line
- marine pelagic larval

### Layer B — species or breeder overlay

The species overlay supplies:

- terminology;
- recommended parent unit;
- likely lifecycle milestones;
- optional observations/measurements;
- suggested task timing;
- parent-removal/parental-care patterns;
- cohort split/sexing/grading moments;
- selection dimensions;
- known edge cases;
- evidence prompts.

All timings remain guidance, not facts.

---

# Initial species research wave

The first six templates were selected to maximize workflow diversity, not because they are the only important breeder species.

## 1. Betta splendens — bubble-nest / individually managed holdbacks

### Research signals

The International Betta Congress maintains breeding resources, a spawn log, and show standards. Its Species Complex Management guidance emphasizes breeder recordkeeping and explicitly calls for recording pH, temperature, water volume, feed, tank setup, hardness, and, when available, TDS/conductivity, plus spawn results and eventual sex ratio/counts. IBC breeder discussions also distinguish conditioning, introduction/spawn, egg/fry care by the male, free-swimming fry, grow-out, and eventual individual management.

### Product implications

**Parent unit:** usually explicit male + female.

**Suggested lifecycle:**

`conditioning -> introduction -> spawn observed -> eggs/nest -> hatch -> free-swimming -> male removal -> fry grow-out -> juvenile grading -> separation/jarring as needed -> breeder/show/sale selection`

**Important optional data:**

- conditioning start and diet;
- introduction date/time;
- aggression/injury note;
- spawn date;
- nest/egg observation;
- hatch and free-swimming dates;
- parent-removal dates;
- fry count estimates;
- sexing/juvenile separation;
- phenotype/show-standard evaluations;
- jar/barracks occupancy where used.

**Breeder Round triggers:**

- conditioning check;
- inspect nest/eggs;
- free-swimming transition review;
- parent removal reminder;
- fry-food transition;
- grow-out density review;
- juvenile separation/selection review.

**UX rule:** a beginner should see only the next likely milestone. Advanced environmental and show-evaluation fields remain collapsed unless enabled.

**Sources:**

- International Betta Congress standards/resources: https://www.ibcbettas.org/memberhome/standards/
- IBC Species Complex Management recordkeeping: https://www.ibcbettas.org/about-betta-splendens/smp/species-complex-management/
- IBC breeding forum: https://www.ibcbettas.org/forums/forum/betta-breeding/

## 2. Fancy guppy / Poecilia reticulata — livebearer line breeding

### Research signals

The International Fancy Guppy Association describes selective/show breeding as a line-management problem rather than merely recording births. IFGA material recommends keeping offspring from different females separated when building parallel lines, separating sexes at roughly 3–6 weeks, controlling density, repeatedly culling/selecting, and choosing future breeding/show stock as juveniles mature. IFGA also describes maintaining backup breeder sets and planned line/inbreeding strategies.

### Product implications

**Parent unit:** pair, trio, or controlled male/female group; maternal identity may be stronger than sire certainty in some setups.

**Suggested lifecycle:**

`breeder group -> mating exposure -> gravid observation -> birth/drop -> maternal cohort -> early grow-out -> sex separation -> male/female subcohorts -> repeated selection -> breeder/show/sale stock`

**Important optional data:**

- dam identity and sire certainty;
- line/strain;
- birth/drop date;
- fry estimate;
- maternal cohort identity;
- sex-separation date;
- deformity/health removals;
- phenotype selection dimensions;
- backup line designation;
- density/tank allocation.

**Breeder Round triggers:**

- gravid check;
- expected drop window;
- density review;
- sex-separation review;
- juvenile selection review;
- backup-line reminder.

**Special edge case:** female livebearers may store sperm, so the system should permit uncertain or historical sire attribution rather than forcing the most recent male as father.

**Sources:**

- IFGA Basics of Show Breeding: https://www.ifga.org/basicbreeding
- IFGA How to Become a Good Breeder: https://www.ifga.org/becomeagoodbreeder
- IFGA Selecting Breeders: https://www.ifga.org/selectingbreeders

## 3. Medaka / Oryzias latipes — repeated egg collection and line preservation

### Research signals

The European Medaka Association describes breeding groups, repeated spawning, egg removal to protect eggs from adults, separate fry rearing, and selective line management. Its genetics guidance emphasizes preserving breeding groups, parent/result records, health/form/behaviour as well as colour, and avoiding weak/deformed lines.

### Product implications

**Parent unit:** pair or breeding group, often repeated over a spawning period.

**Suggested lifecycle:**

`breeding group -> spawning day -> egg collection batch -> incubation -> hatch -> fry cohort -> juvenile grow-out -> phenotype review -> line selection`

**Important optional data:**

- breeding group composition;
- collection date and collection count;
- fertilized/unfertilized/failed eggs;
- incubation container;
- hatch batch;
- variety/line traits;
- outdoor/indoor season context;
- parent-group separation;
- juvenile selection.

**Breeder Round triggers:**

- collect eggs;
- inspect/remove failed eggs;
- hatch check;
- first-food transition;
- move fry to grow-out;
- line/phenotype selection.

**UX rule:** repeated egg collection should be one-tap batch logging, not a new full spawn form every morning.

**Sources:**

- European Medaka Association breeding hub: https://www.ema-medaka.com/en/knowledge/breeding
- EMA genetics/selection guidance: https://ema-medaka.com/en/knowledge/genetics

## 4. Killifish — mop/plant spawner and annual soil-spawner split

### Research signals

The American Killifish Association documents materially different workflows for plant/mop spawning and annual/soil-spawning species. Mop eggs may be collected individually or moved with the entire mop. Annual eggs may be stored in peat or another medium, undergo variable diapause, be labelled with species and spawning date, receive an anticipated hatch/wetting date, be visually assessed for development, and sometimes require repeat wet/dry cycles because eggs from one collection can develop at different rates.

### Product implications

Killifish cannot be represented by a single generic `spawn -> hatch` timer.

**Mop/plant-spawner lifecycle:**

`breeder pair/group -> collection period -> egg batch -> water/peat incubation -> hatch window -> fry cohort -> grow-out`

**Annual/soil-spawner lifecycle:**

`breeder pair/group -> spawning-medium collection -> egg-medium batch -> storage/incubation -> development check -> wetting attempt -> hatch cohort -> optional re-dry/re-wet -> grow-out`

**Important optional data:**

- locality/location code;
- collection period rather than one exact mating time;
- egg batch and medium;
- medium wetness/condition;
- storage temperature;
- predicted wet/hatch window;
- embryo-development observation;
- wetting attempt number;
- hatch count per attempt;
- re-dry status;
- locality-strain provenance.

**Breeder Round triggers:**

- collect/check mop;
- inspect incubating egg batch;
- development/wetting-window review;
- perform wetting attempt;
- re-dry decision;
- fry first-food/grow-out review.

**UX rule:** killifish overlay should display `Egg batches` prominently; generic fish terminology such as “spawn date” is insufficient.

**Sources:**

- American Killifish Association breeding/egg-incubation collection: https://aka.org/32-articles-on-breeding-killifish-incubating-and-hatching-eggs-and-raising-fry-1996-2000/
- AKA incubation overview: https://aka.org/breeding-fish-incubating-and-hatching-eggs-an-overview/
- AKA incubation timing guidance: https://aka.org/incubating-eggs-a-judgement-call-a-few-tips-on-development-and-hatching/

## 5. Neocaridina davidi — colony/selective-line breeding

### Research signals

Neocaridina selective breeding is usually colony-based, with breeder populations rather than explicit one-male/one-female pairings. Practical breeder guidance and community practice repeatedly emphasize removing lower-grade or off-target animals from the breeding population, keeping colour/line populations separate, and repeatedly selecting the best offspring over generations. This makes breeding-stock population and selection history more important than exact parent pair identity.

### Product implications

**Parent unit:** breeding colony or selected breeder subset; exact individual parentage often unknown.

**Suggested lifecycle:**

`line/colony -> breeder population -> berried observation -> hatch/recruitment -> juvenile cohort/population -> grade/trait review -> select breeder subset -> move lower-grade animals out of breeding population -> repeat generation`

**Important optional data:**

- line/colour/morph;
- breeder-colony membership;
- berried female observation;
- juvenile recruitment estimate;
- grade/trait evaluation with photo;
- breeder-retained vs non-breeding disposition;
- generation estimate/certainty;
- source population/provenance.

**Breeder Round triggers:**

- berried/recruitment check;
- population-density review;
- grading session;
- breeder-subset refresh;
- line contamination warning when incompatible breeding populations are mixed.

**Critical model rule:** do not invent individual parentage. Colony ancestry can be expressed as known source population / breeder set rather than false sire/dam edges.

**Terminology rule:** use neutral `remove from breeding population`, `non-breeding`, `sale`, `rehome`, `retire`, etc. The breeder may optionally use the term `cull`, but the product should not assume that culling means euthanasia.

**Sources:**

- Aquarium Co-Op selective-breeding overview: https://www.aquariumcoop.com/blogs/aquarium/keeping-and-breeding-cherry-shrimp-neocaridina-davidi
- Recent breeder/community examples of line selection and cull-tank workflows: https://www.reddit.com/r/shrimptank/comments/1kkatzd and https://www.reddit.com/r/shrimptank/comments/1u0tkqx/

## 6. Apistogramma-type cave brooders — parental care and fry transfer

### Research signals

Specialist Apistogramma breeding discussion emphasizes cave/substrate spawning, strong female brood care, and distinct parent-management decisions after spawning/free-swimming. This produces a workflow unlike Betta parent removal or guppy live birth.

### Product implications

**Parent unit:** pair or controlled group depending breeder strategy/species.

**Suggested lifecycle:**

`condition/pair -> cave/territory -> eggs -> female brood care -> wrigglers/hatch -> free-swimming fry -> male separation if needed -> maternal fry care -> independent fry cohort -> grow-out -> selection`

**Important optional data:**

- cave/site identity;
- spawn-site observation;
- female brood behaviour;
- male removal/territory action;
- free-swimming date;
- parental-care end;
- fry-group move;
- later sex/phenotype selection.

**Breeder Round triggers:**

- inspect brood site without forcing disturbance;
- hatch/free-swimming transition;
- male-separation decision;
- fry-food transition;
- maternal-care/end-of-care review.

**Source:**

- Apistogramma.com specialist discussions: https://apistogramma.com/forum/threads/breeding-apistogramma-cacatuoides.12567/ and https://apistogramma.com/forum/threads/first-time-breeding-a-cacatuoides.24970/

---

# Second research wave

Before implementing a broad species library, research should next cover workflow types not fully represented above:

1. **Corydoras** — group spawning, egg collection/removal, batch hatching, fry survival.
2. **Ancistrus / cave-spawning Loricariids** — cave ownership, male egg care, multiple females in some setups, fry emergence.
3. **African mouthbrooding cichlids** — holding female, natural release vs stripping/incubation, maternal recovery, fry cohorts.
4. **Substrate-spawning/parental cichlids** — pair bonds, territory, parental care and brood transfer.
5. **Discus/angelfish** — substrate eggs, parent-fed fry in discus, pair performance tracking.
6. **Rainbowfish / egg scatterers** — repeated collection windows and batch incubation.
7. **Clownfish/marine larval breeders** — spawning cycles, hatch night, rotifer/live-feed dependency, larval tank and metamorphosis.
8. **Caridina shrimp** — line/grade logic plus more demanding environmental control and variant-specific practices.

## Evidence from breeder-award programs

Aquarium societies independently classify breeding by biologically different groups such as livebearers, anabantoids, catfish, cichlids, killifish, marine fish and invertebrates. Some explicitly distinguish mouthbrooders from substrate spawners and mop-spawning from soil-spawning killifish. This supports using reproductive archetypes underneath species overlays rather than treating all aquatic breeding as one generic workflow.

Examples:

- Fort Wayne Aquarium Society BAP: https://fwaquariumsociety.org/breeder-award-program/
- San Francisco Aquarium Society BAP groups: https://www.sanfranciscoaquariumsociety.org/copy-of-bap
- Aquarist Society of Central Maryland BAP definitions: https://www.ascmaryland.com/programs/BAP/rules
- American Livebearer Association BAP: https://livebearers.org/programs/breeders-award-program-bap/bap-rules

---

# UI implications for species-aware programs

## Default screen should stay simple

A breeder opening a program should initially see only:

- current parent/breeder set;
- current reproductive event or cohort status;
- next suggested action;
- active offspring/cohorts;
- one-tap log action;
- exceptions requiring attention.

Advanced fields belong behind `Details`, `Program setup`, or context-sensitive actions.

## Progressive disclosure examples

A Betta breeder sees `Nest`, `Free swimming`, and `Separate juveniles` only when relevant.

A Medaka breeder sees `Collect eggs` and `Egg batches` rather than a generic spawn form.

An annual killifish breeder sees `Egg medium`, `Incubation`, and `Wetting attempts`.

A shrimp breeder sees `Breeder population`, `Grade`, and `Move out of breeding line`, not forced sire/dam fields.

A guppy breeder sees `Maternal cohort` and `Sex separation`.

## Species-template confidence

The system should distinguish:

- **Recorded fact** — breeder explicitly logged it.
- **Derived fact** — e.g. cohort age from hatch/birth date.
- **Template suggestion** — likely next action based on species/program settings.
- **Breeder override** — custom schedule or alternative method.

A template suggestion must never silently become a recorded event.

---

# Commerce research note

Draneka AquaticFinder, not Breeder, will own marketplace management.

A key finding is that marketplace eligibility varies by channel and item class. eBay's current live-animal policy allows tropical fish under specified conditions, while Etsy's policy explicitly prohibits live animals. Cross-market publishing therefore requires a policy/eligibility engine rather than a universal syndication button.

Both platforms expose APIs that can support listing-management software in permitted categories:

- eBay Inventory API can create/manage inventory items and offers and publish listings: https://developer.ebay.com/api-docs/sell/inventory/static/overview.html
- Etsy Open API v3 supports shop listing/inventory management: https://developers.etsy.com/documentation/tutorials/listings/

Policy references:

- eBay live animals policy: https://www.ebay.com/help/policies/prohibited-restricted-items/live-animals-policy?id=4327
- Etsy prohibited items policy, effective 2026-08-11: https://www.etsy.com/ca/legal/policy/prohibited-items-policy-effective/1475031537022

The marketplace manager must evaluate eligibility at publish time because platform policy, jurisdiction, species status, and shipping rules can change.
