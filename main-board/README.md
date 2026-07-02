# Mission Pegasus PCB

KiCad design for the Mission Pegasus board — a Raspberry Pi Zero based
carrier with an AMS AS7265x spectral sensor front end.

## Opening the project

Open `Mission Pegasus.kicad_pro` in KiCad (10.0 or newer).

## Layout

```
Mission Pegasus.kicad_pro / .sch / .pcb   Main project (open this)
RPI0.kicad_sch                            Sub-sheet: Raspberry Pi Zero
StackInterface.kicad_sch                  Sub-sheet: stack / GPIO interface
fp-lib-table, sym-lib-table               Project-local library registrations

libraries/                                All custom parts libraries
├── footprints/   *.pretty                Footprint libraries
├── symbols/      *.kicad_sym             Symbol libraries
└── 3dmodels/     *.3dshapes              3D models (STEP)

docs/                                     Documentation & manufacturing
├── datasheets/                           AS7265x datasheets / app notes
├── Components.docx                       Component notes
├── Mission Pegasus.csv                   BOM
├── Order Request form.xlsx              Ordering paperwork
└── block_diagram.kicad_sch              Reference block diagram (not in build)

vendor/                                   Third-party tooling (reference only)
└── AS7265x DashBoard Software/           AMS dashboard app, firmware, FTDI driver
```

All library and 3D-model paths are project-relative (`${KIPRJMOD}`), so the
repo is self-contained — clone it anywhere and it opens without missing files.

## Note on library symbols

The symbols cached in the schematics (AS72652 / AS72653 / RASPBERRY_PI_ZERO_2_W)
are the authoritative, complete versions and match the PCB. The library copies
are older/incomplete. **Do not run _Tools → Update Symbols from Library_** on
these parts — it would pull the incomplete library version into the schematic
and break connectivity.
