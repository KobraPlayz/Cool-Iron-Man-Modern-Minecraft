# Adding a New Suit

This guide walks through adding a new Iron Man suit from scratch. You'll need two data files and (eventually) asset files for the model and texture.

---

## Step 1 — Create the Power Definition

Create `data/iron_arsenal/palladium/powers/<suit_id>.json`:

```json
{
  "name": "Iron Man Mark III",
  "background": "minecraft:textures/block/iron_block.png",
  "icon": "minecraft:iron_chestplate",
  "abilities": {

    "flight": {
      "type": "palladium:attribute_modifier",
      "title": "Propulsion Flight",
      "attribute": "palladium:flight_speed",
      "list_index": 0,
      "amount": 0.7
    },

    "flight_flexibility": {
      "type": "palladium:attribute_modifier",
      "attribute": "palladium:flight_flexibility",
      "hidden": true,
      "amount": 5
    },

    "heroic_flight_type": {
      "type": "palladium:attribute_modifier",
      "attribute": "palladium:heroic_flight_type",
      "hidden": true,
      "amount": 1
    },

    "armor": {
      "type": "palladium:attribute_modifier",
      "title": "Armor",
      "attribute": "minecraft:generic.armor",
      "list_index": 1,
      "amount": 20
    }

  }
}
```

> Ability keys must be **unique within the power**. Use descriptive snake_case names.

See [Ability & Condition Reference](Ability-Reference.md) for all confirmed ability types and fields.

---

## Step 2 — Assign the Power to an Item

Create `data/iron_arsenal/palladium/item_powers/<suit_id>.json`:

```json
{
  "slot": "chest",
  "item": "iron_arsenal:<suit_item_id>",
  "power": "iron_arsenal:<suit_id>"
}
```

Valid slots: `head`, `chest`, `legs`, `feet`, `mainhand`, `offhand`

> During development, you can use a vanilla item (e.g. `minecraft:iron_chestplate`) as a placeholder and swap it out later.

---

## Step 3 — Test In-Game

1. Drop both files into the appropriate folders.
2. Run `/reload` in-game.
3. Equip the trigger item.
4. Verify powers are active via the Palladium powers screen.

---

## Step 4 — Add Suit Assets *(when ready)*

Once you have the model and texture files:

| File | Location |
|---|---|
| GeckoLib model | `assets/iron_arsenal/geo/<suit_id>.json` |
| Suit texture | `assets/iron_arsenal/textures/suit/<suit_id>.png` |
| Armor renderer | `assets/iron_arsenal/palladium/armor_renderers/<suit_item_id>.json` |

Armor renderer example:
```json
{
  "textures": "iron_arsenal:textures/suit/<suit_id>.png",
  "model_layers": "palladium:humanoid#suit",
  "hide_second_layer": true
}
```

Assets reload with **F3+T**. No restart needed.

---

## Step 5 — Register a Custom Item *(optional)*

If the suit needs its own item (rather than overriding a vanilla item), create `addon/iron_arsenal/items/<item_id>.json`.

> Custom items are registered once at game start — a full restart is required after adding this file.

---

## Checklist

- [ ] `data/iron_arsenal/palladium/powers/<suit_id>.json`
- [ ] `data/iron_arsenal/palladium/item_powers/<suit_id>.json`
- [ ] `assets/iron_arsenal/textures/suit/<suit_id>.png` *(when available)*
- [ ] `assets/iron_arsenal/geo/<suit_id>.json` *(when available)*
- [ ] `assets/iron_arsenal/palladium/armor_renderers/<suit_item_id>.json` *(when available)*
- [ ] `addon/iron_arsenal/items/<item_id>.json` *(if custom item needed)*
- [ ] Entry added to [Suits & Abilities](Suits.md)
