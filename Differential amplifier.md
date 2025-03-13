# EXPERIMENT 3 - DIFRENTIAL AMPLIFIER 
AIM: The DC analysis determines the Q-point to ensure the MOSFET operates in saturation. AC and transient analysis evaluate gain, frequency response, bandwidth, and time-domain behavior for signal amplification.
# Introduction:
The common source MOSFET amplifier is a widely used circuit in analog electronics, mainly for signal amplification. In this configuration, the input signal is applied to the gate terminal, the output is taken from the drain, and the source is connected to the ground. This amplifier provides a considerable voltage gain and introduces a 180-degree phase shift between the input and output signals, meaning an increase in input voltage results in a decrease in output voltage.

To ensure the MOSFET operates in the saturation region, DC analysis is performed to determine the quiescent point (Q-point). Proper biasing is necessary to keep the transistor in the desired operating region, preventing it from entering cutoff or triode regions, which would affect amplification. 

For small-signal operation, AC analysis is carried out to determine the voltage gain, input and output impedance, and frequency response of the amplifier. The frequency response helps in analyzing the bandwidth, ensuring the circuit amplifies signals effectively within a specific range. Factors like Miller capacitance and parasitic capacitances must be considered, especially at high frequencies, as they can affect gain and stability. 

This type of amplifier is commonly used in RF circuits, audio amplification, and signal processing applications where moderate gain and phase inversion are required. Proper component selection and biasing help in optimizing its performance for different applications.
# Design Question
Design differential amplifier for the following specifications
| Parameters    | Vdd  | P      | Vicm  | Vocm  | Vp   |
|--------------|------|--------|-------|-------|------|
| Specifications | 2.5V | ≤3MW   | 1.3V  | 1.4V  | 0.5V |




Perform DC analysis transient analysis and frequency response and extract the required parameters


# Theory
A differential amplifier is a fundamental electronic circuit designed to amplify the difference between two input signals while rejecting any common-mode signals present on both inputs. This makes it highly effective in applications where noise reduction is important, as it minimizes interference from external sources like power supply fluctuations and electromagnetic noise. 

It typically consists of a pair of transistors arranged symmetrically, ensuring balanced operation and a high common-mode rejection ratio (CMRR). A high CMRR allows the circuit to suppress unwanted noise and interference, making it useful for precision measurements, sensor signal processing, and communication systems.

Differential amplifiers can be built using either bipolar junction transistors (BJTs) or MOSFETs, depending on the application and performance requirements. They are commonly used as the input stage in operational amplifiers due to their good linearity and stability. To achieve proper operation, they require biasing through current sources, resistor networks, or active loads. More advanced designs use current mirrors or cascode configurations to improve gain and bandwidth.

These amplifiers play a crucial role in instrumentation systems, audio processing, analog-to-digital conversion, and wireless communication. Their ability to reject common-mode noise while amplifying differential signals makes them essential in high-precision and low-noise electronic circuits.
# Circuit - 1 [With Rss]
![Screenshot 2025-03-13 213355](https://github.com/user-attachments/assets/d8c766b4-bff3-4a75-b58a-6d59264301fb)


# Design 

Assuming M1 and M2 are perfectly identical, the common-mode input voltages are equal, i.e., \( V_{icm1} = V_{icm2} = V_{icm} \), and the drain resistances are also identical, \( R_{D1} = R_{D2} = R_D \). The drain currents of both transistors are given by \( I_{D1} = I_{D2} = I_{ss}/2 \), and the gate-to-source voltages are the same, \( V_{GS1} = V_{GS2} = V_{GS} \). The common-mode output voltage is \( V_{ocm1} = V_{ocm2} = V_{ocm} = 1.4V \). The relationship between the common-mode input voltage and threshold voltage is given by \( V_{icm} = V_p + V_{GS} \), which leads to \( 1.3V = 0.5V + V_{GS} \), resulting in \( V_{GS} = 0.8V \). Since \( V_{GS} \geq V_{th} \), we can conclude that both transistors M1 and M2 are in the ON state.

Given the power dissipation \( P = 3mW \) and supply voltage \( V_{DD} = 2.5V \), the tail current \( I_{ss} \) is calculated as \( I_{ss} = P / V_{DD} = 3mW / 2.5V = 1.2mA \). Since \( I_D = I_{ss}/2 \), we get \( I_D = 0.6mA \). The source resistance is given by \( R_{ss} = V_p / I_{ss} = 0.5V / 1.2mA = 0.416K\Omega \). The output common-mode voltage is given by \( V_{ocm} = V_{DD} - I_D R_D \), and solving for \( R_D \), we get \( R_D = (V_{DD} - V_{ocm}) / I_D = (2.5V - 1.4V) / 0.6mA = 1.833K\Omega \). Finally, since \( V_{ocm} \geq V_{GS} - V_{th} \), substituting values, we get \( V_{ocm} = 0.8V - 0.36V = 0.44V \), which satisfies the condition. Therefore, we can conclude that both transistors M1 and M2 are operating in the saturation region.



**DC ANALYSIS:-**
![screen2](https://github.com/user-attachments/assets/e223f16d-af1d-453a-9624-6cfb43b06f81)


 - simulation
      
      ![Image](https://github.com/user-attachments/assets/5019afc3-c582-403e-b1ae-2bf3fe4e3e52)
   - we can verify by the graph
   - the wave is starting from 1.325V and reached till 2.498V
   - therefore 2.948 - 1.325 = 1.173V which is equal to the calculated value V<sub>ocm</sub>maxswing.
  
**Range of an V<sub>icm</sub>**
 <table>
    <td>V<sub>GS1</sub> + Vp <= V<sub>icm</sub> <= min(V<sub>DD</sub> - (I<sub>D</sub>*R<sub>D</sub>) + V<sub>th</sub> , V<sub>DD</sub>(when one mosfet is off))</td>
  </table>
      
- **AC Analysis:**
  - we got A<sub>v</sub> = -4.99V/V
  - A<sub>vdB</sub> = 20log(A<sub>v</sub>)
  - A<sub>vdB</sub> = 20log(4.99)
  <table>
    <td>A<sub>vdB</sub> = 13.96 dB</td>
  </table>
  - we need to calculate 3dB gain
  - 3dB gain = A<sub>vdB</sub> - 3dB
  - 3dB gain = 13.96 - 3
  <table>
    <td>3dB gain = 10.96 ~ 11dB</td>
  </table>
- Simulation
  
 ![WhatsApp Image 2025-03-09 at 00 21 23_6c2f6d5c](https://github.com/user-attachments/assets/cceec6b9-44fa-4f8a-8594-ccac206e1eaf)

- From the graph the gain is 13.180 dB
- The 3 dB bandwidth will be 19.433 GHz

# CIRCUIT 2 - [**WITH CURRENT SOURCE**]
![Screenshot 2025-03-13 195834](https://github.com/user-attachments/assets/335ccaef-b8c7-40ac-b3a3-9c301454d8b6)


For the same design value 

**A**] DC ANALYSIS

![image](https://github.com/user-attachments/assets/462722d7-c2df-43b6-aa93-8e1ca87fa3e1)


**B**] TRANSIENT ANALYSIS

![WhatsApp Image 2025-03-09 at 00 55 13_99e31b9e](https://github.com/user-attachments/assets/35b9397f-1c2f-421b-8e20-1af11b6cba26)

- A<sub>vdm</sub> = 452.87mV/100mV
     <table>
     <td>A<sub>vdm</sub> = 4.528V/V</td>
     </table>

**3**] AC ANALYSIS

![WhatsApp Image 2025-03-09 at 11 43 31_774a873a](https://github.com/user-attachments/assets/cf5ad73b-5449-460a-bd9f-8774684c802b)

-  From the graph the gain is 13.180 dB
- The 3 dB bandwidth will be 19.433 GHz

# CIRCUIT-3 [**WITH MOSFET**]

![Screenshot 2025-03-13 191824](https://github.com/user-attachments/assets/955ce4aa-4583-4b13-b5ab-6ed505e53386)



- In this circuit we need to desing the Basing Voltage V<sub>b</sub>.
- For MOSFET 3 to operate in the saturation region.
   - V<sub>GD</sub> <= V<sub>th</sub>
   - V<sub>G</sub> - V<sub>D</sub> = V<sub>th</sub>
   - V<sub>b</sub> = V<sub>th</sub> + V<sub>p</sub>
   - V<sub>b</sub> = 0.366 + 0.5
     <table>
      <td>V<sub>b</sub> = 0.866V </td>
    </table> 
    - from this we can coclude that MOSFET M3 is in saturation region which it can act has constant current source 
    - When we perform DC analysis to check the parameters values we got :-
    
![Screenshot 2025-03-13 213737](https://github.com/user-attachments/assets/23d6474a-7587-470b-a816-9afcbad59db8)



  **Trasient Analysis**

  ![WhatsApp Image 2025-03-09 at 11 46 03_7bc8070e](https://github.com/user-attachments/assets/a2bce1ed-e9be-47b0-9609-18d346fa62b9)

  **AC Analysis**
- We have obtained gain from above analysis i.e 4.54V/V
- contvert to dB scale = 20log(A<sub>vdm</sub>)
- dB = 20log(4.54)
<table>
  <td>dB value is 13.14dB</td>
</table>
  - lets verify this with the graph
  
 ![WhatsApp Image 2025-03-09 at 11 49 26_84d08d63](https://github.com/user-attachments/assets/55a0d690-1db5-4575-9d8c-e3aea016f790)

  3dB will be 12.76dB
  3dB bandwidth will be 21.56 GHz

    ## Result

| Parameters                  | Calculated | Circuit 1 (with R<sub>ss</sub>) | Circuit 2 (with constant current source) | Circuit 3 (with NMOS) | Observation                                                                                             |
|-----------------------------|------------|---------------------------------|------------------------------------------|-----------------------|---------------------------------------------------------------------------------------------------------|
| V<sub>icm</sub>             | 1.3V       | 1.3V                           | 1.3V                                    | 1.3V                  | As per the design                                                                                      |
| V<sub>ocm</sub>             | 1.4V       | 1.4V                           | 1.402V                                  | 1.4V                  | Its as per the simulation, if we want to raise the V<sub>ocm</sub> then we need to decrease R<sub>D</sub> or I<sub>D</sub>, if we need to decrease the V<sub>ocm</sub> then either we need to **increase R<sub>D</sub> or I<sub>D</sub>** |
| V<sub>p</sub>               | 0.5V       | 0.5V                           | 0.501V                                  | 0.50V                 | It's Nodal Voltage                                                                                     |
| I<sub>D</sub>               | 0.6mA      | 0.601mA                        | 0.6mA                                   | 0.601mA               | If I<sub>D</sub> has to be increased then we need to increase the width of the MOSFET and vice-versa.  |
| I<sub>ss</sub>              | 1.2mA      | 1.202mA                        | 1.2mA                                   | 1.202mA               | It's the total current flowing in the differential amplifier and its also called as *Tail Current*     |
| R<sub>D</sub>               | 1.83KΩ     | 1.83kΩ                         | 1.83KΩ                                  | 1.83kΩ                | AS we need to set the V<sub>ocm</sub> as per that the R<sub>D</sub> values has Changed.                |
| g<sub>m</sub>               | 2.77mS     | 2.47mS                         | 2.47mS                                  | 3.3551mS              | From calculation the g<sub>m</sub> has been decreased due to differ in the V<sub>th</sub> value. The g<sub>m</sub> value has been increased due to decrease in the V<sub>ov</sub> |
| A<sub>vdm</sub>             | -4.99V/V   | -4.528 V/V                     | -4.528 V/V                              | -4.528 V/V            | Value extracted from the graph                                                                         |
| Gain in dB scale (20log(A<sub>vdm</sub>)) | 13.96dB | 13.18dB                   | 13.18dB                                 | 15.76dB               | We can see variation because the gain has been increased                                               |
| Bandwidth                   | -          | 19.433GHz                      | 19.433GHz                               | 21.56GHz              | When compare to Resistor and constant current source the Mosfet Bandwidth has been increased because the MOSFET's high input impedance it reduces the loading effect, allowing for a wider range of frequencies to get amplified without any signal distortion. |





  
