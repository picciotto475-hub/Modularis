# Modularis

A compatibility datapack for Truly Modular in Minecraft 1.21.

**Materials created so far: 227**

---

## Currently supported mods

- Ad Astra
- Aether
- Aether Treasure Reforging
- Aethersteel
- Aquaculture 2
- Archaion
- Born in Chaos
- Caverns and Chasms
- Deep Aether
- Deeper and Darker
- Enigmatic Legacy Plus
- Ender's Cataclysm
- Fangs 'n' Claws
- Luminous Nether
- Mowzie's Mobs
- Myths and Legends
- Mystical Agriculture
- MythicUpgrades
- Oreganized
- Orevolution
- Primal
- Quark
- The Beyond
- Tinkers' Construct
- Twilight Forest

---

## How to install

**Requirements:** Minecraft **1.21.1**, **Truly Modular**, and the mods whose materials you want
(see the list above). Materials from mods you don't have are simply skipped.

Modularis is both a **datapack** and a **resource pack** in one zip, so the same zip has to be
loaded in both ways:

- as a **datapack** → materials, stats, abilities and recipes (`data/`)
- as a **resource pack** → textures and names (`assets/`)

If only the datapack is loaded, the materials work but have missing textures and raw names like
`miapi.material.modularis.xxx`. If only the resource pack is loaded, nothing happens.

**Don't split the pack.** Don't take the `assets` folder out to make a separate resource pack, and
don't remove it from the datapack. Always use the whole pack, as it is, in both places: Minecraft
automatically ignores `assets` when it's loaded as a datapack, and ignores `data` when it's loaded
as a resource pack.

### Before you start: check the zip (important if you downloaded it from GitHub)

When you open the zip, the **first thing you see** must be the `README.md`, the `data` folder and
the `assets` folder (plus `pack.mcmeta`).

GitHub's *Download ZIP* adds an extra parent folder (for example `Modularis-main/`), with the real
pack inside it. Minecraft can't read it like that. Unzip it, open that extra folder and zip
**its contents** again, or just use that inner folder directly: it works either way.

### Method 1 (easiest): with a datapack loader

A datapack loader is a mod that loads datapacks for **every world** automatically, so you install
it once and never think about it again. [Paxi](https://modrinth.com/mod/paxi) is one of them, but
any datapack loader you like works.

1. Install the datapack loader in your instance, like any other mod.
2. Open your instance folder (in your launcher: *Open Folder* on the instance).
3. Put the zip in the instance's `datapacks` folder, for example
   `...\Instances\Truly modular materials\datapacks\`.
   **If the `datapacks` folder is not there, start Minecraft at least once with the datapack
   loader installed.**
4. Put **a copy of the same zip** in the instance's `resourcepacks` folder.
5. Start the game → *Options* → *Resource Packs*, move **Modularis** to the right column → *Done*.

### Method 2: manual, without a datapack loader

(Never tried this one, but it should work.)

Same as above, but the datapack part has to be done **for every world**:

1. Put the zip in the instance's `resourcepacks` folder and enable it in *Options* → *Resource Packs*.
2. Put a copy of the zip in the world's datapack folder:
   - **existing world:** `saves\<world name>\datapacks\`
   - **new world:** *Create New World* → *More* → *Data Packs*, drag the zip in and move it to the
     right column.

### After installing

The game may say the resource pack was *made for a newer version*. That's expected (the same file
is also the datapack): confirm and it works normally.

**Check:** in the Truly Modular workbench, materials from supported mods should show their proper
name and texture. If you see `miapi.material.modularis.xxx` or missing textures, the resource pack
isn't enabled.

---

## Maybe you don't like how i did things and want plain materials only, with no special effects?

Every material in this pack is made of a few separate pieces, split across different folders under
`data/modularis/miapi/`:

`materials/` is the material itself: hardness, durability, tier, mining level and all the other
base stats. This is the only folder that actually defines "the material" as a thing you can
select in the crafting table.

`material_extensions/` is where every special ability lives, on-hit effects, potion effects,
attribute bonuses (chance to inflict Wither, bonus damage vs a mob type, lifesteal and so on).
It's all layered on top of the base material and doesn't touch the raw stats, it just adds bonus
effects and abilities.

`modular_converter/` lets real, already crafted items from the source mods (like a real Etherium
Sword you found or crafted normally) be recognized and used as if they were built in the Truly
Modular crafting table.

`recipe/` has the smithing table upgrade recipes, for materials meant to upgrade an existing item
into a stronger one instead of being crafted from scratch.

So if you just want the plain stat based materials with none of the bonus abilities or potion
effects, you can safely delete the `material_extensions/` folder and keep everything else. The
materials will still work normally in the crafting table, just without any of the extra on hit
behavior.

And if you want the absolute minimum, just the materials themselves with no bonus abilities, no
automatic recognition of real mod items and no upgrade recipes, keep only the `materials/` folder
and delete `material_extensions/`, `modular_converter/` and `recipe/` entirely. Nothing else in
the pack depends on those three folders so removing them is always safe.
