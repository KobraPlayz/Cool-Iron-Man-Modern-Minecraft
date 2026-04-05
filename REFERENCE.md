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

## Ability Types (confirmed from source — 1.20/main)

### `palladium:attribute_modifier`
Adds a Minecraft or Palladium attribute modifier while the ability is active.

| Field | Type | Notes |
|---|---|---|
| `attribute` | Resource location | Attribute ID (see tables below) |
| `amount` | double | Modifier value |
| `operation` | string | `add_value` / `add_multiplied_base` / `add_multiplied_total` — defaults to add_value if omitted |
| `title` | string | Display name in GUI (optional) |
| `list_index` | int | Sort order in GUI list (optional) |
| `hidden` | boolean | Hide from powers screen (optional) |

**Palladium flight attributes (confirmed from FlightHandler.java + official test pack):**

| Attribute ID | Range | Effect |
|---|---|---|
| `palladium:flight_speed` | 0.0 – 32.0 | **Enables flight.** Any value >0 activates directional propulsion flight. 0.7 = standard feel. |
| `palladium:levitation_speed` | 0.0 – 32.0 | Enables levitation-style flight (slower, no boost). |
| `palladium:flight_flexibility` | 0.0 – 10.0 | Direction change speed. 5 = default. Lower = more inertia. |
| `palladium:heroic_flight_type` | 0 or 1 | Set to 1 for Iron Man-style prone flight pose. Cosmetic only. |

**Vanilla attributes confirmed usable:**

| Attribute ID | Notes |
|---|---|
| `minecraft:generic.armor` | Armor points (max effective ~20) |
| `minecraft:generic.armor_toughness` | Armor toughness |
| `minecraft:generic.attack_damage` | Melee damage |
| `minecraft:generic.knockback_resistance` | 0.0–1.0; 1.0 = fully knockback immune |
| `minecraft:generic.movement_speed` | Movement speed |
| `minecraft:generic.flying_speed` | Flight speed (use with `palladium:flight_speed`) |
| `minecraft:generic.jump_strength` | Jump height |
| `minecraft:generic.max_health` | Max health |
| `minecraft:generic.gravity` | Gravity multiplier |
| `minecraft:generic.fall_damage_multiplier` | Fall damage scale |

---

### `palladium:damage_immunity`
Makes the entity immune to specified damage types.

| Field | Type | Notes |
|---|---|---|
| `damage_types` | string, tag, or list | e.g. `"minecraft:fall"`, `"#minecraft:bypasses_armor"`, or `["minecraft:fall","minecraft:fire"]` |

---

### `palladium:healing`
Heals the entity at a regular interval.

| Field | Type | Notes |
|---|---|---|
| `frequency` | int (ticks) | Ticks between heals |
| `amount` | float | Half-hearts per heal event |

---

### `palladium:command`
Runs Minecraft commands.

| Field | Type | Notes |
|---|---|---|
| `commands` | string or array | Run every tick while enabled |
| `first_tick_commands` | string or array | Run once when ability activates |
| `last_tick_commands` | string or array | Run once when ability deactivates |

---

### `palladium:energy_beam`
Fires an energy beam in the player's look direction. **⚠ Requires a beam renderer definition file — schema not yet confirmed.**

| Field | Type | Notes |
|---|---|---|
| `energy_beam` | resource location | Points to beam renderer in `assets/<ns>/palladium/energy_beams/<id>.json` |
| `damage` | float | Damage per tick to hit entities |
| `max_distance` | float | Max range in blocks (default 30) |
| `set_on_fire_ticks` | int | Fire ticks on hit entity |

---

### `palladium:slowfall`
Reduces downward velocity ~40%/tick, cancels fall damage. No extra fields.

---

### `palladium:gui_overlay`
Renders a texture overlay on the player's HUD.

| Field | Type | Notes |
|---|---|---|
| `texture` | TextureReference object | `{"type":"palladium:normal","texture":"ns:textures/..."}` |
| `texture_width` / `texture_height` | int | Texture dimensions (default 256) |
| `alignment` | string | `top_left`, `top_center`, `top_right`, `center_left`, `center`, `center_right`, `bottom_left`, `bottom_center`, `bottom_right`, `stretch` |
| `translate` | [x,y,z] | Position offset |
| `scale` | [x,y,z] | Scale |

---

## Conditions (confirmed from source — 1.20/main)

| Type | Description | Key Fields |
|---|---|---|
| `palladium:health` | Player health in range | `min_health`, `max_health` |
| `palladium:crouching` | Player is sneaking | — |
| `palladium:ability_unlocked` | Another ability is unlocked | `ability_id` |

---

## Heroes / Suits

| Hero | Power ID | Item Trigger | Notes |
|---|---|---|---|
| Iron Man Mark II | `iron_arsenal:mark2` | `minecraft:iron_chestplate` (chest) — **PLACEHOLDER** | Replace with custom item when addon item is registered |

### Mark II — Abilities Summary

| Ability Key | Type | Effect | Visible |
|---|---|---|---|
| `flight` | `attribute_modifier` | `palladium:flight_speed` +0.7 — enables propulsion flight | Yes |
| `flight_flexibility` | `attribute_modifier` | `palladium:flight_flexibility` +5 | Hidden |
| `heroic_flight_type` | `attribute_modifier` | `palladium:heroic_flight_type` +1 (Iron Man pose) | Hidden |
| `armor` | `attribute_modifier` | `minecraft:generic.armor` +20 | Yes |
| `armor_toughness` | `attribute_modifier` | `minecraft:generic.armor_toughness` +10 | Hidden |
| `knockback_resistance` | `attribute_modifier` | `minecraft:generic.knockback_resistance` +1.0 | Hidden |
| `enhanced_strength` | `attribute_modifier` | `minecraft:generic.attack_damage` +6 | Yes |
| `fall_damage_immunity` | `damage_immunity` | `minecraft:fall` immune | Yes |

**TODO — Mark II:**
- [ ] Confirm `energy_beam` renderer schema, then add repulsor + unibeam abilities
- [ ] Replace `minecraft:iron_chestplate` placeholder with `iron_arsenal:mark2_chestplate` custom item
- [ ] Provide suit texture → `assets/iron_arsenal/textures/suit/mark2.png`
- [ ] Provide GeckoLib model → `assets/iron_arsenal/geo/mark2.json`
- [ ] Add armor renderer → `assets/iron_arsenal/palladium/armor_renderers/mark2_chestplate.json`

---

## Notes

- **Addon packs** load once at game start — custom items/blocks need a full restart to register.
- **Powers & abilities** are data pack content — use `/reload` after changes.
- Full ability/condition schemas are in `mods/documentation/palladium/abilities.html` and `conditions.html` inside the mod jar.
- Texture and model files must be supplied manually — no placeholders generated without flagging.
- `palladium:flight` ability type **does not exist in 1.20/main**. Use `palladium:attribute_modifier` with `palladium:flight_speed` instead.
- `palladium:energy_beam` (1.20) → renamed to `palladium:beam` in 1.21.8+. Use `energy_beam` for this pack.
