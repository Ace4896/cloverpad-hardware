# More More Keypad!

**NOTE**: This project is still a work-in-progress, this note will be removed once it's ready!

A 3-key keypad for osu!, themed after [MORE MORE JUMP!](https://www.sekaipedia.org/wiki/MORE_MORE_JUMP!) from Project Sekai.

... picture of finished keypad ...

## Usage

Make sure you have the following things installed:

- [FreeCAD 0.21](https://www.freecad.org/)
- [KiCad 7](https://www.kicad.org/)
- [KiCad JLCPCB Tools](https://github.com/Bouni/kicad-jlcpcb-tools) (if you're using JLC for manufacturing the PCB)

Clone the repository with submodules:

```bash
git clone --recurse-submodules https://github.com/Ace4896/more-more-keypad.git
```

Then follow the [build guide](./docs/build-guide.md), which will reference various project files from these folders:

- [**assets**](./assets): Miscellaneous assets that were used in this project.
- [**case**](./case): FreeCAD 0.21 project for the sandwich mount case. It uses the [minimal PCB](./case/minimal-pcb/)'s 3D model as a design aid.
- [**docs**](./docs): Documentation and personal notes for this project.
- [**pcb**](./pcb): KiCad 7 project for the 3-key analog PCB, themed after [Haruka Kiritani](https://www.sekaipedia.org/wiki/Kiritani_Haruka).

## Licensing

This project is licensed under [CERN-OHL-S-2.0](./LICENSE).

Below is a list of assets used from other projects:

- [Project Sekai: Colourful Stage!](https://www.colorfulstage.com/)
  - © SEGA / © Colorful Palette Inc. / © Crypton Future Media, INC.
  - This is a fan project and has no affiliation with SEGA, Colorful Palette, or Crypton Future Media.
  - Assets from MORE MORE JUMP! and its characters are used in the [main PCB](./pcb).
- [ConstantinoSchillebeeckx/cherry-mx-switch](https://github.com/ConstantinoSchillebeeckx/cherry-mx-switch)
  - [MIT License](https://github.com/ConstantinoSchillebeeckx/cherry-mx-switch/blob/master/LICENSE)
  - The Cherry MX Switch 3D model is used in the [minimal PCB](./case/minimal-pcb/) that was made to help design the case.
- [ebastler/marbastlib](https://github.com/ebastler/marbastlib)
  - [CERN-OHL-P-2.0 License](https://github.com/ebastler/marbastlib/blob/main/LICENSE)
  - Various KiCad symbols and footprints are used in the [main PCB](./pcb) and the [minimal PCB](./case/minimal-pcb/).
