# Art Bible — PET-GAME 橫向世界觀
Locked 2026-08-29. Truth source: this folder `petgame-art/` (zip `petgame-art-truthsource.zip`).
Do not AI-redraw 魔比. Do not invent new facing sheets.

## 1. World
- The whole series is **2D side-scroll only**. Camera travels east. No 3/4 overworld, no free roam.
- **魔比 is the visual lead.** The dog walks through the world. Scenes and dialogue sit on the **foreground HUD layer** and pass by as Mobi walks. Copy is never baked into the background plate.
- Layers: Far (parallax ~0.2) / Mid (~0.55) / Ground (1.0) / Mobi / **Foreground HUD (all titles, subtitles, speech, CTA)**.

## 2. Sprite facing (hard lock)
Sprites and world objects only ship these facings:

| Kind | Allowed | Use |
|---|---|---|
| Moving through the world | **EAST side** (and **NORTH** when looking at camera while still walking the X axis) | Walk / run / ride / hop |
| Position-locked | **SOUTH or NORTH side** | Idle, sit, sing, sleep, shop thumb. Must not travel on X. |

- Do **not** author WEST unique sheets. If a leftward beat is required, mirror EAST. Prefer writing the beat so Mobi keeps walking east.
- Canvas: **128×128** per frame, feet baseline **Y=112**, center X=64, PNG nearest, no grey modulate.

## 3. Truth source pack (this drop)
P00001 魔比 / Frenchie is the series lead. P00002 cat is catalog only, not Reels lead.

### P00001-frenchie
- `shop/P00001.png` — 128×128 shop / face lock
- `_inbox/pixellab-Walking.png` — EAST walk, 4×3 grid 512×384, 11 live frames
- `_inbox/pixellab-running.png` — EAST run, 4×3 grid
- `_inbox/pixellab-Frenchie-idle.png` — NORTH/locked idle (guitar), 3×3 grid 384×384
- `_inbox/` love / sleep / sing / bike / car / plane — toy-granted, position-locked or EAST vehicle

### Toys
T00009 micstand, T00010 bicycle, T00011 plane, T00012 car (`shop/` + `export/`).

### Objects
O00002–O00010 world props. Place on ground band. Unique props do not tile.

### Background
Empty in this drop. Reels still use per-episode plates, but **each scene is a horizontal slot**, not a new camera setup.

## 4. Scene change = playground slot cover
When the story changes place, do **not** hard-cut the camera.
Join two horizontal slots the way PET-GAME playground slots join:

- Slots tile on X (game stage slot width 1320px in pet-game; Reels may use a Godot equivalent).
- At the **connecting seam**, put a **visual cover** (arch, tree, fog, wipe, light flash, doorway) so the join is hidden.
- Mobi keeps walking east through the cover. HUD copy can swap on the far side.
- Far / mid parallax may change behind the cover. Moon and other unique far props **do not wrap**.

## 5. Demo / engine
Godot project: `engine/mobi-world`. Demo Mobi must use **this pack's EAST walk**, nearest, cream P00001 face. No PixelLab stills, no Grok redraw.

## 6. Type (Reels HUD)
Glow Sans TC ExtraBold, yellow `#FFD000`, black outline + drop shadow. Written Chinese. CTA `追蹤魔比`. All copy on HUD, optically centered.

Do not post proofs. No episode until user says start.
