# EXPERIMENT 3 - DIIFRENTIAL AMPLIFIER 
AIM: To analyze and design the DC,AC,Transient analysis of Common Source NMOS Amplifier
# Introduction:
It is the basic configuration of the MOSFET(Metal oxide semiconductor field effective transistor) where the input is given to the gate terminal and output is driven form the drain terminal and the source is grounded .This amplifier will give the significant gain which is ideally 1 and this amplifier will act as the buffer amplifier which as 180 degree phase shift. DC Analysis is used to determine the Q point in such a way that the transistor is operating in the saturtaion region. The AC analysis is used to determine the gain, amplifiers frequency response and the bandwidth of the amplifier.

# Design Question
Design differential amplifier for the following specifications
____
|Parameters |Vdd| P | Vicm | Vocm | Vp |
| ------------- | ------------- |
|Secifications| 2.5V| <=3MW | 1.3V| 1.4V | 0.5V|
___




Perform DC analysis transient analysis and frequency response and extract the required parameters


# Theory
A Differential Amplifier is an funadamental electronic circuit designed to amplify the difference between the two input signals while rejecting an Common-Mode signals that are present on the both input signals. This characteristic makes it highly effective in applications requiring noise reduction. The Differential amplifier typically consists of a pair of transistors configured in a symmetrical manner,allowing it to obtain high common-mode rejection ratio(CMMR)

# Circuit - 1 [With Rss]
![Screenshot 2025-03-13 213355](https://github.com/user-attachments/assets/d8c766b4-bff3-4a75-b58a-6d59264301fb)


# Design 

* Assume M1 and M2 are perfectly identical
* Vicm1 = Vicm2 = Vicm
* RD1 = RD2 = RD
* ID1 = ID2 = Iss/2
* VGS1 = VGS2 =VGS
* Vocm1 = Vocm2 = Vocm = 1.4V
 <br> Vicm = Vp + VGS </br>
       1.3 = 0.5 + VGS </br>
       1.3-0.5 = VGS </br>
       <table>
       <td>V<sub>GS</sub> = 0.8V</td>
       </table>
- we can conclude that VGS >= Vth , M1 and M2 are in ON state
- Given P = 3mW we can calucalate Iss
- Iss = P/VDD
- Iss = 3mW/2.5V
- Iss = 1.2mA
- we known that ID = Iss/2
       <table>
       <td>I<sub>D</sub> = 1.2mA</td>
       </table>
- Rss = Vp/I<sub>ss</sub> = 0.5/1.2m
    <table>
     <td>R<sub>ss</sub> = 0.416K</td>
     </table>
- V<sub>ocm</sub> = V<sub>DD</sub> - I<sub>D</sub>*R<sub>D</sub>
- R<sub>D</sub> = (V<sub>DD</sub> - V<sub>ocm</sub>)/I<sub>D</sub>
  - R<sub>D</sub> = (2.5 - 1.4)/0.6m
   <table>
     <td>R<sub>D</sub> = 1.833K</td>
     </table>
- we can conclude V<sub>ocm</sub> >= V<sub>GS</sub> - V<sub>th</sub>
   - V<sub>ocm</sub> = 0.8 - 0.36
   <table>
       <td>V<sub>ocm</sub> >= 0.44V</td>
      </table>
<br>Therefore M1 and M2 are in saturation region</br>
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

**Comparision based on the obtained Values**
  
  <table>
    <tr>
      <td>Parameters</td>
      <td> Calculated</td>
      <td>Circuit 1 (with R<sub>ss</sub>)</td>
      <td>Circuit 2 (with constant current source)</td>
      <td>Circuit 3 (with NMOS)</td>
      <td>Observation</td>
    </tr>
    <tr>
      <td>V<sub>icm</sub></td>
      <td>1.3V</td>
      <td> 1.3V</td>
      <td>1.3V</td>
      <td>1.3V</td>
      <td>As per the design </td>
    </tr>
    <tr>
      <td>V<sub>ocm</sub></td>
      <td> 1.4V</td>
      <td>1.4V</td>
       <td>1.402V</td>
        <td>1.4V</td>
        <td><p>Its as per the simulation , if we want to raise  the V<sub>ocm</sub> then  we need to decrease R<sub>D</sub> or I<sub>D</sub> , if we need to decrease the V<sub>ocm</sub> then either we need to **increase R<sub>D</sub> or I<sub>D</sub></p></td>
    </tr>
    <tr>
      <td>V<sub>p</sub></td>
      <td>0.5V</td>
      <td>0.5V</td>
      <td>0.501V</td>
      <td>0.50V</td>
      <td><p>It's Nodal  Voltage </p></td>
    </tr>
    <tr>
      <td>I<sub>D</sub></td>
      <td>0.6mA</td>
      <td>0.601mA</td>
      <td>0.6mA</td>
      <td>0.601mA</td>
      <td>If I<sub>D</sub> has to be incresed then we need to increase the width of the MOSFET and vice-versa.
      </td>
    </tr>
    <tr>
      <td>I<sub>ss</sub></td>
      <td>1.2mA</td>
      <td>1.202mA</td>
      <td>1.2mA</td>
      <td>1.202mA</td>
      <td>It's the total current flowing in the differential amplifier and its also called as <em>Tail Current</em></td>
    </tr>
    <tr>
      <td>R<sub>D</sub>
      <td>1.83KΩ</td>
      <td>1.83kΩ</td>
      <td>1.83KΩ</td>
      <td>1.83kΩ</td>
      <td>AS we need to set the V<sub>ocm</sub> as per that the R<sub>D</sub> values has Changed.</td>
    </tr>
    <tr>
      <td>g<sub>m</sub></td>
      <td>2.77mS</td>
      <td>2.47mS</td>
      <td>2.47mS</td>
      <td>3.3551mS</td>
      <td><p>From calculation the g<sub>m</sub>has been decreased due to differ in the V<sub>th</sub> value.The g<sub>m</sub> value has been increased due to decrease in the V<sub>ov</sub></p></td>
    </tr>
    <tr>
      <td>A<sub>vdm</td>
        <td>-4.99V/V</td>
        <td>-4.528 V/V</td>
        <td> -4.528 V/V</td>
        <td> -4.528 V/V</td>
        <td><p>Value extracted from the graph </p></td>
    </tr>
        <tr>
          <td>Gain in dB scale(20log(A<sub>vdm</sub>) </td>
          <td>13.96dB</td>
          <td>13.18dB</td>
          <td>13.18dB</td>
          <td>15.76dB</td>
          <td>We can see variation because the gain has been increased</td>
        </tr>
        <tr>
          <td>Bandwidth</td>
          <td>-</td>
          <td>19.433GHz</td>
          <td>19.433GHz</td>
          <td>21.56GHz</td>
          <td><p> When compare to Resistor and constant current source the Mosfet Bandwidth has been increased because the MOSFET's high input impedance it reduces the loading effect, allowing for a wider range of frequencies to get amplified without any signal distortion. </p></td>
        </tr>
         </table>






  
