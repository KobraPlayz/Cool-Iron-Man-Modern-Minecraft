# Iron Arsenal

A Palladium addon pack for Minecraft 1.20.1 — bringing MCU-accurate Iron Man suits, abilities, and technology to your world.

---

## Requirements

| Dependency | Version |
|---|---|
| Minecraft | 1.20.1 |
| Palladium | >= 4.5.0 |
| Forge **or** Fabric | Compatible with either |

> GeckoLib is required if you use the suit model rendering features.

---

## Installation

1. Download or clone this repository.
2. Place the `iron_arsenal` folder (or zipped version) into your `.minecraft/addonpacks/` directory.
3. Launch Minecraft 1.20.1 — the pack loads automatically on startup.

> **Note:** Addon packs load once at game start. Any changes to custom item/block registrations require a full restart. Power and ability changes can be applied with `/reload`.

---

## Current Suits

| Suit | Power ID | Trigger Item | Status |
|---|---|---|---|
| Mark II | `iron_arsenal:mark2` | Iron Chestplate *(placeholder)* | In Progress |

---

## Features

- MCU-accurate suit abilities sourced from the Marvel Cinematic Universe wiki
- Heroic Iron Man flight pose via Palladium's `palladium:heroic_flight_type`
- Data-driven — every ability is a JSON file, no code required to add suits
- Designed for expansion — new suits can be added by dropping in new power + item_powers files

---

## Wiki

Full documentation lives in the [`wiki/`](wiki/) folder:

- [Home](wiki/Home.md)
- [Installation & Setup](wiki/Installation.md)
- [Suits & Abilities](wiki/Suits.md)
- [Adding a New Suit](wiki/Adding-a-New-Suit.md)
- [Ability & Condition Reference](wiki/Ability-Reference.md)

---

## Project Structure

```
iron_arsenal/
├── pack.mcmeta                              ← Pack metadata & dependencies
├── README.md
├── REFERENCE.md                             ← Developer schema reference (kept up to date)
├── wiki/                                    ← Documentation
├── addon/iron_arsenal/items/                ← Custom item registrations
├── assets/iron_arsenal/
│   ├── geo/                                 ← GeckoLib model files
│   ├── lang/                                ← Language files
│   ├── palladium/armor_renderers/           ← Suit render definitions
│   └── textures/suit/                       ← Suit textures
└── data/iron_arsenal/palladium/
    ├── powers/                              ← Power definitions
    └── item_powers/                         ← Item-to-power assignments
```

---

## Development

See [REFERENCE.md](REFERENCE.md) for confirmed ability type schemas, attribute IDs, and the full suit ability table.

See [wiki/Adding-a-New-Suit.md](wiki/Adding-a-New-Suit.md) for a step-by-step guide to adding new suits.

---

## License

All rights to Iron Man and related characters belong to Marvel / Disney. This is a fan project with no commercial intent.
