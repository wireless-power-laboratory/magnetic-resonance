## Research and development of magnetic resonance technologies

Output relating to my work on coupled-coil wireless-power transfer by magnetic resonance.

### The foundation brought by wireless power

My work over the past fifteen years has revolved around this kind of output

![lab-fun](/img/lab-fun.jpg)

Where a pair of 30mm-radius, three-turn, inductive loop coils illustrate that 5V DC power can be thusly utilized to power wirelessly.

### Basic analytic arrangement

There is a task to measure the coupling-coefficient between two 12mm radius, ten-turn, inductive loop coils. It is interesting to know whether the efficiency is better or worse with small coils verses the larger ones that can power lamps at a distance. We would like to determine emperically what are the losses across a frequency sample (band); in this case, between 100 kHz and 100 MHz.

Using the hp[8601A](https://github.com/wireless-power-laboratory/hp8601a) Sweeper/Generator in _tracking generator mode_, one can observe the linearity of two 12.5mm-radius, 10-turn inductive-loop coils on a hp[141S](https://github.com/wireless-power-laboratory/hp141s) Spectrum Analyzer. Before we can do this, the hp8601A is set to run as a tracking generator by modifying the internals in such a way as to direct the `VTO` out and the `1st LO` in.

![8601-007](/img/8601-007.jpg)

Where the input for the `1st LO` will come as an output from the hp[8553L](/img/8553-lo.jpg) plug-in for the hp141S Spectrum Analyzer. When using in a single-frequency setting, one can turn the knob on the hp8601A to change the output; for the purposes of this experiment the entire range will be applied to the coils

