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

## Simulation Outcones

This document presents the simulation results for the current mirror circuit with different L (length) values of MOSFETs. The simulation was conducted for three cases with varying L values.

## Case 1: L = 180 nm

### Simulation Output
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

