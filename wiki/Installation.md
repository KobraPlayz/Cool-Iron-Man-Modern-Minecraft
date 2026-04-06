# Installation & Setup

## Requirements

| Mod | Version | Where to get it |
|---|---|---|
| Minecraft | 1.20.1 | [minecraft.net](https://minecraft.net) |
| Palladium | >= 4.5.0 | [Modrinth](https://modrinth.com/mod/threetag-palladium) |
| Forge or Fabric | 1.20.1-compatible | [files.minecraftforge.net](https://files.minecraftforge.net) / [fabricmc.net](https://fabricmc.net) |

---

## Installing the Pack

1. Locate your Minecraft directory:
   - **Windows:** `%appdata%\.minecraft\`
   - **macOS:** `~/Library/Application Support/minecraft/`
   - **Linux:** `~/.minecraft/`

2. Create the `addonpacks` folder if it doesn't exist:
   ```
   .minecraft/addonpacks/
   ```

3. Place the `iron_arsenal` folder (or zip file) inside `addonpacks/`:
   ```
   .minecraft/addonpacks/iron_arsenal/
   ```

4. Launch Minecraft 1.20.1. The pack loads automatically — no further configuration needed.

---

## Verifying It Loaded

In-game, run:
```
/palladium addonpacks list
```
You should see `iron_arsenal` listed.

If powers aren't working, run `/reload` and re-equip the trigger item.

---

## Troubleshooting

| Issue | Fix |
|---|---|
| Pack not appearing in list | Check folder name matches exactly: `iron_arsenal` |
| Powers not activating | Run `/reload`, then remove and re-equip the item |
| Custom items missing | Custom items require a full game restart to register |
| Version mismatch error | Ensure Palladium >= 4.5.0 is installed |
