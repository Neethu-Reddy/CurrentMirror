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

![image](https://github.com/user-attachments/assets/167561c9-0a57-4d65-a12b-2ca899f4a9aa)



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

**DC Analysis**

**Case1: L=180nm**

![image](https://github.com/user-attachments/assets/a1535d9c-6d99-4b9c-ba5f-d2426fd1cf0a)

PMOSFET = length is 180nm, width is 10um<br>
NMOSFET = length is 180nm, width is 114.025um<br>
Vout= 0.967276V<br>
Vx= 0.967276V<br>
Iref = 0.277mA<br>

**Case2: L=500nm**

![image](https://github.com/user-attachments/assets/354efa5e-5c73-4d02-8e1d-c088b09389ce)

PMOSFET = length is 500nm, width is 10um<br>
NMOSFET = length is 500nm, width is 207.617um<br>
Vout= 0.644713V<br>
Vx= 0.644703V<br>
Iref = 0.277mA<br>

**Case3: L=1um**

![image](https://github.com/user-attachments/assets/64cc84bd-2a38-4fa7-b661-7cb1085f037a)

PMOSFET = length is 1um, width is 10um<br>
NMOSFET = length is 1um, width is 251.54um<br>
Vout= 0.293193V<br>
Vx= 0.293177V<br>
Iref = 0.277mA<br>

### Tabular column:
|  Length  |            Width           |   V<sub>x</sub>  | V<sub>out</sub>  |   I<sub>ref</sub>|
|----------|----------------------------|------------------|------------------|------------------|
|   180nm  | Pmos= 10u; Nmos=114.025u   |    0.967276V     |     0.967276V    |    0.277mA       |
|   500nm  | Pmos= 10u; Nmos=207.617u   |    0.644703V     |     0.644713V    |    0.277mA       |
|    1um   | Pmos= 10u; Nmos=251.54u    |    0.293177V     |     0.293193V    |    0.277mA       |


### Transient analysis:
1.Case 1: 180nm
![Image](https://github.com/user-attachments/assets/893a38ab-0455-4193-8bb9-052746ef2e42)
* Peak to Peak volatge = 1.934V
* Maximum output swing = Vdd-Vov2+Vov3 = 1.8-(-0.00847-0.36)+(0.5-0.36)= 2.29V

<br>

2.Case 2: 500nm
![Image](https://github.com/user-attachments/assets/8786450e-c70e-4efd-8edf-bf6ba5d635ee)
* Peak to Peak volatge = 1.28V
* Maximum output swing = Vdd-Vov2+Vov3 = 1.8-(-0.00000907-0.36)+(0.5-0.36)= 2.29V

<br>

3.Case 3: 1um
![Image](https://github.com/user-attachments/assets/e58a1237-fc27-4672-a463-ea0b2869f16f)
* Peak to Peak volatge = 0.607V
* Maximum output swing = Vdd-Vov2+Vov3 = 1.8-(0.0000165-0.36)+(0.5-0.36)= 2.29V

<br>

**AC Analysis**

**Case1: L=180nm**

![image](https://github.com/user-attachments/assets/e65eaa39-9538-4e5a-871b-2ca23bd946be)

**Case2: L=500nm**

![image](https://github.com/user-attachments/assets/705948fc-6a9c-4c6f-ba5c-ef047f418ec7)

**Case3: L=1um**

![image](https://github.com/user-attachments/assets/bf1c3c97-b19d-421f-bf7b-ecfe5a889c9d)

### Tabular column:
|  Length  |  3dB Gain   |  3dB Bandwidth   | 
|----------|-------------|------------------|
|   180nm  |    27dB     |   265.185MHz     |
|   500nm  |    36dB     |   52.4645MHz     |     
|    1um   |    35.75dB  |   39.4948MHz     |   

### Inference:
* Reference current is copied or mirrored for other two mosfets.The output currentis exactly equal to the reference current.
* The output current remains the same regardless of the connected load, as long as the transistor stays in the saturation region
* V<sub>x</sub> and V<sub>out</sub> will be same when current gets mirrored.
* As length increases V<sub>x</sub> and V<sub>out</sub> decreases.
* As gain increases bandwidth decreases.
* As the refence current is 0.277mA and doing 1:1 ratio of current mirroring the Current must be copied of the same that is 0.277mA.
* In transient analysis we see the maximum output swing caused.
  
<br>

**Case 2** : 1:2 Current mirror

**Circuit Diagram**

![image](https://github.com/user-attachments/assets/b01a18f4-acf8-4eed-89cd-59b2a3a33c39)




### Components :
PMOSFET-2, NMOSFET- 1, supply volatage-2, current source-1.

### Procedure:

1. Build the circuit as per the circuit diagram using LTspice.
2. Set the Vdd as 1.8V.
3. Download the library file.
4. Create a folder. Save the library file and LTspice file to the folder.
5. Import the library file to LTspice using spice directive(.op).
6. Find the current value for the given power rating.
7.  Set the mosfet model name CMOSN for NMOSFET and CMOSP for PMOSFET as given in the library file, length as 180nm and vary the width  of NMOSFET till you get the exact Q point. Set the gate volatge of NMOSFET as 0.5V. 
8. DC analysis: In edit simulation option, change to dc offset to get list of values obtained from the circuit. We should get the calculated current value in the simulation result.So that we need to vary the value of width since width is directly proportional to Drain current(Id) keeping other parameters constant. Since we are doing current mirroring the current of both mosfets should be same as the reference current even the output also should match too. 
9. Transient analysis: In edit simulation option, change from dc offset to transient. Set the dc offset as 0.5V, Amplitude 5mV, frequency 1KHz. Keep stop time for 3ms and run to get the expected waveform.Find the maximum output swing.
10. AC analysis : In edit simulation option, change from transient to ac analysis. Set type of sweep as decade, number of points per decade as 20, start and stop frequency as 0.1Hz and 1THz to get the expected ac waveform. Note down the 3dB gain of the circuit and its bandwidth.

<br>

### Calculations:
* Power <= 1mW
* Vdd = 1.8V
* I<sub>total</sub> = power/Vdd = 1mW/1.8 = 55.5mA
* I<sub>D</sub>= I<sub>total</sub>/3 = 0.185mA.
* 1:2 ratio = 0.185mA : 0.37mA.

<br>

**DC Analysis**

**Case1: L=180nm**

![image](https://github.com/user-attachments/assets/67e85fca-e352-426f-95a9-46577e0b2540)

PMOS1 : L=180nm ; W=70um 
PMOS2 : L=180nm ; W=140um 
NMOS11 = L=180nm ; W=135.867um
Vout= 1.20094V
Vx= 1.20934V
Iref = 0.185mA

<br>






































