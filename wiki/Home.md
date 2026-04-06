# Iron Arsenal — Wiki

Welcome to the Iron Arsenal wiki. This addon pack adds MCU-accurate Iron Man suits and abilities to Minecraft 1.20.1 using the [Palladium](https://modrinth.com/mod/threetag-palladium) mod.

---

## Pages

- [Installation & Setup](Installation.md) — how to install the pack and verify it's working
- [Suits & Abilities](Suits.md) — every suit, its abilities, and how to obtain it
- [Adding a New Suit](Adding-a-New-Suit.md) — step-by-step guide for contributors
- [Ability & Condition Reference](Ability-Reference.md) — full schema reference for all confirmed ability and condition types

---

## Quick Start

1. Place the pack in `.minecraft/addonpacks/`
2. Launch the game
3. Wear the trigger item for any suit (see [Suits & Abilities](Suits.md))
4. You now have the suit's powers

---

## How It Works

Iron Arsenal is built on top of Palladium's data-driven power system. Every suit is defined by two JSON files:

| File | Location | Purpose |
|---|---|---|
| Power definition | `data/iron_arsenal/palladium/powers/<suit>.json` | Defines all abilities |
| Item power | `data/iron_arsenal/palladium/item_powers/<suit>.json` | Links a worn item to the power |

Powers reload with `/reload`. Custom item registrations require a full game restart.
