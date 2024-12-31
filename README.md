## Research and development of magnetic resonance technologies

Output relating to my work on coupled-coil wireless-power transfer by magnetic resonance.

### The foundation brought by wireless power

My work over the past fifteen years has revolved around this kind of output

![lab-fun](/img/lab-fun.jpg)

Where a pair of 30mm-radius, three-turn, inductive loop coils illustrate that 5V DC power can be thusly utilized to power wirelessly.

### Analytical Task

`TODO: Calibrate the graticules and rephotograph for ease of viewing. Discuss and document the calibration in the appropriate repos.`

There is a task to measure the coupling-coefficient between two 12mm radius, ten-turn, inductive loop coils. It is interesting to know whether the efficiency is better or worse with small coils verses the larger ones that can power lamps at a distance. We would like to determine emperically what are the losses across a frequency sample (band); in this case, between 100 kHz and 100 MHz.

Using the hp[8601A](https://github.com/wireless-power-laboratory/hp8601a) Sweeper/Generator in _tracking generator mode_, one can observe the linearity of two 12.5mm-radius, 10-turn inductive-loop coils on a hp[141S](https://github.com/wireless-power-laboratory/hp141s) Spectrum Analyzer. Before we can do this, the hp8601A is set to run as a tracking generator by modifying the internals in such a way as to direct the `VTO` out and the `1st LO` in.

![8601-007](/img/8601-007.jpg)

Where the input for the `1st LO` will come as an output from the hp8553L RF Section plug-in for the hp141S Spectrum Analyzer. As the hp8601A OPT007 that has this particular feature is nearly impossible to find, I made the appropriate modifications according to the Service Manual. To note, the schematic shows a RF amplifier but I opted to test if the modification would work without as the amplifier is a passive type meaning it would only engage if following too low a power value (drift from the set power) adn not directly affecting the signal if it were to not be included. I tend to do this with Hewlett-Packard test equipment as, from experience, they are over-built rather than under-built. Draft testing showed the amplifier not required at the 8553L and there is enough signal strength to traverse a 3m cable between the hp8601A and the hp141S/8552A/8553L set perpendicular to one another.

![8553L](/img/8553-lo.jpg)

When using in a single-frequency setting, one can turn the knob on the hp8601A to change the output; 

![sweeper](/img/sweeper.jpg)

for the purposes of this experiment the entire range will be applied to the coils that are attached by a special cable to the BNC cables to each piece of test equipment.

![coupled-coils](/img/coupled-coils.jpg)

When powered-on, the following is displayed on the hp141S.

![linearity](/img/linearity.jpg)

Where one can see how the coupled-coil arrangement performs under the frequency range of interest.

### Analytical Result

Observing that the output power of the hp8601A is set to `-30 dbm` and the meter-trim set to `0` -- from the figure it reads `-2` meaning it _actually_ has an output value of `-32 dbm` -- this is the sweep power for every frequency sent across the band and is visible on the display. In order for the calibration _between_ the two pieces of test equipment, they should be set in a referential manner -- meaning the `LOG REF` setting on the hp8552A IF Section plug-in is also set to `-30 dbm`. Therefore, one can determine the linearity of the coupled-coils over the entire sweep.

100,000 - 100,000,000 | 50 graticules - `TODO: Write a mathematical expression`

On the spectum analyzer display screen, the dashed-line bisecting horizontally is the `-30 dbm` reference line, as it shares this with its internal calibration signal. The graticule indicators along the bottom are from low (the left) to high (the right) as this is in _tracking generator_ mode rather than _center frequency_ mode. What is the graticule to measure the result is the one traversing the center of the screen from `LIN` to `LOG`. By examination, one can see that the coil arrangement has a peak coupling (minimal loss) at the fourth graticule `2 MHz` then which slowly increases losses reaching is maximum value at the thirty-fifth graticule `75 MHz` at `-43 dbm`, then rises in efficiency to `-40 dbm` level at the end of the sweep. We could state that it would be most efficient to have the circuit perform at the `2 MHz` frequency indication.
