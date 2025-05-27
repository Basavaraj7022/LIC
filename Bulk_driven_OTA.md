# Bulk-Driven Operational Transconductance Amplifier (OTA)

This repository contains LTspice simulation files and documentation for a **Bulk-Driven OTA** optimized for **low-power** and **low-voltage** analog applications such as biomedical and IoT interfaces.

---

## Features

- **Low Supply Voltage**: 0.8V to 1.2V
- **Open Loop Gain**: ~40–60 dB
- **Power Consumption**: Very Low
- **Bandwidth**: 50 MHz
- **Technology**: Bulk-Driven MOSFET design
- **Applications**: Biomedical front-end, low-power analog blocks

---

## Tools Required

- LTspice (recommended) or any SPICE simulator (e.g., Ngspice, PSpice)

---

## How to Run

1. Open `bulk_ota.asc` in LTspice.
2. Run **Transient** and **AC Analysis**.
3. Observe open loop gain, phase margin, and bandwidth.

---

## Authors

- **B Manikanta** — [2023ec_bmanikanta_a@nie.ac.in](mailto:2023ec_bmanikanta_a@nie.ac.in)
- **Basavaraj K C** — [2023ec_basavarajkallappachikki_a@nie.ac.in](mailto:2023ec_basavarajkallappachikki_a@nie.ac.in)

---

# Design Specifications for Bulk-Driven OTA

## Objective

> Design a Bulk-Driven OTA optimized for low-voltage and low-power analog applications.

---

### Key Parameters

| Parameter                | Value                      |
|--------------------------|----------------------------|
| Supply Voltage (Vdd)     | 0.8V – 1.2V                |
| Open Loop Gain           | ~40–60 dB                  |
| Bandwidth                | 50 MHz                     |
| Transconductance (gm)    | Controlled via bulk terminal|
| Power Consumption        | Very Low                   |

---

## Circuit Description

- **Input Stage:** Bulk-driven PMOS differential pair
- **Load:** NMOS current mirror active load
- **Biasing:** Golden current mirror reference
- **Output:** Single-ended
- **Compensation:** Miller Capacitance (Cc) for pole splitting

---

## Stability Enhancement

Miller compensation shifts the dominant pole to ensure phase margin and stable operation across frequency.


---

## Circuit Simulation Results

> **Add your simulation screenshots and design diagrams here.**
>![image](https://github.com/user-attachments/assets/596465d9-e51c-482f-9dba-0fe9094925e9)

---
 ## Simulation Results
 ## INPUT:
 ![image](https://github.com/user-attachments/assets/853e4bd7-1a1e-4eea-9e62-a944a912181c)

## Transient alalysis
![image](https://github.com/user-attachments/assets/57e493ab-9c3f-4571-ac44-63470a2c5cd9)

## Output
![image](https://github.com/user-attachments/assets/8e26da18-13dd-4eed-8e62-7057f3e5f9ed)

## Applications

Bulk-Driven OTAs are used in a variety of modern analog and mixed-signal circuits, especially where ultra-low voltage and low power are critical:

- **Biomedical Instrumentation**: ECG, EEG, and other biosignal amplifiers for wearable or implantable devices.
- **IoT and Sensor Interfaces**: Analog front-ends for sensor nodes operating under tight energy budgets.
- **Portable and Battery-Operated Devices**: Hearing aids, fitness trackers, and portable medical devices.
- **Analog Signal Processing**: Active filters, oscillators, sample-and-hold circuits.
- **Switched-Capacitor Circuits**: Building block for low-voltage ADCs/DACs.
- **Neural Signal Acquisition**: For brain-computer interface and neural prosthetics.
- **Energy Harvesting Systems**: Signal conditioning in systems powered by harvested energy.
- **Low-Voltage Data Converters**: Front-ends for ADCs operating below 1V.
 ## Inference

The design and simulation results of the Bulk-Driven Operational Transconductance Amplifier (OTA) demonstrate its suitability for modern low-voltage, low-power analog applications. The bulk-driven approach allows the OTA to operate reliably at supply voltages as low as 0.8V, making it ideal for battery-powered and energy-constrained environments such as biomedical devices and IoT sensor interfaces.

The simulated open-loop gain in the range of 40–60 dB ensures adequate amplification for weak biosignals, while the high bandwidth (~50 MHz) supports applications requiring fast signal processing. The use of a Miller compensation technique effectively improves the phase margin and overall stability, as observed in the transient and AC analysis plots.

Furthermore, the low power consumption makes the design highly efficient for continuous long-term operation in portable and wearable devices. The versatility of the bulk-driven OTA, as reflected in its ability to serve as an analog front-end in biomedical instrumentation, sensor interfaces, and low-voltage data converters, highlights its importance in advancing ultra-low-power analog circuit design.

In summary, the Bulk-Driven OTA meets the key objectives of low-voltage operation, low power consumption, and satisfactory gain-bandwidth, making it a promising candidate for next-generation analog and mixed-signal systems.

