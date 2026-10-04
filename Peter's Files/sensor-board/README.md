# Mezzanine board (90°)

Daughterboard that mates **perpendicular** to the Mission Pegasus main board
via the shared 2x26 (2.54 mm) stack connector.

> Status: not started — create the KiCad project into this folder (see below).

## Creating the project

1. In KiCad: **File → New Project…**
2. Save it **inside this `mezzanine-board/` folder** (e.g. `Mezzanine.kicad_pro`).
   Keep "Create a new folder" **unchecked** so the files land here directly.
3. Custom parts go in the pre-made `libraries/` subfolders:
   - `libraries/footprints/` (`.pretty`)
   - `libraries/symbols/` (`.kicad_sym`)
   - `libraries/3dmodels/` (`.3dshapes`)
   Register them in this project's `fp-lib-table` / `sym-lib-table` using
   `${KIPRJMOD}/libraries/...` paths so the board stays self-contained.

## The 90° mating interface

- Use the **same connector part and pinout** as the main board's stack
  interface (see `../main-board/StackInterface.kicad_sch`). Pin 1 must meet
  pin 1.
- For the right-angle mate, typically one board carries a **right-angle**
  header and the other a vertical socket. Decide which side is which.
- Match the **connector position and board outline** so the boards align
  physically. Verify by exporting STEP from both boards and checking the
  perpendicular fit in a 3D view.
