# Modularis

A compatibility datapack for Truly Modular in Minecraft 1.21.

**Materials created so far: 130**

## Currently supported mods

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
- Mowzie's Mobs
- Mystical Agriculture
- MythicUpgrades
- Oreganized
- Primal
- Quark
- Twilight Forest

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
