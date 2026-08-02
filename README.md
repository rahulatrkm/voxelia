# Voxelia

A 3D voxel sandbox that runs in a browser tab. Infinite generated terrain, ore
tiers that gate what you can mine, a real crafting grid, furnaces, chests,
flowing water and lava, farming, breeding, and mobs that hunt you at night.

**Play:** https://rahulatrkm.github.io/voxelia/

No download, no account, no build step — one `index.html` and Three.js from a CDN.

## What is in it

**World**
- Four biomes (plains, forest, desert, snowy peaks) chosen by slow temperature
  and moisture fields, so walking a few hundred blocks actually takes you
  somewhere different
- Cave systems carved by two independent 3D noise fields, which is what makes
  them connected tunnels rather than disconnected blobs
- An ore depth ladder: coal is shallow and common, diamond is deep and rare
  (roughly one diamond per thirty-five coal)
- Lava pools in deep caves, clay under shallow water, ice on frozen lakes
- Villages with levelled ground, houses, glass windows, beds, chests, furnaces
  and a lit well, generated across chunk boundaries

**Playing**
- Hold to mine, with a crack overlay that tracks progress. Break time depends on
  the block, the tool, and the tool's tier
- Four tool tiers (wood, stone, iron, diamond) across pickaxe, axe, shovel,
  sword and hoe. Durability, mining speed, and harvest gating — a wooden pickaxe
  will not give you iron, and only diamond takes obsidian
- A 3×3 crafting grid at a table, 2×2 in your pack. Shaped and shapeless
  recipes, mirrored patterns, and a recipe list that shows what you can make now
- Furnaces that burn one fuel at a time and only while something is smelting
- Chests with 27 slots. Break one and its contents spill rather than vanish
- Armour in three materials and four pieces, with real damage reduction
- Bows and arrows; skeletons shoot back
- Flowing water and lava that fall, spread, thin out with distance, drain when
  you remove the source, and turn each other into cobblestone and obsidian
- Farming: till soil with a hoe, plant seeds, irrigate, harvest wheat, bake bread
- Breed cows, pigs, sheep and chickens; milk a cow with a bucket
- Beds that skip the night and set your spawn point
- Sneak so you cannot walk off a ledge, sprint at the cost of hunger, climb
  ladders, slide on ice
- Health, hunger, saturation, breath, fall and lava damage, experience levels
- Die and your pack spills where you fell, so death is a recovery run

**Modes**
- **Survival** — you start with a wooden pickaxe and axe and have to earn the rest
- **Creative** — fly, take no damage, and pick any block from a tabbed palette
- **Hardcore** — survival, but the world is deleted when you die

## Controls

| Action | Key |
| --- | --- |
| Move | `W` `A` `S` `D` |
| Look | Mouse (click to lock) |
| Jump | `Space` |
| Sprint | `Ctrl` |
| Sneak | `Shift` |
| Fly (creative) | `F` |
| Mine / attack | Hold left click |
| Place / use | Right click |
| Inventory | `E` |
| Drop held item | `Q` |
| Select hotbar | `1`–`9`, or scroll |
| Mute | `M` |
| Pause | `Esc` |

On touch devices you get a joystick, look-drag, and buttons for jump, mine,
place, fly and inventory.

## What is deliberately not in it

Being straight about the gap rather than implying parity: there is no redstone,
no Nether or End, no enchanting or potions, no multiplayer, and no boats or
minecarts. Each of those is a larger project than everything above.

## How it works

- **Chunked greedy-ish meshing** with face culling and per-vertex ambient
  occlusion. Only faces that border something see-through become geometry
- **Three draw passes** per chunk — opaque, alpha-tested cutouts (plants,
  torches, glass), and transparent (water, lava) — so sorting stays correct
- **Custom DDA voxel raycaster** for targeting
- **Fluid cellular automaton** over a sparse level map; only non-source cells are
  stored, so anything the terrain generated is permanent by construction
- **Saves record only modified chunks.** Generation is deterministic from the
  seed, so everything you never touched is rebuilt rather than stored
- Procedural textures and item icons drawn to canvas at load — no image assets
- Procedural WebAudio sound effects — no audio files

## Tests

```bash
node voxelia.test.mjs
```

152 assertions. The suite executes the real game module against a stubbed DOM
and a stubbed Three.js, then drives the actual functions: crafting matches,
furnace smelting, fluid spread and drainage, tool gating, save round-trips,
chunk meshing, and the inventory screens.

This matters because an earlier version of this suite only tested world
generation, and a completely unplayable creative mode shipped green.

## Run locally

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## License

MIT.
