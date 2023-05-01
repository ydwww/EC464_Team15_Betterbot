#Active Antenna

The following figure illustrates the schematic active antenna circuit, powered up by a 3.3V DC source. The circuit consists of two stages. The first stage utilizes a BF256B JFET emitter follower with a voltage divider at the base to regulate the voltage at Output1 and prevent the JFET from saturating. The second stage of the circuit is a PN2222A BJT emitter follower to achieve a low output impedance. Since the spectrum analyzer only has a low input impedance of 50 ohms, a large output impedance is added between the circuit and spectrum analyzer during signal analysis to prevent damage to the spectrum analyzer.

