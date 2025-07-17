# Power Amp Design

The power amp for the Heirophone is just an LM386 powered from the +12v supply. To make sure the chip doesn't overheat and blow up, it's important to work out the voltage input range for a given power output and make sure it operates within those limits.

The [LM386 data sheet][lm386-datasheet] gives all the required information.

When running from a 12v supply, and running into a 4ohm load like the surface transducer, the peak-to-peak output voltage will max out at about 3.8 volts. This means the maximum power output we'll be able to get would be :-

```
vRMS = (vPtoP / 2) * 0.707
vRMS = 1.3433v

power = (vRMS ^ 2) / 4ohms = 0.45W
```

Based on the distortion figures, as well as the devices power dissipation based on power output, the aim is to keep the actual power output to about 0.13W maximum. This means the peak to peak voltage across the speaker should be roughly :-

```
sqrt(0.13W * 4ohms) = 0.721 vRMS

(0.721 vRMS / 0.707) * 2 = 2.04 vPtoP
```

Given the default gain of the LM386 is 20, this means the input voltage should be around 0.1 vPtoP

In theory the output from the opamp just prior to the power amp could be 12 vPtoP meaning ideally there is a gain reduction of 120 to keep within the right limits.


[lm386-datasheet]: https://www.ti.com/lit/ds/symlink/lm386.pdf
