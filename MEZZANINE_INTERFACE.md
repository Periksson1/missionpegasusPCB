# Mezzanine 90° Interface Specification

The single source of truth for the connector shared between the **main board**
and the **90° mezzanine board**. Edit this first; then make both boards match it.

## Connector

| Property | Value |
|---|---|
| Type | 2×20, 2.54 mm pitch, 40 positions |
| Mezzanine side | Molex **90152-2140** right-angle receptacle (makes the mezzanine stand vertical) |
| Main board side | Vertical 2×20 pin header (KiCad `Connector_PinHeader_2.54mm:PinHeader_2x20_P2.54mm_Vertical`) |
| Locations on main board | **3**, all populated, wired **in parallel** to the same nets (plug the mezzanine into any one) |
| Constraint | Only **one** mezzanine plugged at a time (parallel positions share nets) |

> Pin 1 on the main-board header must meet pin 1 on the mezzanine receptacle.
> Confirm the receptacle's pin-1 location and numbering direction against the
> Molex datasheet before finalizing the footprint.

## Pin assignment (fill this in)

Signals are TBD — assign from the "available signals" menu below based on what
the mezzanine needs. Power/ground pins are pre-suggested for signal integrity
(GND on corners + middle; keep power and its return adjacent).

| Pin | Signal | | Pin | Signal |
|----:|--------|-|----:|--------|
| 1 | GND *(key/orientation)* | | 2 | 5V_PERM |
| 3 | TBD | | 4 | 5V_PERM |
| 5 | TBD | | 6 | GND |
| 7 | TBD | | 8 | TBD |
| 9 | TBD | | 10 | TBD |
| 11 | TBD | | 12 | TBD |
| 13 | TBD | | 14 | TBD |
| 15 | TBD | | 16 | TBD |
| 17 | TBD | | 18 | TBD |
| 19 | TBD | | 20 | GND |
| 21 | GND | | 22 | TBD |
| 23 | TBD | | 24 | TBD |
| 25 | TBD | | 26 | TBD |
| 27 | TBD | | 28 | TBD |
| 29 | TBD | | 30 | TBD |
| 31 | TBD | | 32 | TBD |
| 33 | TBD | | 34 | TBD |
| 35 | TBD | | 36 | GND |
| 37 | TBD | | 38 | BATT |
| 39 | GND | | 40 | BATT |

## Available signals (from the main board stack, for reference)

Buses / signals present on the main board that the mezzanine could tap:

- **Power**: `5V_PERM`, `BATT`, `CHARGE`, `PWR_1`…`PWR_20` (each with an `ENA_PWR_n` enable)
- **CAN**: `CAN_A_H` / `CAN_A_L`, `CAN_B_H` / `CAN_B_L`
- **UART**: `UART_A_UP`/`UART_A_DN` … `UART_F_UP`/`UART_F_DN`
- **Deploy / RBF**: `RBF_A`, `RBF_B`, `DS_A`, `DS_B`
- **Ground**: `GND`

Full extracted stack pinout is in the git history of `main-board/` (netlist);
regenerate anytime with:
`kicad-cli sch export netlist --format kicadxml "main-board/Mission Pegasus.kicad_sch"`

## Build order

1. **This file** — lock the 40-pin assignment.
2. **Main board** — add 3× `PinHeader_2x20_P2.54mm_Vertical`, wire all three in
   parallel to the assigned nets, add mounting holes at each location.
3. **Mezzanine board** — place the Molex right-angle receptacle with the same
   pinout, design the board outline, add matching mounting holes.
4. **Mechanical check** — export STEP from both boards, confirm the perpendicular
   fit and that the 3 positions don't collide with other components.
