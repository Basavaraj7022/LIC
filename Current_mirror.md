#  Current Mirror Experiment

##  Introduction to Current Mirroring Circuits in Linear Integrated Circuits (LICs)

A **Current Mirror** is a fundamental building block in analog circuit design, particularly within **Linear Integrated Circuits (LICs)**. Its primary function is to **copy (or "mirror") a reference current** from one branch of a circuit to another with high accuracy. This technique ensures that the mirrored current remains consistent, **independent of supply voltage variations, load changes, or temperature fluctuations**.

---

##  How It Works

Current mirrors operate by exploiting the characteristics of **active devices** like **BJTs (Bipolar Junction Transistors)** or **MOSFETs (Metal-Oxide-Semiconductor Field-Effect Transistors)**. The basic structure typically consists of two or more transistors with their **bases/gates connected together**, and one of them configured to **sense a reference current**. The remaining transistor(s) then **reproduce this current** in their collector/drain branches.

- In **BJT-based mirrors**, the collector current depends exponentially on the base-emitter voltage (V_BE).
- In **MOSFET-based mirrors**, operation is based on the square-law behavior of MOSFETs in saturation.

---

##  Key Features of Current Mirrors

-  **Current Replication**: Accurately copies a reference current to another part of the circuit.
-  **Voltage Independence**: Output current remains relatively unaffected by output voltage changes.
-  **Temperature Stability**: With proper design, current mirrors can exhibit good thermal stability.
-  **Scalability**: Output current can be a scaled version of the reference current (I_out = n × I_ref).
-  **Low Component Count**: Typically implemented with just two or more matched transistors.

---

## 📈 Applications of Current Mirrors

Current mirrors are widely utilized in various analog and mixed-signal designs, including:

-  **Biasing Circuits**: Provides stable bias current to amplifier stages.
-  **Active Loads**: Used as a high-impedance load in amplifiers to improve gain.
-  **Current Amplifiers**: Mirrors can scale and replicate currents for amplification purposes.
-  **Analog Signal Processing**: Found in differential amplifiers, operational transconductance amplifiers (OTAs), etc.
-  **Voltage Regulators & Power Management ICs**: Ensure constant current sources and load regulation.

---

##  Example: Basic BJT Current Mirror Circuit

```text
       Vcc
        |
        |
       Rc
        |
        |      B
      |/ C
 Iref --> Q1
      |\ E
        |
        |-----------------
                          |
                        |/ C
                  Iout --> Q2
                        |\ E
                          |
                         GND
