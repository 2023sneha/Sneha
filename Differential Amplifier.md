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

Vtn = 

VGS = 

VDD = IdRd + VDS +Vp

VDS = 3.3 - 1.454 - 0.7

VDS = 1.146V

for mosfet M2:

Vicm = 1.72V

Vocm = 1.81V

Id(M2) = 0.37mA

Vtn = 

VGS = 

VDD = IdRd + VDS +Vp

VDS = 3.3 - 1.454 - 0.7

VDS = 1.146V

To verify the mosfets are in saturation region : VGD <= VTn





Therefore mosfets are in saturation region .

The Q-points of both the mosfets(M1 and M2) are (1.146V, 0.37mA)

## Transient Analysis:
transient analysis is used to simulate a circuit's behavior over time in response to dynamic inputs such as pulses, sine waves, or step signals.
This analysis is particularly crucial for high-speed applications, as it helps evaluate key parameters like rise time, fall time, and propagation delay,
which influence an amplifier’s capability to process fast signals. Additionally, it provides insight into how a MOSFET responds to sudden variations in input voltage and load conditions.





