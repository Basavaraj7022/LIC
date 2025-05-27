# LIC-1
Question : Given that POWER, P=100µ W; Perform DC Analysis,transient and AC analysis for the specified circuit designs, as well as examining the effects of varying each mosfet's width;

# Design-1 :

   ![image](https://github.com/user-attachments/assets/9a8fab35-b076-453d-8c19-eeb2f14c3d76)


Using the Formula for Power, 

P=V*I

We will get the Values of Id as,

Id= 5.56 * 10^-5 A

we have to get the output current, Id for the given circuits by adjusting the values of L & W( Length and Width of the Channel of the MOSFET)

Length and Width of the Channel used to obtain the given Current is shown in the figure below;


1) DC ANALYSIS:

   Procedure for Performing DC Analysis:
   we have to select the dc output print(DC op pnt) in the Edit Simulation Command and Run the Simulation


   The Figure below shows the Values obtained from the DC Analysis : 

   ![image](https://github.com/user-attachments/assets/696cb4c4-e484-4fb0-b9ab-cf9ceaef2c8c)



2) Transient Analysis:

   Procedure for Performing Transient Analysis:
   we have to select the Transient Analysis in the Edit Simulation Command,  Give the stop time as 1ms and Run the Simulation.


   The Graphs below shows the Transient Response of the Given Design;

   ![image](https://github.com/user-attachments/assets/3e2f6c3e-e915-4dbc-aa56-36eaa5ec92e2)
   ![image](https://github.com/user-attachments/assets/c644c390-a82f-473c-9cb5-f333b28ba855)

   
3) AC Analysis:
   
   Procedure for Performing AC Analysis:
   we have to select the AC Analysis in the Edit Simulation Command,  Give the values as shown in the figure beowl and Run th Simulation.


   The Graph below shows the AC Analysis of the Given Design;

   ![image](https://github.com/user-attachments/assets/27252440-be1f-468b-8477-fc012b867090)



# RESULT:
 1) DC Analysis:
     1. The calculated drain current (Id) matches the expected value based on power and voltage, Id = 5.56*10^-5 A.
     2. By adjusting the MOSFET’s channel dimensions (L & W) where L=180nm and W= 203nm, The current requirement was succesfully achecived.
     3. The circuit behaves as expected under DC conditions.

 2) Transient Analysis:
     1. The transient response graph shows how the circuit behaves over time.
     2. The response is smooth, with no unexpected delays or distortions.
     3. The circuit reacts well to changes, confirming its stability.

 3) AC Analysis:
     1. The AC response graph confirms that the circuit remains stable at different frequencies.
     2. The gain(2 dB) and phase shift(which is nearly 180deg) align with theoretical expectations.
     3. The circuit maintains its performance across the tested frequency range.

# INFERENCE:
 1. The experiment confirms that selecting appropriate MOSFET dimensions effectively controls the drain current.  
2. Impact of Width Adjustments:  
3. M1 influences \(I_d\), indicating that its width affects the output current.  
4. The circuit performs reliably across all three analyses—DC, transient, and AC—demonstrating its stability.  
5. Overall, the design functions as expected, aligning with theoretical predictions and proving its practical feasibility.  


# Design-2

![image](https://github.com/user-attachments/assets/9fb14382-e1a6-4662-a5f5-48cc425f37aa)

Using the Formula for Power, 

P=V*I/n

We will get the Values of Id as,

Id= 5.56 * 10^-5 A

we have to get the output current, Id for the given circuits by adjusting the values of L & W of both the MOSFETS M1 & M2 ( Length and Width of the Channel of the MOSFET)
        
DC SWEEP Analysis: This analysis is done for obataing the value of Vin in Saturation range;

we have to select the DC SWEEP in the Edit Simulation Command,

The Graph below represents the VTC Curve and the value of the vin is selected as 0.7V as it is present in the saturation region of the VTC Curve

![image](https://github.com/user-attachments/assets/16b8364d-ffda-40e0-bb75-9e84942f9ae0)


Length and Width of the Channel of the two MOSFETS used to obtain the given Current is shown in the figure below;

![image](https://github.com/user-attachments/assets/dd6df468-7957-4602-bd00-801673f71ae5)
![image](https://github.com/user-attachments/assets/f2490db8-57c7-4949-9e67-ba6728b574c2)


Now we will be performing the DC, Transient and AC Anlaysis;

1) DC ANALYSIS:

   Procedure for Performing DC Analysis:
   we have to select the dc output print(DC op pnt) in the Edit Simulation Command and Run the Simulation

   The Figure below shows the Values obtained from the DC Analysis :

   ![image](https://github.com/user-attachments/assets/e159d32d-0495-4539-835a-ab8fb9b1c6d4)



2) Transient Analysis:

   Procedure for Performing Transient Analysis:
   we have to select the Transient Analysis in the Edit Simulation Command,  Give the stop time as 1ms and Run the Simulation.

   ![Screenshot 2025-02-16 130048](https://github.com/user-attachments/assets/c3faea32-8fd7-4cdb-9d7b-0b454f8d626b)

   The Graphs below shows the Transient Response of the Given Design;

  ![image](https://github.com/user-attachments/assets/70c99a18-0c4b-42de-8288-d95d9795932c)
  ![image](https://github.com/user-attachments/assets/1975eba0-4e02-4469-bb43-43d098f3aa52)



3) AC Analysis:
   
   Procedure for Performing AC Analysis:
   we have to select the AC Analysis in the Edit Simulation Command,  Give the values as shown in the figure beowl and Run th Simulation.

   ![image](https://github.com/user-attachments/assets/80e2d1d3-f2f6-4ce8-b26e-0a803006303a)

   The Graph below shows the AC Analysis of the Given Design;

   ![image](https://github.com/user-attachments/assets/12fadf99-8548-466c-8d8d-cb1cd62253b2)



# RESULT:
1. DC Analysis

   1. The computed drain current (Id) is 5.56*10^-5 A, which is in line with the expected value based on power and voltage.
   2. The intended current was obtained by adjusting the channel diameters (L & W) of both MOSFETs (M1 & M2), where M1: L = 180 nm, W = 1105 nm.
         2. M2: W = 1105 nm, L = 180 nm.      
   3. Within the chosen DC settings, the circuit functions as intended.


2.Transient Analysis:

   1. The transient response graph confirms that the circuit transitions smoothly over time.
   2. The circuit responds effectively to input variations, indicating stable operation.

3.AC Analysis:

   1. The AC response graph confirms that the circuit maintains stability over the tested frequency range.
   2. The gain(5.5 dB) and phase shift (which is nearly 180deg) align with theoretical expectations.
   3. The circuit functions as expected under AC conditions.

# Inference :
  1. The experiment confirms that the drain current may be accurately regulated by choosing the MOSFET dimensions (L & W) correctly.
  2. The proper operating voltage (0.7V) for saturation was chosen with the aid of the voltage transfer characteristics (VTC).
  3. Effect of Modifications to Width:
     
     1. Because M2 has a greater effect on Id, the output current is greatly impacted by its width.
     2. Because M1 has a smaller influence, changes in its breadth only slightly alter Id.
  4. The design demonstrates its viability in real-world applications by fulfilling the anticipated performance criteria and adhering to theoretical expectations.

