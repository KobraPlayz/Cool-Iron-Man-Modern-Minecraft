# Iron Arsenal — Palladium Addon Pack Reference

**Namespace:** `iron_arsenal`
**Minecraft Version:** 1.20.1
**Palladium Version:** >=4.0.0.0
**Pack Format:** 8

---

## Folder Structure

```
iron_arsenal/
├── pack.mcmeta
├── REFERENCE.md
├── addon/
│   └── iron_arsenal/
│       └── items/                          ← Custom item definitions (registered once at launch)
├── assets/
│   └── iron_arsenal/
│       ├── geo/                            ← GeckoLib model files (.json)
│       ├── lang/                           ← Language files (e.g. en_us.json)
│       ├── palladium/
│       │   └── armor_renderers/            ← Armor renderer definitions
│       └── textures/
│           ├── item/                       ← Item textures
│           └── suit/                       ← Suit/armor textures
└── data/
    └── iron_arsenal/
        └── palladium/
            ├── abilities/                  ← Standalone ability files (optional split-out)
            ├── item_powers/                ← Links items/slots to powers
            └── powers/                     ← Power definitions
```

---

## pack.mcmeta Schema (confirmed)

```json
{
  "pack": {
    "id": "iron_arsenal",
    "description": "...",
    "pack_format": 8,
    "version": "1.0.0.0"
  },
  "dependencies": {
    "common": {
      "minecraft": ">=1.20.1",
      "palladium": ">=4.0.0.0"
    }
  }
}
```

---

## Power Definition Schema (confirmed)

**Path:** `data/iron_arsenal/palladium/powers/<power_id>.json`

```json
{
  "name": "Power Display Name",
  "background": "iron_arsenal:textures/...",
  "icon": "iron_arsenal:textures/...",
  "gui_display_type": "list",
  "abilities": {
    "<ability_key>": {
      "type": "palladium:<ability_type>",
      "conditions": {
        "unlocking": [],
        "enabling": []
      }
    }
  }
}
```

**Confirmed fields:**
| Field | Type | Notes |
|---|---|---|
| `name` | string or text component | Plain string or `{ "translate": "key" }` |
| `background` | resource location | Path to a texture for the abilities screen |
| `icon` | resource location | Item ID or texture path |
| `gui_display_type` | string | `"list"` or `"tree"` |
| `abilities` | object | Map of unique ability keys to ability objects |

---

## Item Powers Schema (confirmed)

**Path:** `data/iron_arsenal/palladium/item_powers/<filename>.json`

```json
{
  "slot": "chest",
  "item": "iron_arsenal:<item_id>",
  "power": "iron_arsenal:<power_id>"
}
```

**Confirmed slots:** `mainhand`, `offhand`, `feet`, `legs`, `chest`, `head`

**Multiple powers per item:**
```json
{ "slot": "chest", "item": "iron_arsenal:mk1_chestplate", "power": ["iron_arsenal:power_a", "iron_arsenal:power_b"] }
```

---

## Armor Renderer Schema (confirmed)

**Path:** `assets/iron_arsenal/palladium/armor_renderers/<item_id>.json`

```json
{
  "textures": "iron_arsenal:textures/suit/<suit_name>.png",
  "model_layers": "palladium:humanoid#suit",
  "hide_second_layer": true
}
```

---

## Ability Types (confirmed working)

| Type | Description | Key Fields |
|---|---|---|
| `palladium:command` | Runs MC commands | `commands: [...]` |
| `palladium:healing` | Regenerates health | `frequency`, `amount` |

> Add more here as we confirm them in-game.

---

## Conditions (confirmed working)

| Type | Description | Key Fields |
|---|---|---|
| `palladium:health` | Triggers at health range | `min_health`, `max_health` |
| `palladium:crouching` | Player is crouching | — |
| `palladium:ability_unlocked` | Another ability is unlocked | `ability_id` |

> Add more here as we confirm them in-game.

---

## Heroes / Suits

| Hero | Power ID | Item ID | Status |
|---|---|---|---|
| *(none yet)* | — | — | — |

---

## Notes

- **Addon packs** load once at game start — custom items/blocks need a full restart to register.
- **Powers & abilities** are data pack content — use `/reload` after changes.
- Full ability/condition schemas are in `mods/documentation/palladium/abilities.html` and `conditions.html` inside the mod jar.
- Texture and model files must be supplied manually — no placeholders generated without flagging.
