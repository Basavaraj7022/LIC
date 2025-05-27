#  Current Mirror Experiment

##  Introduction to Current Mirroring Circuits in Linear Integrated Circuits (LICs)

A **Current Mirror** is a fundamental building block in analog circuit design, particularly within **Linear Integrated Circuits (LICs)**. Its primary function is to **copy (or "mirror") a reference current** from one branch of a circuit to another with high accuracy. This technique ensures that the mirrored current remains consistent, **independent of supply voltage variations, load changes, or temperature fluctuations**.

---
![image](https://github.com/user-attachments/assets/59995b13-ed05-4924-af52-dd388bdd6e5e)


##  How It Works

Current mirrors operate by exploiting the characteristics of **active devices** like **BJTs (Bipolar Junction Transistors)** or **MOSFETs (Metal-Oxide-Semiconductor Field-Effect Transistors)**. The basic structure typically consists of two or more transistors with their **bases/gates connected together**, and one of them configured to **sense a reference current**. The remaining transistor(s) then **reproduce this current** in their collector/drain branches.

- In **BJT-based mirrors**, the collector current depends exponentially on the base-emitter voltage (V_BE).
- In **MOSFET-based mirrors**, operation is based on the square-law behavior of MOSFETs in saturation.

---
##Circuit diagram
![image](https://github.com/user-attachments/assets/3b155032-8727-493e-85e9-6f6c45c028f8)

## Design Question

<p>Design a current mirror circuit which has a gain of AV = -10V/V, power supply of Vdd = 1.8V, and power of P <= 1mW. Find reference current (Iref), output current (Id), and total current (Itotal). Perform DC and AC analysis for mirror ratio 1:1, 1:2.</p>

## Design
-  The MOSFET should be in saturation region 
<table>
<td>V1>V<sub>th</sub></td>
</table>
i.e 0.5>0.366
 
  -  I<sub>taotal</sub>=P/V<sub>dd</sub>
<table>
<td>I<sub>total</sub>=0.55mA</td>
</table>
I<sub>total</sub>=I<sub>ref</sub> + I<sub>p</sub>
I<sub>ref</sub>=I<sub>p</sub>=(I<sub>total</sub>)/2
<table>
<td>I<sub>ref</sub>=I<sub>p</sub>=0.27mA</td>
</table>

## Case 1: L = 180 nm
## Simulation Outcones

This document presents the simulation results for the current mirror circuit with different L (length) values of MOSFETs. The simulation was conducted for three cases with varying L values.
![image](https://github.com/user-attachments/assets/438e0969-2afc-4820-8f90-1fcfd3321efe)

## Case 2: L = 500 nm
### Analysis
- **Observation 1**: W = 2.38u.
- **Observation 2**: W/L ratio of M1 and M2 transistors are maintained same .
- ![image](https://github.com/user-attachments/assets/90ae5f45-21d6-44ee-a9bf-0082e5508729)

### Analysis
- **Observation 1**: W = 6.0649u
- **Observation 2**: W/L ratio of M1 and M2 transistors are maintained same i,e 1:1 .

## Case 3: L = 1 µm
### Simulation Output
![image](https://github.com/user-attachments/assets/304ead32-018f-461c-bdc9-5c21acabc633)

  ## Special Case: W/L Ratio of M1:M2 = 1:2
### Simulation Output
![image](https://github.com/user-attachments/assets/d95482ae-a1bb-4832-93af-c4020acd51e5)

### Analysis
- **Observation 1**: Width is kept at 180nm and length were M1:M2 = 2.38u:4.76u
- **Observation 2**: W/L ratio of M1 and M2 transistors are maintained same i,e 1:2 .

- ## Transient analysis 
### SIMULATION OUTPUT
![image](https://github.com/user-attachments/assets/e4ce02c5-2dc6-4dcd-bcb0-e7cc8466e8b3)

- **Observation** MaxOutSwing =  1.175V<sub>p-p</sub> 
## AC ANALYSIS
### SIMULATION OUTPUT
![image](https://github.com/user-attachments/assets/ef23c67a-edec-4111-a012-f0003d5d8f76)

## CIRCUIT DIAGRAM 2
![image](https://github.com/user-attachments/assets/e1688f59-ca14-4ac5-b5c7-5285a065970d)

### DC ANALYSIS 
![image](https://github.com/user-attachments/assets/71fb9a82-a34a-4392-ae32-378b93f1e4e6)

- **Observation** We can observe that current accross M6 and M3 transistors are almost double because of 1:2 W/L ratio 

- **Observation** We can observe that current accross M5 and M4 transistors are same because of 1:1 W/L ratio 

### AC ANALYSIS 
![image](https://github.com/user-attachments/assets/9dc68fb7-937f-45ea-b3de-04196fecdf58)

- **Observation** B<sub>w</sub>=1.94G<sub>Hz</sub>

##  Key Features of Current Mirrors

-  **Current Replication**: Accurately copies a reference current to another part of the circuit.
-  **Voltage Independence**: Output current remains relatively unaffected by output voltage changes.
-  **Temperature Stability**: With proper design, current mirrors can exhibit good thermal stability.
-  **Scalability**: Output current can be a scaled version of the reference current (I_out = n × I_ref).
-  **Low Component Count**: Typically implemented with just two or more matched transistors.

---

##  Applications of Current Mirrors

Current mirrors are widely utilized in various analog and mixed-signal designs, including:

-  **Biasing Circuits**: Provides stable bias current to amplifier stages.
-  **Active Loads**: Used as a high-impedance load in amplifiers to improve gain.
-  **Current Amplifiers**: Mirrors can scale and replicate currents for amplification purposes.
-  **Analog Signal Processing**: Found in differential amplifiers, operational transconductance amplifiers (OTAs), etc.
-  **Voltage Regulators & Power Management ICs**: Ensure constant current sources and load regulation.

