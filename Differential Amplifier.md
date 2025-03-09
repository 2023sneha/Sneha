## Experminet 3:- MOS Differential Amplifier
## AIM:Design and analyse the MOS differential amplifier circuit for the given specification.
VDD=3.3V

P<=3mW

Vicm=1.72V

Vocm=1.81V

Vp= 0.7V

## Perform DC analysis, transient analysis and frequency response and extract the required paramenters.

## Introduction
The DC analysis of a MOS differential amplifier establishes the transistors' operating point (bias conditions) by varying the input voltages and examining the resulting DC output voltages and currents.

The differential amplifier is a crucial analog circuit designed to amplify the voltage difference between two input signals while minimizing common-mode noise. This makes it essential for precision signal processing applications. This experiment aims to investigate key performance parameters, including differential-mode gain, common-mode gain, and the common-mode rejection ratio (CMRR), through practical measurements and detailed analysis of a constructed circuit. By conducting these tests, we will gain hands-on experience with the amplifier’s functionality and its importance in real-world applications.

The differential amplifier operates in two primary modes:

Common Mode: This mode considers the shared component of the two input signals, calculated as (V₁ + V₂) / 2. It represents the average voltage between the inputs.

Differential Mode: This mode focuses on the voltage difference between the two inputs, expressed as V₁ - V₂. This difference is typically the signal of interest in amplification applications.




## Circuit Diagram

![image](https://github.com/user-attachments/assets/30104f9d-82a7-45d0-8ee6-d6d8abc46d37)

## Working Principle of a MOS Differential Amplifier

1. Differential Input: The amplifier processes the voltage difference between two input signals, amplifying only the differential component while rejecting common-mode signals, which helps improve noise immunity.


2. Current Source Biasing: A stable current source supplies a constant bias current (Ib), ensuring consistent and predictable circuit operation.


3. Output Voltages: The amplified differential signal is present at the output terminals ( Vout+ and Vout-), where it can be further processed based on application needs.






Current Flow in the Circuit

The total drain current (ID1 + ID2) remains equal to the bias current (IB) at all times.

In an ideal condition where both transistors are perfectly matched and no differential input is applied, each MOSFET conducts exactly half of the bias current (IB).

When a differential input is introduced, one transistor's current increases while the other's decreases, but their sum remains unchanged, maintaining circuit stability.




Behavior in Saturation Mode

If the MOSFETs operate in the saturation region, their drain current follows the standard MOSFET current equation:


ID = 1/2 un Cox W/L (VGS - Vth)^2 (1 + lambda VDS)

Because the bias current (IB) is constant, the circuit automatically adjusts the source voltage to achieve a gate-to-source voltage (VGS) that results in the required drain current for proper operation.


## Procedure: Simulating a Differential Amplifier in LTSpice

1. Open LTSpice

Launch LTSpice and create a new schematic file to begin the simulation process.

2. Load the Required Library

Ensure accurate MOSFET simulations by importing the tsmc018.lib library, which contains models for TSMC 0.18µm (180nm) CMOS technology. The library file should be stored in the same directory as the LTSpice simulation file.

3. Add Circuit Components

Select and place the required components in the schematic:

M1 & M2 (CMOSN): Two NMOS transistors

R1, R2, RSS: Three resistors

VDD, V2, V3: Three voltage sources


Assign appropriate values to each component based on the design specifications.

4. Connect the Circuit

Wire the components together according to the differential amplifier schematic. Ensure correct connections between the transistors, resistors, and voltage sources.

5. Configure the Simulation Settings

Open the Simulate menu and select Edit Simulation Cmd.

Go to the DC op pnt (DC operating point) tab.


6. Perform DC Operating Point Analysis

Enable the option to compute the DC operating point.

Start the simulation by clicking Run to analyze the circuit's DC behavior.


7. Analyze the Simulation Results

## Design:
Given P<=3mW
**But we have considered P=2.5mW**
since P=VddxIss;

**Iss = P/Vdd = 2.5m/3.3 = 0.757mA**


**Id1=Id2=Iss/2 = 0.37mA**

By Applying KVL :

**Vdd-I1Rd-Vocm1=0**
3.3 - 0.37 Rd - 1.81 = 0
**Rd = 3.93kohm**

**Rss=Vp/Iss = 0.7/0.757m**

Rss=0.924kohm

### Circuit 1
![Screenshot 2025-03-09 175910](https://github.com/user-attachments/assets/19da8f18-ecaa-4531-8eb8-2c92e296a84a)

## DC Analysis:
The DC analysis of a MOS differential amplifier establishes the transistors' operating point (bias conditions) by varying the input voltages and examining the resulting DC output voltages and currents.
![Screenshot 2025-03-09 180533](https://github.com/user-attachments/assets/eeda1d9d-84a4-464f-8212-777a4e3db03f)
![Screenshot 2025-03-09 180634](https://github.com/user-attachments/assets/5022e6bc-3422-43cd-9feb-5fbd5678fd8e)

Length( M1 and M2) = 180nm

Width ( M1 and M2) = 2.0558um

for mosfet M1:

Vicm = 1.72V

Vocm = 1.81V

Id(M1) = 0.37mA

Vtn = 0.487V


VDD = IdRd + VDS +Vp

VDS = 3.3 - 1.454 - 0.7

VDS = 1.146V

for mosfet M2:

Vicm = 1.72V

Vocm = 1.81V

Id(M2) = 0.37mA

Vtn = 0.487V

VDD = IdRd + VDS +Vp

VDS = 3.3 - 1.454 - 0.7

VDS = 1.146V


The Q-points of both the mosfets(M1 and M2) are (1.146V, 0.37mA)

## Transient Analysis:
Transient analysis is used to simulate a circuit's behavior over time in response to dynamic inputs such as pulses, sine waves, or step signals.
This analysis is particularly crucial for high-speed applications, as it helps evaluate key parameters like rise time, fall time, and propagation delay,
which influence an amplifier’s capability to process fast signals. Additionally, it provides insight into how a MOSFET responds to sudden variations in input voltage and load conditions.


![Screenshot 2025-03-09 184903](https://github.com/user-attachments/assets/bf69358b-22af-4305-a2ed-ca330024b68b)



**Input waveform:**
![Screenshot 2025-03-09 185007](https://github.com/user-attachments/assets/91722de7-f1b2-413e-909f-937c623579eb)
**Output waveform:**
![Screenshot 2025-03-09 184927](https://github.com/user-attachments/assets/856f933a-50fb-414d-a10c-c38afd5b43ce)
**Input and Output Waveform**
![image](https://github.com/user-attachments/assets/515aac92-cc7e-4fd6-8a26-f11c5f1ece02)


From the graph ,we can observe the 180 degree phase shift in the output signal and the output voltage (at Vocm node) is amplified .

**Gain(Av) = Voutpeak/Vinpeak**

=1.875-1.7504/1.7705-1.6709  = 1.251V/V
**20log(1.251)dB =1.9451dB ** 

## AC Analysis

![image](https://github.com/user-attachments/assets/fa5163e4-e895-4aa8-85b8-0673373cb5f3)
![image](https://github.com/user-attachments/assets/b2753eb5-35d8-4d8c-9fcb-ce7751e23b68)

From the graph gain in dB scale is
20log(1.251)=1.9451dB



## Circuit 2
Replacing ( R3 ) with a current source ( Iss ) transforms the circuit into a fully differential pair with an active current source. This modification eliminates source degeneration, increasing the gain and improving common-mode rejection (CMRR). The current source ensures a stable bias current, making the circuit less sensitive to variations in component values. Without ( R3 ), the transconductance ( g_m ) is higher, resulting in a larger differential gain given by (Ad=gm*rd).


![image](https://github.com/user-attachments/assets/e157baa2-2d18-4038-8405-d9065f551b2b)

## DC Analysis

![image](https://github.com/user-attachments/assets/6ede87d0-5b55-469d-af39-61ab1ebc9572)

![image](https://github.com/user-attachments/assets/a5869d1f-b101-45f6-ad85-237277559344)


Mosfet aspect ratio was same ie, L= 180nm, W = 2.0553um

for mosfet M1 & M2:

Vicm = 1.72V

Vocm = 1.81V

Id= 0.37mA

Vtn = 0.487v

VDD = IdRd + VDS +Vp

VDS =3.3 - 1.454 - 0.7

VDS = 1.146 V

The Q-point of both the mosfets are (1.146V, 0.37mA).


## Transient Analysis

**Output Waveform**
![image](https://github.com/user-attachments/assets/45047349-ef07-4c27-88e1-19785e6bc0f3)

**Input Waveform**
![image](https://github.com/user-attachments/assets/2fbbb163-8677-49fd-8cd3-4506c0f74314)

**Input and Output Waveform**
![image](https://github.com/user-attachments/assets/ea1103aa-9621-490a-a058-2336c488b4b8)

From the above observation
Gain Av=Vout(peak)/Vin(peak)
Av= 0.3156/0.1004 = 3.143 V/V
Converting it to the decibel(dB):
20log(3.143) = 9.94 dB


## AC Analysis
![image](https://github.com/user-attachments/assets/23c89a63-4405-47c9-9db4-5ab71a96ab95)

From the graph gain in dB scale is
20log(3.143)=9.94dB


## Circuit 3
**Differential Amplifier with NMOS Current Source Biasing**

This circuit features an improved differential amplifier where the traditional tail resistor is replaced with an NMOS transistor (M3) functioning as a current source. This modification enhances the stability and control of the bias current in the differential pair (M1 and M2), resulting in a more consistent operating point and improved common-mode rejection.

By utilizing an active NMOS current source, the circuit achieves higher accuracy and stability in amplifying the difference between the input signals (V2 and V1). This method ensures better regulation of the bias current, which is crucial for applications demanding precise signal processing and strong resistance to common-mode noise. While maintaining its fundamental role of differential signal amplification, the circuit benefits from enhanced performance and reliability due to the active biasing approach.

## Circuit Diagram
![image](https://github.com/user-attachments/assets/97c1716e-bf98-4e86-9de6-abfdbd0546a7)

## DC Analysis
![image](https://github.com/user-attachments/assets/a83ad4ed-046e-45a9-8ab1-de3e000e6d14)
![image](https://github.com/user-attachments/assets/b088203d-4032-4b0e-a606-86d3ec1b895a)


Mosfet aspect ratio was same ie, L= 180nm, W = 2.0549um

for mosfet M1 & M2:

Vicm = 1.72V

Vocm = 1.81V

Id= 0.37mA

Vtn = 0.487v

VDD = IdRd + VDS +Vp

VDS =3.3 - 1.454 - 0.7

VDS = 1.146 V

The Q-point of both the mosfets are (1.146V, 0.37mA).


## Transient Analysis

**Output Waveform**
![image](https://github.com/user-attachments/assets/593d8860-09bd-4abd-aa47-bd9907e1ed00)

**Input Waveform**
![image](https://github.com/user-attachments/assets/49eca7d2-5ff6-4bf7-bf40-f0618cc88b45)

**Input and Output Waveform**
![image](https://github.com/user-attachments/assets/b544b301-a5e0-4fe2-8b7b-97e7464a64be)

From the above observation
Gain Av=Vout(peak)/Vin(peak)
Av= 0.3126/0.0974 = 3.209V/V
Converting it to the decibel(dB):
20log(3.209) = 10.127 dB


## AC Analysis
![image](https://github.com/user-attachments/assets/a51c2042-109f-43d2-a2a4-796efc51b5be)


From the graph gain in dB scale is
20log(3.209)=10.127dB

## Inference: Impact of Different Tail Current Sources in a Differential Amplifier

**With Resistor (Rss) as the Tail Current Source:**

**Moderate Differential Gain:**
The differential gain is restricted by the tail resistor (Rss) since the current through the differential pair is determined by the resistor’s value, limiting amplification.

**Reason:** A resistor does not actively regulate the tail current, so its resistance directly affects the amount of current flowing through the differential pair, thereby constraining the gain.

**Limited Output Voltage Swing:**
The voltage swing at the output is restricted due to the voltage drop across the tail resistor. As the output voltage moves closer to the supply voltage, the current through Rss decreases, reducing the available voltage range for the output.

**Reason:** The voltage drop across Rss reduces the supply voltage available for the output, thereby restricting how far the output can swing before reaching supply limits.

**Lower Common-Mode Rejection Ratio (CMRR):**
The CMRR is relatively low because the tail resistor presents a lower impedance, making the circuit more susceptible to common-mode signals.

**Reason:** The low impedance of Rss allows common-mode signals to influence both sides of the differential pair similarly, reducing the circuit’s ability to reject unwanted noise.


**With an Ideal Current Source (Iss) as the Tail Current Source:**

**Higher Differential Gain:**
A constant tail current improves differential gain by ensuring a steady current supply to the differential pair, leading to better signal amplification.

**Reason:** Since the tail current remains fixed, the differential pair operates more efficiently, resulting in greater amplification.

**Better Output Voltage Swing:**
An ideal current source eliminates the voltage drop issues seen with a resistor, allowing for a wider output voltage range.

**Reason:** Unlike a resistor, an ideal current source does not introduce a significant voltage drop, maximizing the available headroom for the output signal.

**Higher CMRR:**
The high impedance of an ideal current source enhances common-mode rejection, making the circuit less susceptible to external noise.

**Reason:** The high impedance prevents variations in the power supply or common-mode signals from affecting the tail current, improving the circuit’s ability to reject unwanted interference.


**With NMOS Transistor as the Tail Current Source:**

**Maximum Differential Gain:**
The NMOS transistor functions as an active current source with high impedance, providing superior stability and enabling the highest possible differential gain.

**Reason:** Since the NMOS current source actively regulates the tail current with minimal variation, the differential pair remains optimally biased, maximizing gain.

**Widest Output Voltage Swing:**
The NMOS current source reduces voltage losses in the tail, allowing for the largest possible output signal range.

**Reason:** Unlike a resistor, an NMOS-based current source has a lower voltage drop, preserving more of the supply voltage for output signal swing.

**Best Common-Mode Rejection Ratio (CMRR):**
The NMOS current source offers the highest impedance, leading to the most effective isolation from supply fluctuations and external noise.

**Reason:** The high impedance characteristic of the NMOS transistor ensures that the tail current remains stable, preventing common-mode signals from influencing the differential pair, resulting in superior noise rejection.

## Summary of Reasons:

**Resistor (Rss):**

Restricts current flow, limiting differential gain.

Causes a voltage drop, reducing output swing.

Has low impedance, making the circuit more susceptible to common-mode noise.


**Ideal Current Source:**

Supplies a constant tail current, improving gain.

Eliminates voltage drop issues, allowing for a wider output swing.

Has high impedance, enhancing common-mode rejection.


**NMOS Current Source:**

Functions as an active high-impedance source, optimizing differential gain.

Minimizes voltage loss, providing the widest output swing.

Offers superior isolation from interference, resulting in the highest CMRR.













