# Shard Trim Expansion

**Minecraft Bedrock Edition Addon**  
**Target Version:** 1.26.51 (and compatible 1.26.x)  
**Platform:** iPhone / Bedrock (also works on other Bedrock platforms)

## What This Addon Does

Adds **10 new armor trim materials** that can be used at a Smithing Table with any existing vanilla armor trim pattern:

| Material              | Identifier                  | Visual Identity              |
|-----------------------|-----------------------------|------------------------------|
| Echo Shard            | `minecraft:echo_shard`      | Deep echo purple / dark violet |
| Nether Brick          | `minecraft:nether_brick`    | Dark Nether red / maroon     |
| Prismarine Shard      | `minecraft:prismarine_shard`| Teal                         |
| Prismarine Crystals   | `minecraft:prismarine_crystals` | Bright aqua              |
| Brick                 | `minecraft:brick`           | Brick red                    |
| Blackstone            | `minecraft:blackstone`      | Very dark gray / black       |
| Chorus Fruit          | `minecraft:chorus_fruit`    | End purple                   |
| Slimeball             | `minecraft:slime_ball`      | Slime green                  |
| Magma Cream           | `minecraft:magma_cream`     | Magma orange                 |
| Bone                  | `minecraft:bone`            | Ivory / bone white           |

All **vanilla trim materials** (Amethyst, Copper, Diamond, Emerald, Gold, Iron, Lapis, Netherite, Quartz, Redstone, Resin) continue to work exactly as before. No vanilla materials, patterns, armor, or recipes are replaced or removed.

## How It Works

1. **Behavior Pack** extends the vanilla item tag `minecraft:trim_materials` to include the 10 new items while keeping every original entry.
2. The existing vanilla smithing trim recipe already accepts anything in that tag, so the new materials appear in the Smithing Table UI and can be applied with any trim template.
3. **Resource Pack** supplies matching color palette textures under `textures/trims/color_palettes/` so the game can apply the intended hues when the trim is rendered.

No Script API, no experimental toggles, no custom armor items, no new trim patterns, and no world-generation changes.

## Installation (iPhone / Bedrock)

1. Download the release `.mcaddon` (or the two `.mcpack` files) from this repository / Releases.
2. Open the file with Minecraft (Files app → Share → Minecraft, or tap the file).
3. Minecraft will import both the Behavior Pack and Resource Pack.
4. Create a new world **or** edit an existing world:
   - Go to **Behavior Packs** → activate **Shard Trim Expansion BP**.
   - Go to **Resource Packs** → activate **Shard Trim Expansion RP**.
5. (Optional but recommended) Set the Resource Pack priority above other texture packs that might override trims.
6. Enter the world. No experiments need to be enabled.

## Known Limitations

- **Custom palette support in Bedrock is limited** compared to Java. The engine primarily recognizes the built-in palette names. Supplying new palette files is the closest supported method; results can vary by device/version.
- Inventory icons of trimmed armor sometimes fail to show the custom color (a known Bedrock rendering quirk). The armor **worn on the player or armor stand** usually displays the correct color.
- Blackstone is a block item; it works as a material but may feel slightly less “item-like” than the others.
- If another addon also modifies the `minecraft:trim_materials` tag, the last-loaded pack wins. This pack intentionally includes the full vanilla list to minimize breakage.

## Compatibility Notes

- Designed for Bedrock 1.26.51.
- Should work on 1.26.x and many 1.21.x versions that already have the trim system.
- Does **not** require any experimental gameplay features.
- Safe to use on Realms and servers that allow the packs (both BP + RP must be present).

## File Structure

```
ShardTrimExpansion/
├── behavior_packs/
│   └── ShardTrimExpansion_BP/
│       ├── manifest.json
│       ├── tags/items/trim_materials.json
│       └── texts/en_US.lang
├── resource_packs/
│   └── ShardTrimExpansion_RP/
│       ├── manifest.json
│       ├── textures/trims/color_palettes/
│       │   ├── <material>.png
│       │   └── <material>.texture_set.json
│       └── texts/en_US.lang
├── README.md
└── (packaged .mcaddon available in Releases)
```

## Test Checklist

1. Import the packs successfully.
2. Activate both BP and RP on a world.
3. Open a Smithing Table.
4. Place any armor + any vanilla trim template.
5. Confirm all 10 new materials appear as valid additions alongside the original ones.
6. Apply each new material and check the worn armor color.
7. Confirm vanilla materials still produce their original colors.
8. Confirm untrimmed armor is unchanged.
9. Check content log for missing-texture / invalid-tag errors (should be none).

## Credits

Created following Packwright Smith standards for a clean, vanilla-compatible Bedrock addon.
