# Print & Setup Guide (Expedition Outpost)

Notes on slicing, printing, and finishing **Expedition Outpost (Orange Home)**, plus what to check if you want to edit the Blender files.

## Files

| File | What it is |
| :--- | :--- |
| [`production/expedition_outpost_printable.stl`](./production/expedition_outpost_printable.stl) | Combined STL (`10.7 × 11.2 × 16.3 cm`, flat base at `Z = 0.0 mm`) |
| [`BOM.csv`](./BOM.csv) | Filament weight and cost estimate |
| `src/orange home.blend` | Main 3-story building scene (Blender 3.6+) |
| `src/otherassets.blend` | Crates, campfire logs, compasses, dustbin, and Walking Window |
| `src/Tent.blend` | Rooftop camping tent |

## Size and Scale

The model is `107.2 × 112.1 × 163.3 mm` (`10.7 × 11.2 × 16.3 cm`), so it fits on standard `18 × 18 × 18 cm` beds like the Bambu A1 mini, Prusa MINI, Ender 3, and Prusa MK4.

Keep it at **100% scale** unless you thicken the small parts first. Window bars, crate slats, and compass details are already under `0.8 mm` (with a few thin bars under `0.4 mm`), so shrinking the house down will make a `0.4 mm` nozzle skip them.

## Slicer Setup

Drop [`production/expedition_outpost_printable.stl`](./production/expedition_outpost_printable.stl) into Bambu Studio, OrcaSlicer, PrusaSlicer, or Cura and keep the base flat on the plate at `Z = 0.0 mm` (no raft needed).

The STL combines 185 sub-parts. If your slicer warns about non-manifold edges or overlapping shells, click **Repair / Fix Model** (Bambu Studio and OrcaSlicer usually handle it on import). Turn on **Arachne** or **Detect thin walls** and check the slice preview before printing so thin window bars and crate slats don't get dropped.

| Setting | Value | Why |
| :--- | :--- | :--- |
| Nozzle | `0.4 mm` | Standard FDM nozzle |
| Filament | `PLA` or `PLA+` | e.g. Numakers PLA+ (1.75 mm) |
| Layer height | `0.20 mm` (or `0.16 mm`) | `0.16 mm` picks up the window bars and compasses better |
| Walls | `3 walls` (`~1.2 mm`) | Keeps balcony railings, frames, and tent walls solid |
| Top / bottom layers | `4–5 layers` | Avoids pinholes on the roof and balconies |
| Infill | `15% Gyroid` | Keeps the inside light (`~323 g` model) |
| Supports | Tree / Organic (`Touching Buildplate only`) | Needed under the shop awning and 2nd-floor balcony (`~22 g`) |
| Bed adhesion | `Skirt` (or `Brim` if corners lift) | Flat base has plenty of contact area |

From slicer estimates (I don't have a 3D printer yet, so this hasn't been physically printed), a full print uses roughly `345 g` of filament (`~323 g` for the model + `~22 g` for tree supports), costs around `$2.24 USD (₹207)` at `₹600/kg`, and takes `~10–12 hours` at `0.20 mm`.

## Editing in Blender

If you want to tweak props, scale the house down with thicker bars, or split floors for multi-color printing:

1. Open `src/orange home.blend` in **Blender 3.6+** (and `src/otherassets.blend` or `src/Tent.blend` for individual props).
2. Before exporting a new `.stl`, apply scale (`Ctrl + A` -> *Scale*), set units to millimeters (`Scene Properties -> Units -> Millimeters`), keep the base at `Z = 0.0`, and thicken any fences, slats, or window bars to at least `0.8–1.2 mm` for a `0.4 mm` nozzle.

## Cleanup and Painting

Once the bed cools down, pop the print off and snip the tree supports under the shop awning, balcony overhang, and Walking Window legs with flush cutters. Knock down rough support marks or layer lines with `400–800` grit sandpaper.

If you want to paint it, put down a thin coat of matte grey or white plastic primer first, then use hobby acrylics (warm terracotta/orange walls, dark brown crates and campfire logs, off-white trims and railings, olive or tan for the tent) and finish with a matte clear coat.
