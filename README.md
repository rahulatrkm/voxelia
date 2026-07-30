# 🧊 Voxelia

**A 3D voxel sandbox you can build anything in — right in your browser.**
No download, no account. Explore procedurally generated worlds, mine and place
blocks, and build whatever you imagine.

👉 **Play:** https://rahulatrkm.github.io/voxelia/

![Voxelia](https://rahulatrkm.github.io/voxelia/) <!-- live -->

## Features

- **🌍 Procedural worlds** — hills, valleys, beaches, water and trees generated
  from noise, different every new world
- **⛏️ Mine & build** — break and place blocks with a classic hotbar; DDA voxel
  raycasting for pixel-precise targeting
- **🧱 10 block types** — grass, dirt, stone, sand, wood, leaves, planks, glass,
  brick and water
- **🏃 Real first-person physics** — gravity, jumping, sprinting and full AABB
  collision against the voxel world
- **🕊️ Creative fly mode** — press `F` to lift off and build freely
- **🌗 Day/night cycle** — a moving sun, changing sky colour and fog
- **💾 Persistent world** — everything you build is saved locally (run-length
  encoded) and reloads when you come back
- **⚡ Runs anywhere** — pure WebGL via Three.js, 60 fps in a browser tab, works
  on desktop; no install

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
