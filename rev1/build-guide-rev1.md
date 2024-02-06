# Build Guide for Cloverpad rev. 1

**TODO**: Needs updating to match the new 3D printed case design

To build the keypad, you'll need:

- [`Standard Parts`](#standard-parts) - screws, rubber feet
- [Case](#case) - 3D printed case
- One of the PCBs:
  - [Cloverpad HE](#cloverpad-he-pcb-hall-effect-switches) if you're using hall effect mechanical switches
  - [Cloverpad MX](#cloverpad-mx-pcb-mechanical-switches) if you're using regular MX-style mechanical switches
- Mechanical switches for your chosen PCB
  - The Cloverpad HE is compatible with Wooting Lekker and Gateron KS-20 hall effect mechanical switches
  - The Cloverpad MX is compatible with any MX-style mechanical switch

## Standard Parts

It should be possible to find these parts from places like Amazon or electronics stores.

|          Part          | Quantity |
| :--------------------: | :------: |
| 20mm Round M2 Standoff |    4     |
|       M2 Screws        |    8     |

**NOTE**: Before you get the case and PCB manufactured, you'll need to check the outer diameter of the M2 standoffs you're using. Usually, this is 3.2mm - the default mounting holes in the case and PCB have a diameter of 3.5mm, which should give enough room to account for tolerances.

If you do need to modify the mounting hole diameter, there are a few things to change:

- `cloverpad-case`:
  - Open the project in FreeCAD
  - In the tree view on the left, open `parameters` - this will open the spreadsheet view
  - Modify the value of `Standoff Outer Diameter / mm` so that it's slightly larger than the standoff's outer diameter
  - Export each layer of the case in the appropriate format
- `cloverpad-he` / `cloverpad-mx`:
  - Open the `.kicad_pro` file - this will open the project view
  - Open the `.kicad_sch` file - this will open the schematic view
  - In the schematic view:
    - Run the footprint assignment tool
    - Find and highlight H1, H2, H3 and H4
    - Change the mounting hole footprint to one that is slightly larger than the standoff's outer diameter
    - Save the footprint assignments
  - Open the `.kicad_pcb` file - this will open the PCB view
  - In the PCB view:
    - Update the PCB footprints from the schematic file
    - Ensure that the centre of each hole remained the same
    - Hide the H1, H2 etc. labels for the mounting holes
    - Use the KiCad JLCPCB extension to generate the new Gerbers, BOM and CPL files

## Case

The case design uses a stacked acrylic sandwich mount with the following layers:

|      Part       |      Material       | Quantity |
| :-------------: | :-----------------: | :------: |
|  `top-spacer`   |     3mm Acrylic     |    2     |
|     `plate`     | 5mm Frosted Acrylic |    1     |
| `bottom-spacer` | 5mm Frosted Acrylic |    1     |
| `bottom-piece`  | 3mm Frosted Acrylic |    1     |

Frosted acrylic was chosen for the bottom pieces and plate as it can diffuse the RGB underglow lighting better, though regular acrylic is fine as well.

## Cloverpad HE PCB (Hall Effect Switches)

The Cloverpad HE PCB currently uses these parts:

|               Component                |              Footprint              |   LCSC   |
| :------------------------------------: | :---------------------------------: | :------: |
|             22pF Capacitor             |          C_0402_1005Metric          |  C1555   |
|            100nF Capacitor             |          C_0402_1005Metric          |  C1525   |
|             1uF Capacitor              |          C_0402_1005Metric          |  C52923  |
|             10uF Capacitor             |          C_0603_1608Metric          |  C19702  |
|            27 Ohm Resistor             |          R_0402_1005Metric          |  C25100  |
|            100 Ohm Resistor            |          R_0402_1005Metric          |  C25076  |
|            1k Ohm Resistor             |          R_0402_1005Metric          |  C11702  |
|           5.1k Ohm Resistor            |          R_0402_1005Metric          |  C25905  |
|       USB-C Receptacle (USB 2.0)       | USB_C_Receptacle_HRO_TYPE-C-31-M-12 | C165948  |
|         500mA Resettable Fuse          |        Fuse_1206_3216Metric         | C170165  |
|        ESD Protection (SRV05-4)        |          SOT-23-6-routable          | C2836319 |
|  3.3V Voltage Regulator XC6206P332MR   |              SOT-23-3               |  C5446   |
|        Microcontroller (RP2040)        | QFN-56-1EP_7x7mm_P0.4mm_EP3.2x3.2mm |  C2040   |
|             12MHz Crystal              |   Crystal_SMD_3225-4Pin_3.2x2.5mm   |  C9002   |
|       16MB Flash (W25Q16JVSSIQ)        |     SOIC-8_5.23x5.23mm_P1.27mm      | C131025  |
| 5V Logic Level Converter (74AHCT1G125) |           SOT-353_SC-70-5           | C151417  |
|     Hall Sensor (DRV5056A4xDBZxQ1)     |          KS-20-1U-DRV5056           | C2152902 |
|   Switch SMD RGB LEDs (SK6812MINI-E)   |            LED_MX_6028R             | C5149201 |
|      Underglow RGB LEDs (WS2812B)      | LED_WS2812B_PLCC4_5.0x5.0mm_P3.2mm  | C2761795 |
|              Push Buttons              |           SW_SPST_TL3342            | C318884  |

Some things to keep in mind for each component:

- **22pF Capacitors**: These are used for the crystal; if you're using a different crystal, you'll need to recalculate the values
- **Flash Memory**: Anything from Winbond's W25Q series should work; I've picked 16MB as it's more than enough for this project
- **Hall Sensor**: Use the A4 variant of the DRV5056 or DRV5056-Q1 (this should have 155mT / 1550G of magnetic range at 3.3V). The Q1 is usually more expensive as it's certified for automotive use
- **Underglow RGB LEDs**: Any 50x50mm variant of the WS2812B that operates on 5V logic should work
- **Switch SMD RGB LEDs**: Make sure that the LEDs have extruding pins which allow them to be reverse mounted

## Cloverpad MX PCB (Mechanical Switches)

The Cloverpad MX PCB currently uses these parts:

|               Component               |              Footprint              |   LCSC   |
| :-----------------------------------: | :---------------------------------: | :------: |
|            22pF  Capacitor            |          C_0402_1005Metric          |  C1555   |
|            100nF Capacitor            |          C_0402_1005Metric          |  C1525   |
|             1uF Capacitor             |          C_0402_1005Metric          |  C52923  |
|            10uF Capacitor             |          C_0603_1608Metric          |  C19702  |
|            27 Ohm Resistor            |          R_0402_1005Metric          |  C25100  |
|            1k Ohm Resistor            |          R_0402_1005Metric          |  C11702  |
|           5k1 Ohm Resistor            |          R_0402_1005Metric          |  C25905  |
|      USB-C Receptable (USB 2.0)       | USB_C_Receptacle_HRO_TYPE-C-31-M-12 | C165948  |
|         500mA Resettable Fuse         |        Fuse_1206_3216Metric         | C170165  |
|       ESD Protection (SRV05-4)        |          SOT-23-6-routable          | C2836319 |
| 3.3V Voltage Regulator (XC6206P332MR) |              SOT-23-3               |  C5446   |
|       Microcontroller (RP2040)        | QFN-56-1EP_7x7mm_P0.4mm_EP3.2x3.2mm |  C2040   |
|             12MHz Crystal             |   Crystal_SMD_3225-4Pin_3.2x2.5mm   |  C9002   |
|       16MB Flash (W25Q16JVSSIQ)       |     SOIC-8_5.23x5.23mm_P1.27mm      | C131025  |
|         Kailh Hotswap Sockets         |             SW_MX_HS_1u             | C5156480 |
|             Push Buttons              |           SW_SPST_TL3342            | C318884  |

Some things to keep in mind for each component:

- **22pF Capacitors**: These are used for the crystal; if you're using a different crystal, you'll need to recalculate the values
- **Flash Memory**: Anything from Winbond's W25Q series should work; I've picked 16MB as it's more than enough for this project

## Ordering From JLCPCB (WIP)

- Use JLCPCB tool to generate required files
- Upload Gerber `.zip` file
- Enable PCB assembly and upload BOM + CPL files
  - Cross-check detected parts + pricing after uploading BOM - some may be missing
  - Cross-check component placement against rendered PCB

## Assembling the Keypad (WIP)

The layers on the keypad should be the following (top-to-bottom):

- Top Spacer
- Top Spacer
- Plate
- PCB
- Bottom Spacer
- Bottom Piece
