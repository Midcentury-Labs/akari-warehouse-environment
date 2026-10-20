# Akari Warehouse Environment — Scenes & Demo Videos

UE5 warehouse lighting-variant scenes (maps + camera sequences) and rendered demo videos produced for the Akari / NeuraShade neural renderer project.

## What's here

**`ue5-content/`** — Unreal Engine 5.8 content files, grouped as they should be copied into a project's `Content/` folder:

- `AkariRelease/` — orbit-path release scenes (`orbit_night.umap`, `orbit_overcast.umap`) with their camera-rail sequences (`seq_orbit_*.uasset`).
- `LightingReview/` — four lighting-variant scenes of the same warehouse (`afternoon`, `daylight`, `night`, `overcast` `.umap`) plus the fixed `camera_*.uasset` rigs used for the review captures.
- `WalkcamSequences/` — the four walkcam camera rails (`walkcam_1`–`4`) used to capture G-buffer training data.

**`media/`** — rendered outputs:

- `Akari-Launch-v1.mp4` — launch film (orbit scenes, night + overcast).
- `warehouse-1-*` / `warehouse-2-*` — full comparison videos, looped versions, and poster frames from the first two warehouse walkcam demos.
- `warehouse-3-full.mp4` / `warehouse-4-full.mp4` — comparison videos from the remaining two walkcam trajectories.
- `warehouse-reference.png` / `warehouse-neural.png`, `detail-reference.png` / `detail-neural.png` — side-by-side reference vs. neural-render comparisons.

## Requirements / how to open the maps

The scenes are built on the **Modular Warehouse** asset pack (available on Fab). The pack's meshes, materials, and textures are **not** redistributed in this repo — they are third-party licensed content. To open the maps:

1. Have the Modular Warehouse pack installed in a UE 5.8 project (so `/Game/ModularWarehouse/...` resolves).
2. Copy the folders from `ue5-content/` into the project's `Content/` directory.
3. On first open, allow Unreal to rebuild lighting data (precomputed lighting build data is intentionally excluded to keep the repo small; the scenes use Lumen for real-time lighting previews).

## Notes

- Scene arrangement, lighting setups, camera rails, and all rendered media are authored by Midcentury Labs as part of the Akari / NeuraShade neural rendering project.
- G-buffer capture for the neural renderer used these camera rails through a Movie Render Queue pipeline (albedo / normals / depth / roughness / metallic / irradiance passes).
