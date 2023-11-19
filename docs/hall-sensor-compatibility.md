# Hall Sensor Compatibility

**NOTE**: As far as I'm aware, the KS-20 and Lekker switches use the same mechanism, and the only differences are branding, colours and spring weight. It should be possible to use them interchangably.

In the KS-20's datasheet, there are a few key pieces of information:

- Total Travel: 4.1 +/- 0.2mm
- Hall Sensor Placement: Back of PCB
- Orientation of Permanent Magnet: North pole at bottom of switch
- Magnetic Flux Density @ North Pole:
  - Initial Position: 102 +/- 15G
  - Total Travel Position: 905 +/- 80G

Based on the hall sensor placement and the orientation of the permanent magnet, it generates a positive field. In the diagram below (credit: [Texas Instruments - SLYT826](https://www.ti.com/document-viewer/lit/html/slyt826)), we can see this in the top-right case:

![Sensor Polarity](./sensor-polarity.png)

This means that the hall sensor used needs to have the following properties:

- Detect a positive magnetic field (sometimes referred to as "south active")
- Produce a linear output so we can get analog readings
- Have a magnetic range that covers the maximum magnetic flux
- (Ideally) Unipolar i.e. reacts to only one pole / field direction
  - Technically, we can use a bipolar sensor that reacts to both poles, but we lose half of the resolution to a range of values that we won't use

The DRV5056A3 was chosen as it meets most of this criteria:

- Has a variant that can detect positive fields
- Generates a linear output
- Has a magnetic range of 79mT (790G)
- Is unipolar

The only downside is that we can't detect the full travel distance, since the analog output will be saturated before we reach the end of a keypress. If we wanted to detect the whole keypress, we could use the DRV5056A4 instead (magnetic range of 158mT / 1580G), but we lose a large section of the output voltage range as our maximum magnetic flux density is only 905G.
