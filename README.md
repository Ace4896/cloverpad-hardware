# Cloverpad - Hardware

**NOTE**: This project is still a work-in-progress, this note will be removed once it's ready!

This repository contains the hardware designs for the Cloverpad, a 3-key keypad for osu! themed after [MORE MORE JUMP!](https://www.sekaipedia.org/wiki/MORE_MORE_JUMP!) from Project Sekai.

... picture of finished keypad ...

There are two PCB variants for this keypad:

- **Cloverpad HE**: PCB for use with hall effect switches (e.g. Wooting Lekker, Gateron KS-20), themed after [Haruka Kiritani](https://www.sekaipedia.org/wiki/Kiritani_Haruka).
- **Cloverpad MX**: PCB for use with regular MX-style mechanical switches, themed after [Minori Hanasato](https://www.sekaipedia.org/wiki/Hanasato_Minori).

## Usage

Make sure you have the following things installed:

- [FreeCAD 0.21](https://www.freecad.org/)
- [KiCad 8](https://www.kicad.org/) with the following plugins:
  - [marbastlib Keyboard Footprints](https://github.com/ebastler/marbastlib)
  - [KiCad JLCPCB Tools](https://github.com/Bouni/kicad-jlcpcb-tools) (if you're using JLC for manufacturing the PCB)

Clone the repository:

```bash
git clone git@github.com:Cloverpad/cloverpad-hardware.git
```

Then navigate to the folder for the revision you're interested in:

- [Rev. 2](./rev2)
- [Rev. 1](./rev1) (Cloverpad MX only; not recommended due to design flaws)

## Additional Files

These project files were used to help design the case and PCB:

- [**assets**](./assets): Miscellaneous assets - logos, character emotes etc.
- [**notes**](./notes): Personal notes for this project - you may find them useful if you're designing a keypad/keyboard of your own
- [**kle**](./kle): Keypad layouts generated by [Keyboard Layout Editor](http://www.keyboard-layout-editor.com/)

## Licensing

This project is licensed under [CERN-OHL-S-2.0](./LICENSE).

Below is a list of assets used from other projects:

- [Project Sekai: Colourful Stage!](https://www.colorfulstage.com/)
  - © SEGA / © Colorful Palette Inc. / © Crypton Future Media, INC.
  - This is a fan project and has no affiliation with SEGA, Colorful Palette, or Crypton Future Media.
  - Assets from MORE MORE JUMP! and its characters are used in the PCB designs.
- [ConstantinoSchillebeeckx/cherry-mx-switch](https://github.com/ConstantinoSchillebeeckx/cherry-mx-switch)
  - [MIT License](https://github.com/ConstantinoSchillebeeckx/cherry-mx-switch/blob/master/LICENSE)
  - The Cherry MX Switch 3D model is used in the minimal PCB.
- [ebastler/marbastlib](https://github.com/ebastler/marbastlib)
  - [CERN-OHL-P-2.0 License](https://github.com/ebastler/marbastlib/blob/main/LICENSE)
  - Various KiCad symbols and footprints are used in the PCB designs and the minimal PCB.
