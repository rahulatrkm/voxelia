# 🧊 Voxelia

**A 3D voxel sandbox you can build anything in — right in your browser.**
No download, no account. Explore procedurally generated worlds, mine and place
blocks, and build whatever you imagine.

👉 **Play:** https://rahulatrkm.github.io/voxelia/

![Voxelia](https://rahulatrkm.github.io/voxelia/) <!-- live -->

## Features

- **🌍 Infinite streaming worlds** — chunks load and unload around you as you walk,
  so the world never ends
- **🧱 Textured blocks** — every block has a procedurally-generated texture on a
  shared atlas (grass fringe, wood grain, brick mortar, ore flecks…)
- **⛏️ Mine & build** — DDA voxel raycasting for pixel-precise targeting; blocks
  drop into your inventory when mined
- **❤️ Survival mode** — health & hunger, fall damage, drowning, eating to heal,
  death & respawn — or switch to **Creative** with flight and unlimited blocks
- **🐷 Mobs** — pigs and sheep roam by day; zombies spawn in the dark, chase you
  and deal damage (fight back by hitting them)
- **🎒 Inventory & crafting** — a grid inventory plus recipes (planks, glass,
  brick)
- **🔊 Procedural sound** — footsteps, block break/place, hurt & eat SFX via
  WebAudio (no audio files)
- **📱 Mobile controls** — on-screen joystick, look-drag and action buttons on
  touch devices
- **🌗 Day/night cycle** with a moving sun, sky-colour blending and fog
- **💾 Persistent world** — your world, inventory and stats save locally and
  reload next time

## Controls

| Action | Key |
| --- | --- |
| Move | `W` `A` `S` `D` |
| Look | Mouse (click to lock) |
| Jump | `Space` |
| Sprint | `Shift` |
| Fly toggle | `F` |
| Mine block | Left click |
| Place block | Right click |
| Select block | `1`–`8` |

## Voxelia Pro (the premium plan)

The core game is free. **Voxelia Pro ($4/mo)** is the roadmap for a paid tier:

- **Bigger / streaming worlds** (beyond the current render radius)
- **More blocks & materials**, plus lights and slabs
- **Cloud saves** across devices
- **Multiplayer** shared worlds
- **World export/share links**

> This repository is the free, open core. Pro features are the planned
> commercial layer on top of the same engine.

## Tech

- **Three.js** (WebGL) rendering
- **Chunked meshing** with face culling — only visible block faces become
  geometry, so large worlds stay fast
- **Custom voxel raycaster** (DDA) for mining/placing
- **Swept-AABB collision** against the voxel grid
- One self-contained `index.html`, no build step

## Run locally

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## License

MIT (engine & original code). Have fun and build things.
