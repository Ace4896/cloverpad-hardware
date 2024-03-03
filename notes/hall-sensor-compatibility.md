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

The DRV5056A3 was chosen as it meets most of the criteria:

- Has a variant that can detect positive fields
- Generates a linear output
- Has a magnetic range of 78mT (780G) at 3.3V
  - Technically, this range is not large enough, but in the ideal case, we'd only lose the last 0.2mm of travel on average, which makes this viable in practice
- Is unipolar

The DRV5056A4 would also work and be able to track the entire keystroke, but its reduced resolution means that 0.1mm precision is harder to achieve, especially at the top of the keystroke where the ADC values are smaller.
