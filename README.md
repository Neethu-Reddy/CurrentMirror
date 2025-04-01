# CurrentMirror
## Introduction
A current mirror is a circuit designed to copy (mirror) a reference current from one branch of the circuit to another, ensuring that the output current remains constant regardless of voltage variations. This is essential for maintaining stable operation in analog circuits, particularly in integrated circuits (ICs).
A current mirror consists of at least two transistors (usually bipolar junction transistors (BJTs) or metal-oxide-semiconductor field-effect transistors (MOSFETs)) arranged in such a way that the current flowing through one transistor (the reference transistor) is mirrored by the other transistor(s) (the output transistor(s)).
A MOSFET current mirror works similarly to a BJT current mirror. However, instead of the base-emitter voltage, the MOSFET current mirror relies on the gate-source voltage (Vgs) to establish the current. The gate-source voltage of both MOSFETs in the mirror is set equal, and by matching their dimensions and ensuring proper biasing, the output current in the mirrored transistor will be a copy of the reference current.

![image](https://github.com/user-attachments/assets/fe619bac-b7ae-45a6-b93d-66df66f62341)

For MOSFETs, the gate and drain of the first transistor are connected together, and the gates of both transistors are connected. This ensures that the gate-source voltage of both transistors is the same, leading to the same drain current (assuming the transistors are identical).

By neglecting the channel length modulation of the two transistors the drain currents can be given as :<br>

I<sub>REF</sub> = K'<sub>n</sub>Cox (VGS - V TH)2<br>

and<br>

I<sub>out</sub> = mn Cox (VGS - V TH)2<br>

If we take ratio of two equations, we get<br>

I<sub>ref</sub>=I<sub>out</sub>

**Advantages of Current Mirrors:**<br>

**Stable Biasing**: Provides consistent and accurate bias currents<br>
**Improved Performance**: Enhances gain, stability, and bandwidth of amplifiers<br>
**Power Efficiency**: Reduces power consumption compared to resistor biasing<br>
**Temperature Compensation**: Ensures reliable operation over a wide temperature range<br>
**Scalability**: Easily scalable to multiple output branches<br>

## Aim : Design and Analyze Current mirror circuit as active load in amplifier circuit.

Given :

Vdd=1.8 V.<br>
P <=1 mW.<br>
Av>-10 V/V.<br>

## Circuit Diagram



**Calculation**:

Drain current equation is given by:

ID = (1/2)μnCox(W/L)(VGS - Vth)^2<br>
ITotal = P / VDD<br>
ITotal = Iref + Ix<br>
For 1:1 ratio Iref = Ix<br>
Iref(2) = ITotal<br>
Iref = ITotal/2<br>
ITotal = 1 mW/1.8 V<br>
ITotal = 0.555 mA<br>
Iref = 0.555 m/2<br>
Therefore, Iref = 0.2777 mA.<br>

**Case 1** : 1:1 Current mirror

**1) L=180nm**














