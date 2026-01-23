# piqued
Mutable Peaks port for AE modular

# Contents

Gerber files for frontpanel

Gerber/BOM/Placement files for PCB1 (top board: controls, LEDs etc)

Gerber/BOM/Placement files for PCB2 (lower board: core, DAC etc)

Schematics for PCBs 1&2 (PDFs)

'Peaks' folder contains customised firmware for AE modular (negative offset applied to DAC output specifically for envelopes so that they start at 0v)

# Programming

Use an STLINK programmer [like this](https://www.digikey.co.uk/short/z80h784r)

with a little adapter cable [like this](https://www.digikey.co.uk/short/9wrf4dtm)

and tiny header pins [like these](https://www.digikey.co.uk/short/wbzdn2vj)

Use the [Mutable Dev Environment](https://pichenettes.github.io/mutable-instruments-documentation/modules/peaks/open_source/) to upload, following the JTAG instructions

# Calibration

Hold MODE while powering on to enter calibration mode

Probe output 1 with a multimeter and finetune the output using knobs 1 and 2 until the output reads **2.5v**

+ Knob 1 (coarse) adjusts over a range of ~1v
+ Knob 2 (fine) adjusts over a range of ~0.1v

Repeat with output 2 using knobs 3 & 4

Press SPLIT to store calibration data.

# Extra

If you read this far, here's the lowdown on the secret modes:

Hold SPLIT and MODE together for about 1 second, release, and repeat twice more to enter Peaks' hidden [NUMBER STATION](https://pichenettes.github.io/mutable-instruments-documentation/modules/peaks/secrets/) mode

>The module generates a signal reminiscent of a number station, simulating a noisy AM receiver.

>The knobs control the pitch of the tone (or voice), the probability that it will switch to a different number, and the amount of noise and distortion.

Once in number station mode, press and hold SPLIT and MODE together for 1 second again to access a BOUNCING BALL envelope generator

This was left in the code by Emilie but disabled in the UI. I've brought it back for the AE version! Controls:

1. Gravity
2. Energy loss per bounce
3. Initial height of 'throw'
4. Initial velocity
