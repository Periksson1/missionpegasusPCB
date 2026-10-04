# Mission Pegasus main board

KiCad design for the Raspberry Pi Zero carrier and stack interface in the
Mission Pegasus two-board assembly.

## Opening the project

Use **KiCad 10.0 or newer** and open
[`Mission Pegasus.kicad_pro`](Mission%20Pegasus.kicad_pro).
See the [root README](../README.md) for cloning the current `UART-board` branch.

## Files and references

| Path | Purpose |
|---|---|
| `Mission Pegasus.kicad_pro` | KiCad project settings |
| `Mission Pegasus.kicad_sch` | Root schematic |
| `Mission Pegasus.kicad_pcb` | PCB layout |
| `RPI0.kicad_sch` | Raspberry Pi Zero schematic sub-sheet |
| `StackInterface.kicad_sch` | Stack/GPIO interface sub-sheet |
| `fp-lib-table`, `sym-lib-table` | Project-local library registrations |
| `libraries/` | Custom footprints, symbols, and 3D models |
| `docs/` | Datasheets, component notes, ordering paperwork, and reference block diagram |
| `Mission PegasusBOM.csv` | Saved board BOM |
| `Images/` | Project artwork |
| `mainboard*.step`, `mainboard6/` | Mechanical exports and CAD files |

Custom library tables use `${KIPRJMOD}` paths. Keep the libraries with the
project and install the standard KiCad libraries. Third-party dashboard software,
firmware, and drivers are in [`../vendor/`](../vendor/).

## Interface and status

See the [stack schematic](StackInterface.kicad_sch) and
[draft mezzanine interface notes](../MEZZANINE_INTERFACE.md). The notes still have
incomplete pin assignments and must be checked against the current schematics.

Schematic and PCB design files are present. Manufacturing and electrical test
results are not documented. Check the [BOM](Mission%20PegasusBOM.csv) and mechanical
exports against the selected revision before using them for fabrication.

## Note on library symbols

The symbols cached in the schematics (`AS72652`, `AS72653`, and
`RASPBERRY_PI_ZERO_2_W`) are the authoritative, complete versions described by this
project's existing documentation. The library copies are older/incomplete.
**Do not run Tools → Update Symbols from Library on these parts** without first
reconciling the definitions; replacing them can break connectivity.
