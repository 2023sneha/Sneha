# Sneha
# Circuit Diagram
![Screenshot 2025-02-17 165839](https://github.com/user-attachments/assets/7288202d-dcc9-4d18-b716-29c0d3fcd9bf)
# DC Analysis 
![Screenshot 2025-02-17 165304](https://github.com/user-attachments/assets/08e8fdaa-b415-4bd9-981b-a532027a210d)
# Transient Analysis
![Screenshot 2025-02-17 165544](https://github.com/user-attachments/assets/6d1e8ad1-a7e6-4742-bc02-fa53f91b19b9)
# AC Analysis
![Screenshot 2025-02-17 165719](https://github.com/user-attachments/assets/12c78491-06a8-49a4-9d53-04e14121b87e)
Linear Integrated Circuits 
AIM:
Specifications: 180 nm, tsmc, VDD = 1.8 V, Power budget = 50 uW
Analysis: DC analysis, Transient analysis, AC analysis
Experiment 1
CS amplifier analysis with resistive load
Components required
NMOS Transistors: M1 (nmos-4).
Resistors: R1 (1K ohm).
Power Supply: Vdd (1.8V) for DC supply.
Input Signal Source: Vin (0.9V) signal input.
Circuit diagram overview
Transistor Setup:
M1 (NMOS) as the main amplifying transistor.
Gate of M1 is connected to the input node Vin.
Source of M1 connected to the ground.
Drain of M1 connected to the resistor.
Biasing:
Vin provides the input signal.
Load resistor:
one terminal of resistor is connected to the drain of M1 and the other to Vdd.
DC analysis
The required current for the given power values to operate mosfet in satuturation region is 27.772 micro ampers, since only w and l can be varied to get the desired current so their values are

L=

W=

Results
Vdd=1.8V

Vin=0.9V

Vout=1.77223V

Id(M1)=27.772uA
Transient analysis
A sinusoidal input signal of 0.9V peak-to-peak is applied to the gate, and the output voltage is observed at the drain
Results
An interveting output curve was obtained when Vin and Vout was plotted against voltage and time with 1ms cycle. here we can observe a rough 180 degree phase shift between input and output.
AC analysis
This AC analysis evaluates the frequency response of a common-source NMOS amplifier. The gain is plotted over a wide frequency range to observe how the circuit amplifies signals at different frequencies and determine its bandwidth limitations.

Results
The gain remains stable at lower frequencies.

The amplifier’s bandwidth and highlights its frequency-dependent performance.
