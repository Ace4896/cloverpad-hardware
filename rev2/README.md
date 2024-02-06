# Cloverpad rev. 2

**NOTE**: This revision is still a work-in-progress, this note will be removed once it's ready!

This folder contains the hardware designs for the Cloverpad rev. 2. This is an incremental improvement over rev. 1, which resolves various issues with the 3D printed case.

Features:

- RP2040 MCU
- Cloverpad HE supports hot-swappable MX-style hall effect switches
- Cloverpad MX supports hot-swappable MX-style digital switches
- 3D printed case w/ threaded inserts

Required parts (for reference):

- 3D printed case + PCB
- USB Type-C cable
- 8x M2x6mm screws
- 8x M2x3mm threaded inserts
- Rubber feet

## Design Files

- [`cloverpad-case.FCStd`](./cloverpad-case.FCStd): FreeCAD 0.21 project for the 3D printed case.
- [`cloverpad-he-pcb`](./cloverpad-he-pcb): KiCad 7 project for the Cloverpad HE rev. 2 PCB.
- [`cloverpad-mx-pcb`](./cloverpad-mx-pcb): KiCad 7 project for the Cloverpad MX rev. 2 PCB.
