Since we are a pure hardware project, the only software involve in our project is LTspice, which is analog electronic circuit simulator produced by Analog Device and it can be downloaded from [LTspice download](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).

For beginner, a detailed tutorial can be found [tutorial link](https://www.analog.com/en/education/education-library/videos/video-series/ltspice-getting-started-tutorial.html).

## Brief Tutorial
After downloading the LTspice, you can create a new schematic by opening it up and choosing to start a new, blank schematic. The next step is placing components. From the toolbar, you can place any components you want and place it on the schematic. By using command+R (mac) or ctrl+R (window), you can rotate the components to coordinate with your circuit. After placing the components you need, you will need to give value based such as resistance and capacitance. If you need to use transistors, you should also pick the type. LTspice has a few built in transistors such as 2N2222 or PN4416. Any other transistors can be found online by simply searching for its product name and "spice model". Then we can go to the website and copy the model. In LTspice, we can add the spice model by editing the SPICE directive and change the transistor to the specific type we want. After placing all the components and giving them values, you need to wire all the components together. The last step is to run the simulation by clicking the run button and setting the analysis type and its parameters. Then you will be able to see the output of your circuit.

## Improved Schematic
There are five circuit files to simulate in LTSpice for this project:

1. Active Antenna
2. Isolation Amplifier
3. Tracking Filter
4. Triode Mixer
5. Combined System (Antenna, Isolation Amplifier, Tracking Filter, and Triode Mixer)

All the circuits are improved version. The original circuit schematics can be downloaded from [betterbots](http://www.betterbots.com/). 

By downloading them, you can open them up in LTspice. Then click the **run** button, you will see the output of each circuits. 

## Analysis Type in LTspice
LTspice offers a few different analysis types such as transient, AC analysis, DC analysis. In our project, we mainly used AC analysis because we are improving an AM radio system and AC analysis is aim to analyzing the frequency response. AC analysis can be used to calculate the gain, phase shift, and frequency response and the output is also shown in the bode plot. AC analysis have multiple scaling: liner, octave, and decade. Each one provides a different number of simulation points and setting frequency. Decade scaling (dec) is our major choice. One decade is equivalent to a ratio of 10. We also used DC analysis in order to get the voltage level and current at different position of the circuit. Since for most of the circuits, we are using transistors thus we always expect the emitter voltage to be smaller than the power voltage and prevent the transistor from saturating. By using the DC analysis, we are able to find the emitter voltage and then we can compare it with the actual value to check if our circuit is built properly. Transient analysis is used when we want to compare the ideal signal with the actual prototype output. Transient analysis is a time domain analysis that shows the output of the behavior over time. Since the time domain is also usually shown in the oscilloscope, we always use transient analysis for output comparison. From the comparison, we can tell whether the circuit works properly or if there is any clipping or noise caused by other components of the circuits.

# LTSpice set up for each circuit
After watching the tutorials we provided in an earlier section, we assume that the user will have the ability to simulate and choose components from the LTSpice, the following will be just a guide on which simulation commands the user necessary to run for each circuit.

## Active Antenna Spice Guide

The active antenna schematic is shown in the figure below:

![image](https://user-images.githubusercontent.com/98863790/235391792-e42ed6e1-e10f-4022-b5ba-1897ad460bd8.png)

The active antenna will only use AC simulation, more specific down below:

![image](https://user-images.githubusercontent.com/98863790/235392040-710a7fa3-0821-48cf-8684-cbcfc8d4ad14.png)



