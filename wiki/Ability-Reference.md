# Ability & Condition Reference

All ability types confirmed for **Palladium 4.5.x / Minecraft 1.20.1**.

> This page mirrors and summarises [REFERENCE.md](../REFERENCE.md) in a more readable format. REFERENCE.md is the authoritative source — update it first when confirming new schemas.

---

## Universal Fields

Every ability object supports these fields regardless of type:

| Field | Type | Default | Notes |
|---|---|---|---|
| `type` | string | — | **Required.** The ability type ID. |
| `title` | string | null | Display name shown in the powers GUI. |
| `list_index` | int | -1 | Sort order in the GUI list. |
| `hidden` | boolean | false | Hide from the powers screen entirely. |

---

## Ability Types

### `palladium:attribute_modifier`

Applies an attribute modifier while the ability is active. Used for flight, armor, speed, strength, etc.

```json
{
  "type": "palladium:attribute_modifier",
  "attribute": "palladium:flight_speed",
  "amount": 0.7,
  "title": "Flight"
}
```

| Field | Required | Notes |
|---|---|---|
| `attribute` | Yes | Attribute resource location (see tables below) |
| `amount` | Yes | Modifier value |
| `operation` | No | `add_value` / `add_multiplied_base` / `add_multiplied_total`. Defaults to `add_value`. |

**Palladium flight attributes:**

| Attribute | Effect |
|---|---|
| `palladium:flight_speed` | Any value > 0 enables directional propulsion flight. 0.7 = standard. |
| `palladium:levitation_speed` | Enables slower levitation-style flight. |
| `palladium:flight_flexibility` | Direction change speed. 5 = default feel. Lower = more inertia. |
| `palladium:heroic_flight_type` | Set to 1 for Iron Man prone flight pose. Cosmetic only. |

**Vanilla attributes:**

| Attribute | Notes |
|---|---|
| `minecraft:generic.armor` | Armor points. Max effective ~20. |
| `minecraft:generic.armor_toughness` | Armor toughness. |
| `minecraft:generic.attack_damage` | Melee damage. |
| `minecraft:generic.knockback_resistance` | 0.0–1.0. 1.0 = fully immune. |
| `minecraft:generic.movement_speed` | Walking/running speed. |
| `minecraft:generic.flying_speed` | Speed while flying. |
| `minecraft:generic.jump_strength` | Jump height. |
| `minecraft:generic.max_health` | Max health points. |
| `minecraft:generic.gravity` | Gravity multiplier. |
| `minecraft:generic.fall_damage_multiplier` | Fall damage scale. |

---

### `palladium:damage_immunity`

Makes the player immune to specific damage types.

```json
{
  "type": "palladium:damage_immunity",
  "damage_types": "minecraft:fall"
}
```

| Field | Required | Notes |
|---|---|---|
| `damage_types` | Yes | Single ID, tag (`#minecraft:...`), or array |

Common damage type IDs: `minecraft:fall`, `minecraft:fire`, `minecraft:lava`, `minecraft:drown`, `minecraft:explosion`, `minecraft:magic`

---

### `palladium:healing`

Heals the player at a regular interval.

```json
{
  "type": "palladium:healing",
  "frequency": 20,
  "amount": 1
}
```

| Field | Required | Notes |
|---|---|---|
| `frequency` | Yes | Ticks between heals (20 ticks = 1 second) |
| `amount` | Yes | Half-hearts healed per event |

---

### `palladium:energy_beam`

Fires an energy beam in the player's look direction. **Requires a beam renderer definition file.**

```json
{
  "type": "palladium:energy_beam",
  "energy_beam": "iron_arsenal:repulsor",
  "damage": 4.0,
  "max_distance": 30.0
}
```

| Field | Required | Notes |
|---|---|---|
| `energy_beam` | Yes | ResourceLocation pointing to beam renderer in `assets/<ns>/palladium/energy_beams/<id>.json` |
| `damage` | No | Damage per tick to hit entities. Default 0. |
| `max_distance` | No | Range in blocks. Default 30. |
| `set_on_fire_ticks` | No | Fire ticks applied on hit. Default 0. |

> ⚠ Beam renderer schema not yet confirmed. Do not implement until verified.

---

### `palladium:slowfall`

Reduces downward velocity ~40% per tick and cancels fall damage. No extra fields.

```json
{
  "type": "palladium:slowfall"
}
```

---

### `palladium:command`

Runs Minecraft commands.

```json
{
  "type": "palladium:command",
  "first_tick_commands": ["/say Suit activated"],
  "last_tick_commands": ["/say Suit removed"]
}
```

| Field | Notes |
|---|---|
| `commands` | Run every tick while active |
| `first_tick_commands` | Run once on activation |
| `last_tick_commands` | Run once on deactivation |

---

### `palladium:gui_overlay`

Renders a texture overlay on the HUD.

```json
{
  "type": "palladium:gui_overlay",
  "texture": { "type": "palladium:normal", "texture": "iron_arsenal:textures/hud/mark2.png" },
  "texture_width": 256,
  "texture_height": 256,
  "alignment": "stretch"
}
```

| Field | Required | Notes |
|---|---|---|
| `texture` | Yes | TextureReference object |
| `alignment` | Yes | `top_left`, `top_center`, `top_right`, `center_left`, `center`, `center_right`, `bottom_left`, `bottom_center`, `bottom_right`, `stretch` |
| `texture_width` / `texture_height` | No | Default 256 |
| `translate` | No | `[x, y, z]` position offset |
| `scale` | No | `[x, y, z]` scale |

---

## Conditions

Conditions go inside `"conditions": { "unlocking": [...], "enabling": [...] }` on an ability.

- **`unlocking`** — conditions that must be met to have the ability available at all.
- **`enabling`** — conditions that must be met for the ability to be active.

| Type | Description | Fields |
|---|---|---|
| `palladium:health` | Player health in range | `min_health`, `max_health` |
| `palladium:crouching` | Player is sneaking | — |
| `palladium:ability_unlocked` | Another ability in the same power is unlocked | `ability_id` |

### Example — ability that only activates while crouching

```json
"repulsor_boost": {
  "type": "palladium:attribute_modifier",
  "attribute": "minecraft:generic.movement_speed",
  "amount": 0.5,
  "conditions": {
    "enabling": [
      { "type": "palladium:crouching" }
    ]
  }
}
```
