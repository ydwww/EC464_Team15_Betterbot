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

The active antenna will only use AC simulation, the command is shown below:

![image](https://user-images.githubusercontent.com/98863790/235392040-710a7fa3-0821-48cf-8684-cbcfc8d4ad14.png)

After the user runs the simulation, right click on the output of the antenna, the following bode plot of the antenna will display:

![image](https://user-images.githubusercontent.com/98863790/235392148-1baf566c-9203-4a24-9968-a5b03f882baa.png)

## Isolation Amplifier

The improved isolation Amplifier schematic is shown in the figure below:

![image](https://user-images.githubusercontent.com/98863790/235392525-c0bc67cb-1988-4587-b19e-03c763931657.png)

The isolation amplfiier will use AC, Noise, and Transient Analysis as part of the project.

To begin with The AC analysis will show the gain of the amplifier, the command of the AC analysis is shown below:

![image](https://user-images.githubusercontent.com/98863790/235392728-9c222fa6-4f20-4456-8b2f-1b2849c4f1e2.png)

After the user simulates the circuit, left click on the output of the amplifier where the node label as (o), the following bode plot should show up:

![image](https://user-images.githubusercontent.com/98863790/235393047-93238f70-d5be-4a10-b4df-43f00745b3fc.png)

The second command will be the noise simulation, the command of the noise simulation is shown below:

![image](https://user-images.githubusercontent.com/98863790/235393405-1d1df9a9-fce1-4571-8af9-ce8723937a39.png)

After the user simulates the circuit, right click on the output screen and find add trace and select gain and vinose then click ok to see the output:

![image](https://user-images.githubusercontent.com/98863790/235393572-2adabc09-4914-440f-a6bd-822f4fd6466b.png)
![image](https://user-images.githubusercontent.com/98863790/235393707-f236b857-085c-4ce2-bc3c-8f9fddbe2923.png)
![image](https://user-images.githubusercontent.com/98863790/235393749-2d47875a-8011-4321-a7bb-c23be9cf8874.png)

The third command will require a current input source (remove AC voltage source and replace it with a current source (set the ac value to 1)) for example:

![image](https://user-images.githubusercontent.com/98863790/235393988-d505fefe-4534-44ed-962f-2a3fa2fe94bd.png)

The purpose of this simulation is to check the input impedence of the circuit.

The command and simulation output is shown below (to obtain the proper input impedance output, the user shown right click on the input section/node):

![image](https://user-images.githubusercontent.com/98863790/235394205-0171ca88-ae96-4dc6-a9c1-43eb7d0b8e36.png)
![image](https://user-images.githubusercontent.com/98863790/235394392-9ba96947-166b-4635-b01a-53781192a0dd.png)

## Tracking Filter

The improved tracking filter schematic is shown below:

## Triode Mixer

The improved triode mixere schematic is shown below:

![image](https://user-images.githubusercontent.com/98863790/235394937-3e620f4b-e5f0-42c0-93a5-c7b5e437ec20.png)

The triode mixer will use transient analysis and FFT as part of the project, after simulating the transient anaylsis, left click on the output of the mixer, and right click on the output screen find FFT, the FFT will show the intermediate frequency.

![image](https://user-images.githubusercontent.com/98863790/235395525-d429e01f-2ca1-43f6-af32-a5b240e55644.png)
![image](https://user-images.githubusercontent.com/98863790/235395759-f323c1db-92af-4b21-9ef0-78142b325ae8.png)
![image](https://user-images.githubusercontent.com/98863790/235395829-e2e5731c-6157-4e66-87e9-9bf583c4902b.png)








