Dual Bat Detector
=================

Andrew Martin, acramonics, 2026
-------------------------------

This design combines two circuits for bat detection that use different
principles.

### Frequency Divider

The top part of the circuit diagram and PCB uses two LM386 audio
amplifiers to boost the signal and a 4024 chip to divide the frequency
down to the audio range. This circuit is the 'Enhanced Bat Detector'
from https://batdetector.freevar.com/ This design doesn't require any
tuning of the detector and will cover all frequencies.

### Heterodyne

This bottom part of the circuit diagram and PCB implements a
heterodyne design with the same principle as an AM radio. The circuit
comes from *Nuts and Volts* magazine at
https://www.nutsvolts.com/magazine/article/june2011_berber This uses
just one IC (an LM324 quad opamp). The first opamp is a high-gain
amplifier combined with a high-pass filter (>20kHz); the second opamp
provides further amplification and filtering; the third opamp is an
oscillator with a frequency range of around 15-110kHz; the fourth
opamp is the heterodyne mixer taking the amplified/filtered signal
together with the oscillator signal and outputs the difference between
them.

Building the circuit
--------------------

You can, of course just build one part of the circuit, but the design
is such that you can use a 3PDT switch to select between the two
circuits. (You could also use a 3P3T switch to have an off position
where nothing is connected.)



### Switches

- An ON-OFF-ON toggle switch, the MTS-303R is available from
  [AliExpress](https://www.aliexpress.com/item/1005007484491572.html)
- A 3PDT toggle switch, the TE Connectivity 2-1825139-3, is available
  from
  [Rapid Electronics](https://www.rapidonline.com/te-connectivity-2-1825139-3-toggle-switch-3pdt-on-off-on-pcb-mount-15-1926)
- Alpha produce 4P3T rotary switches such as the SR2611-0403-38F5
  available from
  [Rapid Electronics](https://www.rapidonline.com/taiwan-alpha-sr2611-0403-38f5-make-before-break-rotary-switch-4-pole-3-way-79-0115)
  or the SR2511F-0303-19R0B-E9-S-W-159 available from
  [Mouser](https://www.mouser.co.uk/ProductDetail/Alpha-Taiwan/SR2511F-0303-19R0B-E9-S-W-159?qs=8%252Br4Hz5Xir%2F8i45vdtZdhg%3D%3D)
- Other choices include 4P3T switches from Alps Alpine
  [RS, SRRM433700](https://uk.rs-online.com/web/p/rotary-switches/1239626)
  and various choices from Lorlin CK  
  [See the datasheet](https://docs.rs-online.com/7602/A700000008016972.pdf)
- A 4P3T rotary switch, the RS26, is also available from AliExpress
  https://www.aliexpress.com/item/1005008776212710.html
- Various 3P3T wafer-style switches are also available and described
  as 'Rotary Band Switches' See:
  - https://www.aliexpress.com/item/1005011839909128.html
  - https://www.aliexpress.com/item/1005007021912980.html
  - https://www.aliexpress.com/item/1005005723913772.html
  - https://www.aliexpress.com/item/1005011597813751.html
  - https://www.aliexpress.com/item/1005006184759913.html
  - https://www.aliexpress.com/item/1005010336131768.html
  - https://www.aliexpress.com/item/1005008856647634.html

### Potentiometer

The dual-gang B100K potentiometer is a compromise between the
recommended B50K for the heterodyne circuit and the A220K for the
frequency divider. It should be fine for the latter, but it may be
necessary to put a 47K resistor in parallel with the pot used for the
heterodyne circuit.

### Optional parts

R2, R3, C5 and C10 in the frequency divider circuit shouldn't be
needed but can be added if there is instability in the
amplifier.  Similarly, C3 and C8 shouldn't be needed.

L1 and L2 may not be needed depending on the transducer/microphone used.

### Transducer/Microphone

40kHz ultrasonic transducer are easily available from AliExpress and
most good component suppliers. However, according to the *Nuts and
Volts* article, a simple piezo or ceramic sounder used as a microphone
can be better. produce superior results. For these, L1 and L2 are not
needed. 

### Headphones/earpiece

A crystal earpiece is ideal.

### Component values

Some of the values are dependent on the sensor/microphone used.

**With a 40kHz ultrasonic transducer:**

- L1=6.8mH
- R1=150R or 220R
- RV1 should be set to a value in the range 150R to 2K2. 470R to 1K5
  is a good starting point. Increased values can be used if the
  detector is too noisy or oscillates.
- L2 is in the range 10uH to 6.8mH

**With other piezo/ceramic transducers**

- L1/L2 are not used
- R1 and RV1 adjusted as above

