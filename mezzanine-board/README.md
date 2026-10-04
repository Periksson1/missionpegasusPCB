# Mission Pegasus mezzanine sensor board

Spectral sensor daughterboard for the perpendicular Mission Pegasus assembly.
The KiCad project already contains a schematic and PCB layout.

## Opening the project

Use **KiCad 10.0 or newer** and open [`sensorPCB.kicad_pro`](sensorPCB.kicad_pro).
See the [root README](../README.md) for cloning the current `UART-board` branch.
Keep the project's `libraries/` directory alongside the design files; custom
library registrations use `${KIPRJMOD}` paths. Standard KiCad libraries are also
needed.

## Files and references

| Path | Purpose |
|---|---|
| `sensorPCB.kicad_pro` | KiCad project settings |
| `sensorPCB.kicad_sch` | Sensor-board schematic |
| `sensorPCB.kicad_pcb` | Sensor-board PCB layout |
| `fp-lib-table`, `sym-lib-table` | Custom library registrations |
| `libraries/` | Custom symbols, footprints, and 3D models |
| `sensorPCBBOM.csv` | Saved sensor-board BOM |
| `sensorboard*.step` | Mechanical exports |
| `sensorboard2/`, `sensorboard3/`, `sensorboard5/` | CAD parts and assemblies |

## Mating interface

Review the [main-board stack schematic](../main-board/StackInterface.kicad_sch)
and both current board schematics when checking the connector pinout. The
[draft interface notes](../MEZZANINE_INTERFACE.md) contain incomplete assignments;
they are not a verified wiring specification.

Confirm pin-1 orientation, matching signal assignments, connector placement,
and clearance in the perpendicular assembly. Assembly CAD is in
[`../CAD/`](../CAD/).

## Design status

Schematic, PCB, BOM, and mechanical files are present. Manufacturing, assembly,
and electrical test results are not documented. The [BOM](sensorPCBBOM.csv) and
CAD exports should be checked against the chosen PCB revision before use.
