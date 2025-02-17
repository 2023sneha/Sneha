# Sneha
# LINEAR INTEGRATED CIRCUITS
# Experiment 1
# Dc,Transient and AC Analysis of Common Source Amplifier using MOSFET
# INTRODUCTION
A Common Source (CS) amplifier using MOSFET is widely used for amplification.
1. DC Analysis: Finds the operating point (Q-point) by setting proper biasing to keep the MOSFET in saturation.

2. Transient Analysis: Studies the time response to input signals, crucial for switching and pulse response.

3. AC Analysis: Examines small-signal gain, input/output impedance, and frequency response using the small-signal model.

A MOSFET is a type of transistor used for amplifying or switching electronic signals. It is widely used in digital and analog circuits due to its high efficiency and fast switching speed.

In saturation mode, an NMOS transistor operates under the conditions:

Vgs > Vth (Gate-to-Source Voltage greater than Threshold Voltage)
Vds ≥ Vov (Drain-to-Source Voltage greater than Overdrive Voltage)
The current equation in saturation mode is given by Id = (1/2) kn Vov², where:

Vov = Vgs - Vth
The voltage gain is given by: Av = -gm RdorAv = Vout/Vin

A MOSFET in saturation and acts as a constant current source, making it useful for amplifier circuits.

Drain current equation: *Id = (1/2) kn Vov², where *Vov = Vgs - Vth.
The amplifier gain follows Av = -gm Rd.

# Components Required
NMOS Transistor : M1

Resistor : R1 1K ohm

Power Supply : V1 1.8V for DC Supply

Input Signal Source : V2 0.9V signal input
# Circuit Diagram
![Screenshot 2025-02-17 165839](https://github.com/user-attachments/assets/7288202d-dcc9-4d18-b716-29c0d3fcd9bf)
# Components Details
TSMCO18 library was included which is crucial for accurate MOSFET simulation in 180nm CMOS technology
Here NMOS transistor must operate in saturation region for amplification.
Lenght L = 250nm

Width W = 0.05um

Threshold Voltage(Vin) = 0.366V

Resistor R1 = 1K ohm

Supply Voltage = 1.8V

Input AC signal : *DC Voltage:0.9V*Amplitude:50mV*Frequency:1KHz.
# DC Analysis 
The required current for the given power values to operate mosfet in satuturation region is 27.772 micro ampers, since only w and l can be varied to get the desired current so their values are:
![Screenshot 2025-02-17 165304](https://github.com/user-attachments/assets/08e8fdaa-b415-4bd9-981b-a532027a210d) 

Length L = 250nm

Width W = 0.05um

Results: 
Vdd = 1.8V

Vin = 0.9V

Vout = 1.77V

Id = 27.772uA

Ig = 0A

# Transient Analysis
A sinusoidal input signal of 0.9V peak-to-peak is applied to the gate, and the output voltage is observed at the drain and it has a 180-degree phase shift between input and output.
![Screenshot 2025-02-17 165544](https://github.com/user-attachments/assets/6d1e8ad1-a7e6-4742-bc02-fa53f91b19b9) 
Vout = 1.7730V
# AC Analysis
AC analysis evaluates the frequency response of a common-source NMOS amplifier. The gain is plotted over a wide frequency range to observe how the circuit amplifies signals at different frequencies and determine its bandwidth limitations.
![Screenshot 2025-02-17 165719](https://github.com/user-attachments/assets/12c78491-06a8-49a4-9d53-04e14121b87e) 
The gain remains stable at lower frequencies.
The amplifier’s bandwidth and highlights its frequency-dependent performance.
