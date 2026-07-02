# Mission Pegasus

Hardware for the Mission Pegasus project. Two mating PCBs that connect at
90° to each other.

## Boards

| Folder | Board | Description |
|---|---|---|
| [`main-board/`](main-board/) | Mission Pegasus main board | Raspberry Pi Zero carrier with an AMS AS7265x spectral sensor front end. |
| [`mezzanine-board/`](mezzanine-board/) | 90° mezzanine board | Daughterboard that mates perpendicular to the main board via the stack connector. |

Each board is a **self-contained KiCad project** with its own `libraries/`
folder, so you can open either one independently. Open the `.kicad_pro`
inside the board's folder.

## Repository layout

```
main-board/          Main board KiCad project (see main-board/README.md)
mezzanine-board/     90° mezzanine KiCad project
vendor/              Shared third-party tooling (AMS dashboard app, firmware, FTDI driver)
```

## The 90° interface

The two boards share a mating connector (2x26 2.54 mm header/socket). When
changing anything on that connector — pinout, position, or board outline —
update **both** boards together and check the mechanical fit in KiCad's 3D
viewer (export STEP from each and confirm the perpendicular alignment).
