# Monostable Multivibrator using 555 Timer IC

##  Aim

To design a circuit using a **555 Timer IC in monostable mode** that generates a **single output pulse** of **0.5 milliseconds** duration upon receiving a trigger signal.

---

##  Theory

A **monostable multivibrator** has:
- **One stable state (LOW)**.
- **One temporary state (HIGH)**.

When a **trigger signal** (negative pulse) is applied:
- The output becomes **HIGH** for a precise time `T`.
- After time `T`, the output returns to **LOW**, waiting for the next trigger.

The duration of the HIGH output (`T`) is determined by:
T = 1.1 × R × C
Where:
- `T` = Output pulse duration in seconds
- `R` = Resistance in ohms (Ω)
- `C` = Capacitance in farads (F)

This configuration is used in:
- Delay circuits
- Pulse generators
- Debouncing mechanical switches

---

##  Working Principle

1. **Default Output**: The 555 timer output is **LOW**.
2. **Triggering**: When a **negative pulse** is applied to **pin 2**, the timer output becomes **HIGH**.
3. **Timing Phase**: The capacitor starts charging through the resistor.
4. **Threshold Level**: Once capacitor voltage reaches **2/3 of Vcc**, the timer resets the output to **LOW**.
5. **Auto Reset**: The capacitor discharges internally, and the circuit waits for the next trigger.

Output time duration:
T = 1.1 × R × C

---
## Output


##  Calculation

**Given:**
- Desired output pulse time, `T = 0.5 ms = 0.0005 s`
- Capacitance, `C = 1 µF = 0.000001 F`

**Required:**
R = T / (1.1 × C)

**Calculation:**
R = 0.0005 / (1.1 × 0.000001)
R = 454.54 Ω

**Standard Resistor Used:**

---

##  Components Required

| Component        | Value        | Quantity |
|------------------|--------------|----------|
| 555 Timer IC      | -            | 1        |
| Resistor          | 455 Ω        | 1        |
| Capacitor         | 1 µF         | 1        |
| Push Button       | -            | 1        |
| Power Supply      | 5V or 9V DC  | 1        |
| Breadboard & Wires| -            | As needed|

---

##  Procedure

1. **Build the Circuit**  
   - Connect the 555 timer in monostable configuration:
     - **Pin 1** → GND  
     - **Pin 2** → Trigger (push button or signal generator)  
     - **Pin 3** → Output  
     - **Pin 4** → Vcc (via pull-up or directly to Vcc)  
     - **Pin 5** → 10nF to GND (optional for noise immunity)  
     - **Pin 6** → Connect to Pin 7  
     - **Pin 7** → Connect to resistor `R`, then to Vcc  
     - **Pin 8** → Vcc  
     - **Between Pin 6/7 and GND**, connect capacitor `C`

2. **Choose Component Values**  
   - Use **R = 455 Ω**, **C = 1 µF** to achieve **T = 0.5 ms**.

3. **Trigger the Timer**  
   - Press the push button or use a signal generator to apply a **negative pulse** to **pin 2**.

4. **Observe Output Pulse**  
   - Use an oscilloscope or logic analyzer to measure **output at pin 3**.

5. **Verify Output Duration**  
   - Confirm that the output pulse duration is **approximately 0.5 ms**.

---
## output: 

![WhatsApp Image 2025-05-27 at 15 04 34_a8a4eb54](https://github.com/user-attachments/assets/4a4cae07-1c10-40d4-b728-7d5534fff296)


##  Applications

- Timer circuits
- Pulse width shaping
- One-shot triggering
- Switch debouncing
- Frequency divider

---




