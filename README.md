# More More Keypad!

**NOTE**: This project is still a work-in-progress, this note will be removed once it's ready!

A 3-key keypad for osu!, themed after [MORE MORE JUMP!](https://www.sekaipedia.org/wiki/MORE_MORE_JUMP!) from Project Sekai.

... picture of finished keypad ...

## Usage

Make sure you have the following things installed:

- [FreeCAD 0.21](https://www.freecad.org/)
- [KiCad 7](https://www.kicad.org/)
- [KiCad JLCPCB Tools](https://github.com/Bouni/kicad-jlcpcb-tools) (if you're using JLC for manufacturing the PCB)

First, clone the repository with submodules:

```bash
git clone --recurse-submodules https://github.com/Ace4896/more-more-keypad.git
```

Then follow the [build guide](./docs/build-guide.md), which will reference various project files from these folders:

- [**case**](./case): FreeCAD 0.21 project for the sandwich mount case. It uses the [minimal PCB](./case/minimal-pcb/)'s 3D model as a design aid.
- [**docs**](./docs): Documentation and personal notes for this project.
- [**pcb**](./pcb): KiCad 7 projects for the 3-key analog PCB, themed after [Haruka Kiritani](https://www.sekaipedia.org/wiki/Kiritani_Haruka).

## Credits

- [ConstantinoSchillebeeckx/cherry-mx-switch](https://github.com/ConstantinoSchillebeeckx/cherry-mx-switch): Cherry MX Switch 3D Model
  - Licensed under [MIT](https://github.com/ConstantinoSchillebeeckx/cherry-mx-switch/blob/master/LICENSE)
  - Used in the [minimal PCB](./case/minimal-pcb/) that was made to help design the case.
- [ebastler/marbastlib](https://github.com/ebastler/marbastlib): Collection of KiCad footprints for keyboards
  - Licensed under [CERN Open Hardware Licence Version 2](https://github.com/ebastler/marbastlib/blob/main/LICENSE)
  - Used in the [main PCB](./pcb) and the [minimal PCB](./case/minimal-pcb/).
