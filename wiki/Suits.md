# Suits & Abilities

All suits are passive — equip the trigger item in the correct slot and the powers activate automatically.

**Status key:**
- `Implemented` — in-game and functional
- `Planned` — on the roadmap, JSON files pending
- `Documented` — lore reference only, no implementation timeline yet

---

## Mark I

> *"Heavy. Crude. Built from nothing in a cave with a box of scraps. But it flew."*

**Status:** Documented
**First Appearance:** Iron Man (2008)
**Material:** Salvaged scrap metal, missile components

### MCU Features
- Built in captivity by Tony Stark and Ho Yinsen under duress
- Primitive boot jets and gauntlet flamethrowers — no repulsors
- Worn once to escape the Ten Rings; abandoned in the desert
- No arc reactor integration — powered by a separate chest-mounted unit

### Planned Abilities

| Ability | Effect |
|---------|--------|
| Gauntlet Flamethrowers | Fire/lava immunity + fire damage on melee hits (via `palladium:damage_immunity` + command) |
| Crude Armor | +12 armor, +4 toughness |
| Boost Jets | Limited flight (`palladium:flight_speed` 0.4 — slow, no heroic pose) |
| No Life Support | No fall damage immunity (unfinished suit) |

---

## Mark II

> *"The first flight-capable suit. Built as a prototype to test propulsion. The chrome titanium alloy proved nearly indestructible — but icing at high altitude cut testing short."*

**Status:** Implemented (placeholder item — `minecraft:iron_chestplate`)
**First Appearance:** Iron Man (2008)
**Material:** Titanium-chrome alloy

### MCU Features
- First suit capable of sustained, directional flight
- Experienced catastrophic icing at high altitude — led directly to MK3's gold-titanium alloy
- Stolen by Lt. Col. James Rhodes, retrofitted as War Machine

### Abilities

| Ability | Effect | Visible |
|---------|--------|---------|
| Propulsion Flight | `palladium:flight_speed` +0.7 | Yes |
| Titanium-Chrome Alloy Armor | `minecraft:generic.armor` +20 | Yes |
| Enhanced Strength | `minecraft:generic.attack_damage` +6 | Yes |
| Impact Protection | Fall damage immunity | Yes |
| *(armor toughness)* | +10 | Hidden |
| *(knockback resistance)* | Full | Hidden |
| *(heroic flight type)* | Iron Man prone pose | Hidden |

---

## Mark III

> *"The real one. Gold-titanium alloy from a Stark Industries satellite design — doesn't ice. Red and gold. This is Iron Man."*

**Status:** Planned
**First Appearance:** Iron Man (2008)
**Material:** Gold-titanium alloy (95.5% titanium, 4.5% gold)

### MCU Features
- Solved the MK2 icing problem using a satellite-derived alloy
- First suit with the iconic red and gold color scheme
- First fully integrated weapons system (repulsors, missiles, flares)
- Heavily damaged during the Obadiah Stane / Iron Monger fight; rebuilt as MK4

### Planned Abilities

| Ability | Effect | Visible |
|---------|--------|---------|
| Propulsion Flight | `palladium:flight_speed` +0.7 | Yes |
| Gold-Titanium Alloy Armor | `minecraft:generic.armor` +22 | Yes |
| Enhanced Strength | `minecraft:generic.attack_damage` +7 | Yes |
| Impact Protection | Fall damage immunity | Yes |
| Fire Resistance | Fire + lava damage immunity | Yes |
| *(armor toughness)* | +11 | Hidden |
| *(knockback resistance)* | Full | Hidden |
| *(heroic flight type)* | Iron Man prone pose | Hidden |

---

## Mark IV

> *"An upgrade. Everything MK3 was, better. Monaco proved it could take a beating — until Whiplash."*

**Status:** Planned
**First Appearance:** Iron Man 2 (2010)
**Material:** Gold-titanium alloy (refined)

### MCU Features
- Incremental refinement over MK3 — improved structural integrity and HUD
- Used during the Monaco Grand Prix when Whiplash attacked; took significant damage
- Retired when MK6 was completed (arc reactor element upgrade)

### Planned Abilities

| Ability | Effect | Visible |
|---------|--------|---------|
| Propulsion Flight | `palladium:flight_speed` +0.75 | Yes |
| Refined Alloy Armor | `minecraft:generic.armor` +22 | Yes |
| Enhanced Strength | `minecraft:generic.attack_damage` +7 | Yes |
| Impact Protection | Fall damage immunity | Yes |
| Fire Resistance | Fire + lava damage immunity | Yes |
| *(armor toughness)* | +12 | Hidden |
| *(knockback resistance)* | Full | Hidden |
| *(heroic flight type)* | Iron Man prone pose | Hidden |

---

## Mark V

> *"The suitcase. For emergencies. It's not pretty, but it works."*

**Status:** Documented
**First Appearance:** Iron Man 2 (2010)
**Material:** Lightweight titanium alloy (compromised for portability)

### MCU Features
- Folds into a briefcase for covert carry — Tony keeps it in his car
- Significantly weaker than mainline suits — no weapons system, limited flight
- Emergency/backup use only; used at Monaco when caught off-guard by Whiplash
- Not intended for sustained combat

### Planned Abilities

| Ability | Effect | Visible |
|---------|--------|---------|
| Emergency Flight | `palladium:flight_speed` +0.6 | Yes |
| Lightweight Armor | `minecraft:generic.armor` +14 | Yes |
| Compact Strength | `minecraft:generic.attack_damage` +5 | Yes |
| Impact Protection | Fall damage immunity | Yes |
| *(armor toughness)* | +6 | Hidden |
| *(knockback resistance)* | 0.5 (partial) | Hidden |

---

## Mark VI

> *"Built on the new element. Clean power. No more palladium poisoning."*

**Status:** Planned
**First Appearance:** Iron Man 2 (2010) / The Avengers (2012)
**Material:** Gold-titanium alloy + new arc reactor element (vibranium-inspired)

### MCU Features
- Powered by a new arc reactor element synthesized by Tony, ending his palladium poisoning
- Triangular chest arc reactor (distinct from the circular design of MK2–MK5)
- Deployed via stationary mechanical arm gantry at Stark Tower
- Carried Tony through a nuclear warhead into the Chitauri mothership during the Battle of New York
- Nearly killed Tony when he lost consciousness re-entering the atmosphere; saved by the Hulk

### Planned Abilities

| Ability | Effect | Visible |
|---------|--------|---------|
| Enhanced Propulsion | `palladium:flight_speed` +0.80 | Yes |
| Advanced Alloy Armor | `minecraft:generic.armor` +24 | Yes |
| Superior Strength | `minecraft:generic.attack_damage` +8 | Yes |
| Impact Protection | Fall damage immunity | Yes |
| Blast Shielding | Explosion damage immunity | Yes |
| Fire Resistance | Fire + lava damage immunity | Yes |
| *(armor toughness)* | +14 | Hidden |
| *(knockback resistance)* | Full | Hidden |
| *(heroic flight type)* | Iron Man prone pose | Hidden |

---

## Mark VII

> *"You're gonna love this one."*

**Status:** Planned
**First Appearance:** The Avengers (2012)
**Material:** Gold-titanium alloy (advanced)

### MCU Features
- First suit with remote autonomous deployment — flies to Tony and assembles around him
- Activated via two magnetic bracelets worn on Tony's wrists
- Carries heavy munitions loadout — used the full arsenal against the Chitauri fleet
- Seen briefly alongside the House Party Protocol suits in Iron Man 3 before being destroyed

### Planned Abilities

| Ability | Effect | Visible |
|---------|--------|---------|
| Enhanced Propulsion | `palladium:flight_speed` +0.85 | Yes |
| Advanced Alloy Armor | `minecraft:generic.armor` +26 | Yes |
| Superior Strength | `minecraft:generic.attack_damage` +9 | Yes |
| Impact Protection | Fall damage immunity | Yes |
| Blast Shielding | Explosion damage immunity | Yes |
| Fire Resistance | Fire + lava damage immunity | Yes |
| Emergency Nano-Repair | `palladium:healing` — 1 HP every 5s | Yes |
| *(armor toughness)* | +16 | Hidden |
| *(knockback resistance)* | Full | Hidden |
| *(heroic flight type)* | Iron Man prone pose | Hidden |

---

## Mark VIII–XIV

**Status:** Documented
**First Appearance:** Iron Man 3 (2013) — House Party Protocol
**Material:** Gold-titanium alloy variants

Early House Party Protocol suits. Deployed during the Mandarin/Aldrich Killian crisis to fight Extremis soldiers and rescue Pepper Potts. Most were destroyed in the final battle at the Roxxon oil platform.

No confirmed individual names for MK8–MK14 in MCU canon.

---

## Mark XV — "Sneaky"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Stealth operations

Low-profile suit with a muted color scheme. Designed for infiltration where the full Iron Man silhouette would be a liability.

---

## Mark XVI–XVI

**Status:** Documented
**First Appearance:** Iron Man 3 (2013) — House Party Protocol
Unnamed variants. Deployed alongside others in the oil platform battle.

---

## Mark XVII — "Heartbreaker"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** High-powered chest RT / heavy bombardment

Features an oversized arc reactor in the chest capable of firing a much more powerful unibeam. Built for situations requiring overwhelming firepower rather than agility.

---

## Mark XVIII–XIX

**Status:** Documented
**First Appearance:** Iron Man 3 (2013) — House Party Protocol
Unnamed variants. Deployed in the oil platform battle.

---

## Mark XX — "Python"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Constriction / grappling

Suit designed for physically restraining large targets. Flexible limb segments.

---

## Mark XXI — "Midas"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Aesthetic / gold coloring

Mostly gold-colored variant. Named after King Midas. Role in the House Party Protocol battle unclear.

---

## Mark XXII — "Hot Rod"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** High-speed pursuit

Red/yellow hot rod-inspired color scheme. Optimized for speed pursuit scenarios.

---

## Mark XXIII — "Shades"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)

Named variant from the House Party Protocol. Limited MCU canon detail.

---

## Mark XXIV — "Tank"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Heavy armor / slow

Maximum protection at the cost of speed and agility. Designed to absorb punishment.

---

## Mark XXV — "Striker"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Melee / close-quarters

Built for close-quarters combat. Enhanced physical attack capability.

---

## Mark XXVI — "Gamma"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Radiation protection

Shielded against radiation and exotic energy types.

---

## Mark XXVII — "Disco"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Anti-electricity

Insulated against electrical attacks. Useful against Whiplash-type electro-whip weapons or Extremis soldiers generating bio-heat.

---

## Mark XXVIII — "Jack"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)

Compact variant from the House Party Protocol.

---

## Mark XXIX — "Fiddler"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Precision targeting

Enhanced sensor array and targeting systems for precision engagement.

---

## Mark XXX — "Blue Steel"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)

Blue-tinted variant. Part of the House Party Protocol response.

---

## Mark XXXI — "Piston"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Industrial / drilling

Heavy-duty suit with reinforced arms for industrial applications and forcing through structures.

---

## Mark XXXII — "Romeo"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)

Sleek, streamlined variant. Named for aesthetic reasons.

---

## Mark XXXIII — "Silver Centurion"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Material:** Red/silver finish (pays homage to the classic comics Silver Centurion armor)

One of the more prominent House Party Protocol suits. Red and silver color scheme, a nod to the Silver Centurion armor from the comics.

---

## Mark XXXIV — "Southpaw"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Left-arm-dominant loadout

Weapons configuration biased to the left arm/hand.

---

## Mark XXXV — "Red Snapper"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Extra manipulator limbs

Features additional claw/gripper arms for search-and-rescue scenarios. Used during the House Party battle to grab and throw enemies.

---

## Mark XXXVI — "Peacemaker"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Heavy weapons loadout

Carries expanded missile/ordnance payload for suppression and area denial.

---

## Mark XXXVII — "Hammerhead"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Aquatic operations

Sealed and pressure-rated for underwater use. Hydro-optimized maneuvering thrusters.

---

## Mark XXXVIII — "Igor"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Heavy lifting / construction

Massive frame suit designed for lifting and construction applications — essentially a powered exoframe. Slow but enormously strong. Used in the House Party battle to support and prop up structures.

---

## Mark XXXIX — "Starboost" / "Gemini"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Space / vacuum operations

Sealed for space and vacuum. Improved thrust output for exoatmospheric flight. A precursor concept to the deep-space capability Tony later needed for Infinity War.

---

## Mark XL — "Shotgun"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Hypersonic speed

Built for maximum velocity above all else. Capable of hypersonic flight — used to smash through targets at extreme speed rather than engage in sustained combat.

---

## Mark XLI — "Bones"

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Specialty:** Lightweight framework

Skeleton-like open-frame design — minimal armor plating, maximum mobility and speed. Sacrifices protection for agility.

---

## Mark XLII

> *"I'm Iron Man. And I can remote-pilot my suit. And it listens."*

**Status:** Documented
**First Appearance:** Iron Man 3 (2013)
**Material:** Gold-titanium alloy (modular/segmented)

### MCU Features
- Tony's primary suit in Iron Man 3 — controlled via implanted transmitter and later a mental link through EXTREMIS-adjacent tech
- Modular: individual armor pieces fly to Tony and self-assemble — can attach to other people
- Deliberately incomplete by design — allows for rapid deployment and partial use
- Destroyed at Tony's direction by detonating the arc reactor during the Mandarin confrontation
- Rebuilt as MK43 for Avengers: Age of Ultron

### Planned Abilities

| Ability | Effect |
|---------|--------|
| Propulsion Flight | `palladium:flight_speed` +0.85 |
| Advanced Armor | `minecraft:generic.armor` +26 |
| Enhanced Strength | `minecraft:generic.attack_damage` +9 |
| Fire Resistance | Fire + lava immunity |
| Blast Shielding | Explosion immunity |
| Emergency Repair | `palladium:healing` 1 HP / 5s |

---

## Mark XLIII

**Status:** Documented
**First Appearance:** Avengers: Age of Ultron (2015)
**Material:** Gold-titanium alloy (refined MK42 chassis)

Rebuilt MK42 with improved stability and HUD. Used in the Sokovia raid to capture Wolfgang von Strucker. Badly damaged by Scarlet Witch's mind manipulation during the Vision/Ultron confrontation. Retired in favor of MK44/MK45.

---

## Mark XLIV — "Veronica" (Hulkbuster)

> *"I'm calling in Veronica."*

**Status:** Documented
**First Appearance:** Avengers: Age of Ultron (2015)
**Material:** Reinforced titanium-gold alloy (massively scaled)

### MCU Features
- Tony's anti-Hulk contingency — a massive modular frame designed to contain and subdue Bruce Banner if he lost control
- Stored in a satellite platform called "Veronica" and deployed in pieces around Tony mid-flight
- Worn over a base suit (MK43) — functions as an overlay rather than standalone armor
- Traded blow-for-blow with a mind-controlled Hulk in Johannesburg
- Partially destroyed during the Hulk fight; left arm ripped off, core frame intact

### Planned Abilities

| Ability | Effect |
|---------|--------|
| Limited Flight | `palladium:flight_speed` +0.4 (massive suit — slow) |
| Reinforced Frame | `minecraft:generic.armor` +30 |
| Max Health Boost | `minecraft:generic.max_health` +20 |
| Titanfall Strike | `minecraft:generic.attack_damage` +15 |
| Blast Shielding | Explosion immunity |
| Fire Resistance | Fire + lava immunity |
| Structural Integrity | `minecraft:generic.knockback_resistance` 1.0 |

---

## Mark XLV

**Status:** Documented
**First Appearance:** Avengers: Age of Ultron (2015)
**Material:** Gold-titanium alloy (cleaner design, white/gold trim)

Tony's primary suit for the final battle in Sokovia. More streamlined than previous suits — incorporated lessons from the damage to MK43. Destroyed during the Sokovia battle.

---

## Mark XLVI

**Status:** Documented
**First Appearance:** Captain America: Civil War (2016)
**Material:** Gold-titanium alloy

Used throughout the Avengers Civil War conflict. Fought against both Captain America and Bucky Barnes simultaneously. Features improved HUD and facial recognition. Left badly damaged after Tony was defeated by Rogers at the Siberian bunker.

---

## Mark XLVII

**Status:** Documented
**First Appearance:** Spider-Man: Homecoming (2017)

Brief appearance. Tony wears it when confronting Adrian Toomes / Vulture. No major combat role in Homecoming — primarily used to oversee Peter Parker's situation.

---

## Mark XLVIII — L (Unknown suits)

**Status:** Documented (unconfirmed)

Tony Stark built additional suits in the period between Homecoming and Infinity War while living at the Lake House with Pepper and Morgan. The exact numbering of MK48 and MK49 is not confirmed in MCU canon. These represent the gap between MK47 and the nanotech breakthrough of MK50.

---

## Mark L (50) — Nanotech

> *"All that's left is a high-tech prosthetic."*

**Status:** Documented
**First Appearance:** Avengers: Infinity War (2018)
**Material:** Nanotech (stored in arc reactor housing on Tony's chest)

### MCU Features
- Revolutionary departure from traditional suit construction — stored as liquid nanotechnology inside a housing unit on Tony's chest
- Can form any weapon, shield, or attachment on demand in real time
- Partially self-repairing — nanotech reabsorbs and redistributes to patch damage
- Used to fight Thanos directly on Titan — Tony was impaled but survived through nanite sealing
- Significantly weakened by the fight with Thanos; almost fully depleted

### Planned Abilities

| Ability | Effect |
|---------|--------|
| Nanotech Flight | `palladium:flight_speed` +1.1 |
| Nanotech Armor | `minecraft:generic.armor` +28 |
| Superior Strength | `minecraft:generic.attack_damage` +12 |
| Fall / Explosion / Fire immunity | All three damage type immunities |
| Nanite Repair | `palladium:healing` 1 HP / 3s |
| *(armor toughness)* | +20 |
| *(knockback resistance)* | Full |

---

## Mark LI–LXXXIV (51–84)

**Status:** Documented (unconfirmed)

Tony spent five years at the Lake House after the Decimation raising Morgan while the world grieved. He continued to tinker but the extent of suit development during this period is unknown. When he returned to active duty for the Time Heist in Endgame, FRIDAY referenced the MK85, implying many iterations were built between MK50 and MK85. The specific features of these suits are not shown in the MCU.

---

## Mark LXXXV (85)

> *"And I am... Iron Man."*

**Status:** Documented
**First Appearance:** Avengers: Endgame (2019)
**Material:** Nanotech (advanced — capable of housing an Infinity Gauntlet)

### MCU Features
- Tony's final suit and the most powerful armor he ever built
- Nanotech construction allows it to morph into an Infinity Gauntlet — Tony used this to redirect the Infinity Stones and snap half the universe back into existence
- The Snap using the Stones was lethal — the energy destroyed the nanotech suit and fatally irradiated Tony
- The definitive end point of the Iron Man armor lineage

### Planned Abilities

| Ability | Effect |
|---------|--------|
| Nanotech Flight | `palladium:flight_speed` +1.3 |
| MK85 Armor | `minecraft:generic.armor` +30 |
| Max Strength | `minecraft:generic.attack_damage` +14 |
| All Damage Immunities | Fall, fire, lava, explosion, magic |
| Nanite Regeneration | `palladium:healing` 1 HP / 2s |
| Max Health | `minecraft:generic.max_health` +10 |
| *(armor toughness)* | +24 |
| *(knockback resistance)* | Full |

---

*More suits in active development. See [Adding a New Suit](Adding-a-New-Suit.md) to contribute.*
