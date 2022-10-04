![Screenshot from 2022-08-15 17-17-44](https://user-images.githubusercontent.com/69398841/184629923-4325bf41-9446-4510-a93a-1fa72bdca850.png)

# Static-Timing-Analysis
Static timing analysis (STA) is a method of validating the timing performance of a design by checking all possible paths for timing violations. STA breaks a design down into timing paths, calculates the signal propagation delay along each path, and checks for violations of timing constraints inside the design and at the input/output interface.

## Timing Path

![image](https://user-images.githubusercontent.com/110079770/190552665-bf99cee6-aba9-40b2-a0a8-101de7b8d329.png)

## Example Of Timing Paths

![image](https://user-images.githubusercontent.com/110079770/190560524-e101803d-cb67-4fc0-9532-a50b12e61c36.png)

## Types Of Checks to be Performed 

## Types Of Setup/Hold Analysis 

![image](https://user-images.githubusercontent.com/110079770/190888247-335fa2a4-0370-498c-a171-d0b9fdbfb558.png)

## Slew/Transition Analysis
 
``` 
Two Types Slew/Transition Analysis.
1)Data(max/min)
2)clock(max/min)

```

## Load Analysis

```
Two Types Of Load Analysis
1)Fanout(max/main)
2)Capacitance(max/min)
```

![image](https://user-images.githubusercontent.com/110079770/190888536-3eb65ad6-2489-4fc1-8686-4ec74db1e40d.png)


## Clock Analysis
```
Two Types of Clock Analysis
1)Skew : Difference between the latencies (L1,L2,L3,L4 etc.,) are refferred to as skew.
2)Pulse Width : This type of analysis is performed due to the clock tree network that has parasitic elements in the clock network path we need to see upto which point the pulse width gets degraded to.

```

### Types of Analysis to be performed in Static Timing Analysis

![image](https://user-images.githubusercontent.com/110079770/190888864-7ccf1b68-cd84-4078-8af2-c052c35e5c7e.png)





#### Slack 

<b> Slack : </b> Difference between arrival time and require time <br>

`Slack(S) = RAT - AAT`

-> <I> Max Slack (Setup Timing, Setup Slack, Setup Analysis) : </I> The difference between expected maximum require time and actual arrival time. <br>

-> <I> Min Slack (Hold Timing, Hold Slack, Hold Analysis) : </I> The difference between actual arrival time and expected minimum require time. <br>


<ins> Example 1</ins> :

![image](https://user-images.githubusercontent.com/62461290/190431165-83bc4713-2b6a-4beb-a17d-6944258c8ff2.png) <br>

`Max Slack = 3ns - 3.5ns = -0.5ns`

![image](https://user-images.githubusercontent.com/62461290/190429835-58719349-dfe6-4a48-a97c-cd1403a7c864.png)<br>

`Min Slack = 3.5ns - 0.5ns = 3ns`

<ins> Example 2</ins> :

![image](https://user-images.githubusercontent.com/62461290/190434143-0b421273-c59b-4926-bf26-92e58ae02069.png) <br>

`Max Slack = 1ns - 0.2ns = 0.8ns`

![image](https://user-images.githubusercontent.com/62461290/190433799-0e17d633-518c-44a7-b92f-8fd36a6d680e.png) <br>

`Min slack = 0.2ns - 0.3ns = -0.1ns`

### Types of Analysis

<p align="center">
<img src="https://user-images.githubusercontent.com/62461290/190980344-a74f3bf0-1482-4a42-9ba3-78c0564f12f2.png">
</p>

<b> Types of setup/hold analysis : </b>

1. <I> reg2reg : </I> Any path that starts at a register and end at a register is called reg2reg path. <br>

![image](https://user-images.githubusercontent.com/62461290/190436869-395360d3-37b5-4490-9248-dcd04471b026.png)<br>

2. <I> in2reg : </I> Any path that starts at a input port and end at a register is called in2reg path. <br>

![image](https://user-images.githubusercontent.com/62461290/190437220-79303d9c-c41b-4827-bef4-67d121b2abcf.png)<br>

3. <I> reg2out : </I> Any path that starts at a register and end at a output port is called out2reg path. <br>

![image](https://user-images.githubusercontent.com/62461290/190437614-f1ee053b-1de1-49eb-9b53-bb2f3cc50eb9.png)<br>

4. <I> in2out : </I> Any path that starts at a input port and end at a output port is called out2reg path. <br>

![image](https://user-images.githubusercontent.com/62461290/190438268-c83677a9-b361-4253-ad3e-5931937d5b50.png)<br>

5. <I> clock gating : </I> Path that starts from clock and ends at and gate output is called clock gating timing path. <br>

![image](https://user-images.githubusercontent.com/62461290/190438984-51a8ecc5-a45a-4987-8ea3-be1bcf47cd6e.png)<br>

6. <I> recovery/removal : </I> Path between clock of flipflop that is driving reset pin to the reset pin is called recovery/removal path. <br>

![image](https://user-images.githubusercontent.com/62461290/190439696-dd8d1c9a-2378-4633-8740-46456a9e12fa.png) <br>


7. <I> data-to-data : </I> The requirement of a to arrive a particular point and ctrl to arrive at a different point. <br>

![image](https://user-images.githubusercontent.com/62461290/190460805-258982bf-a65f-4618-8e0d-864ea31e4745.png)<br>

`Latch is level triggered and flop is edge triggered` <br>

8. <I> Latch timings : </I> it either gives time or borrows times in the circuit. <br>

Flipflop borrows time from latch. <br>
![image](https://user-images.githubusercontent.com/62461290/190462109-b07a16c3-417e-467d-897b-3314a3adbefb.png)

Latch give time to the flipflop <br>
![image](https://user-images.githubusercontent.com/62461290/190461805-737c19f3-34ec-4feb-a131-90b444e59f46.png)<br>

#### Slew/Transition Analysis

Slew/Transition should cover between a minimum and maximum value. It mainly controls the power of the circuit.

<b> Types of slew/transition analysis : </b>

* <I> Data (max/min) : </I>

![image](https://user-images.githubusercontent.com/62461290/190467735-0c3eec71-6df3-46c5-9595-34d08bc3eda4.png) <br>

* <I> Clock (max/min) : </I>

![image](https://user-images.githubusercontent.com/62461290/190467955-2c211a54-1f08-4a78-a116-da218d337e46.png) <br>

#### Load Analysis

Analyses the charge and discharge of the amount of load. <br>

* <I> FanOut (max/min) </I> <br>
* <I> Capacitance (max/min) </I> <br>

#### Clock Analysis

* <I> Skew : </I> Latency difference between L1, L2, L3, L4. <br>

![image](https://user-images.githubusercontent.com/62461290/190468861-b79cae1c-5f51-4728-aa3b-ca8b91b99b0d.png) <br>

* <I> Pulse Width : </I> Analysis on the best possible fit for the pulse width. <br>

![image](https://user-images.githubusercontent.com/62461290/190469402-ff5fc3a0-d3fa-4979-976e-40db0b754897.png) <br>


## Section 2: Introduction to timing graph

`Specifications: Clock Frequency(F) = 1GHz, Clock Period(T)=1/F=1ns`
### reg2reg setup (max) analysis - Single Clock

<b> Combination logic delay : </b>

Cell delays, wire delays, signal arrival time at inputs in real scenarios are usually in ps.<br>

![image](https://user-images.githubusercontent.com/62461290/190559641-3c6e7240-8499-4338-a27e-e4e723d25307.png) <br>

Convert the above circuit to a 'Direct Acyclic Graph (DAG)' shown below:
 
 ![image](https://user-images.githubusercontent.com/62461290/190561519-9900cb60-fac0-40dc-8793-090623fa42be.png) <br>
 
* <I> Actual Arrival Time (AAT) </I> = Time at any node where we see latest transition after first rise clock edge. (Worst if a node has multiple paths)<br>

![image](https://user-images.githubusercontent.com/62461290/190631553-4fc605de-dcea-48ff-8055-2b58623d9d98.png) <br>

* <I> Required Arrival Time (RAT) </I> = Time at any node where we expect latest transition within clock cycle. (Best if a node has multiple paths) <br>

![image](https://user-images.githubusercontent.com/62461290/190632660-ebadfa91-3233-445f-a4b6-ac2bb111d5f2.png) <br>

AAT is expected to be less than RAT at every node for meeting design expectations. <br>

* <I> Slack </I> = Required arrival time - Actual arrival time <br>

![image](https://user-images.githubusercontent.com/62461290/190657779-a50877dc-7c4c-4d95-b4a1-e913297d4707.png) <br>

* <I> Path Based Analysis : </I> It takes into account the actual path followed to reach an end point. <br>

* <I> Graph Based Analysis : </I> It takes into account the worst possible path to reach an end point. <br>

![image](https://user-images.githubusercontent.com/62461290/190659029-1d45c606-48ad-4966-bb22-42c2a9d3237e.png) <br>

![image](https://user-images.githubusercontent.com/62461290/190661563-4f051417-5179-4aa0-85b0-97c4cf5b40a2.png) <br>

Path based analysis is more realistic than graph based analysis. <br>

Pin node conventions <br>

![image](https://user-images.githubusercontent.com/62461290/190666816-3f808fdd-92d1-4b3c-b74a-98d5673bb9fb.png) <br>

![image](https://user-images.githubusercontent.com/62461290/190668545-a66d7253-9bcf-46da-945a-28bc4e6ea19b.png) <br>

The calculation of arrival time, require time and slack remains same.

![image](https://user-images.githubusercontent.com/62461290/190668975-88c923a1-b0c1-4fc1-bb8d-b0564dd8dfc9.png)

## Section 3: Clk-to-q delay, library setup, hold time and jitter

| &Delta;<sub>1</sub> - &Delta;<sub>2</sub> | = Skew <br>

![image](https://user-images.githubusercontent.com/62461290/190689424-cd87624c-72ef-449c-b1d7-3c66395895da.png) <br>

Mux level implementation of capture flop. <br>

![image](https://user-images.githubusercontent.com/62461290/190690335-38470d16-a3c2-4caf-ad5b-4b64a3ba1ebf.png) <br>

-> <b> Negative Latch </b> <br>

Transistor level implementation of negative latch. <br>

![image](https://user-images.githubusercontent.com/62461290/190690443-2bcedb68-9edd-4d72-b42d-b8c5c92571ba.png) <br>

When CLK is low, Tr1 turns on and input D is latched to output Q. <br>

![image](https://user-images.githubusercontent.com/62461290/190841128-de7f0e7e-c45b-4ba1-bdf7-da1ac7b24087.png) <br>

-> <b> Positive latch </b> <br>

Transistor level implementation of positive latch. <br>

![image](https://user-images.githubusercontent.com/62461290/190841212-01fe3415-aba3-4dac-b3f6-f2c36e5e12d5.png)<br>

When CLK is high, Tr4 turns on and input Qm is latched to output Q. <br>

![image](https://user-images.githubusercontent.com/62461290/190841270-88fd8e39-c041-4a83-b1b5-88c8f13f7d8e.png)<br>

Clock signals that go to positive latch and negative latch are different, Hence the difference in names. <br>

-> <b> Positive edge triggered flip-flop using master-slave configuration </b> <br>

![image](https://user-images.githubusercontent.com/62461290/190841620-7a1a30f7-ebf0-406c-8652-9ce26214dbf6.png) <br>

Working for the negative level of the clock. D reaches from input of negative latch to input of positive latch. <br>

When CLK is low, Tr1 and Tr3 turns ON. Hence, input D is latched to output Qm of negative latch. Inv4, Inv6 holds the Q state of slave positive latch. Also D' is ready at the output of Inv5 to propagate till Q when CLK becomes high.<br>

![image](https://user-images.githubusercontent.com/62461290/190841716-67b9935e-b4a1-4cf4-bdda-4cf286a570ac.png) <br>

<I><b> Setup Time </b></I> is the time before rising edge of CLK, that input D becomes valid i.e D input has to be stable such that Qm is sent out, to Q reliably. <br>

Input D takes atleast 3 inverter delays+ 1 transmission gate delay to become stable before rising edge of CLK. Atleast this much amount of time is needed by flipflop to accept the data. If the data comes in between this time frame the data will get corrupted. Therefore a certain amount of <b><I> library setup time </I></b> is needed for the data to be stable at the interiors of the flop. <br>

`Setup Time  = 3 Inverter delay + 1 Transmission gate delay`

Working for the positive level of the clock. D reaches from input of positive latch to output port Q. <br>

When CLK  is high, TR2 and TR4 turns on. Hence input Qm is latched to output Q of negative latch through Tr4 and Inv6. Inv2, Inv3 hold the Qm state of master negative latch. <br>

![image](https://user-images.githubusercontent.com/62461290/190850579-d42f3a21-8fbe-4885-afe2-e318019ad806.png) <br>

<b><I> Clock to Q delay </I></b> is the time needed to propagate 'Qm' to 'Q'. (D was stable till output of Inv5). Therefore time required, to propogate is 1 transmission gate delay + 1 inverter delay. <br>

`Clk-Q = 1 transmission gate delay + 1 inverter delay`

Hold Time is the time for which D input remain valid after clock edge. In this case Tr1 is off after rising CLK. So, D is allowed to change or can change immediately after rise CLK edge. So Hold time is zero.

`Hold Time = zero`

The Analysis is accounted by the following equation <b> &Theta;+&Delta;<sub>1</sub> < T+&Delta;<sub>2</sub> - S </b> <br>

![image](https://user-images.githubusercontent.com/62461290/190851682-3e4401d9-394e-457c-a63d-6e2fd47addfa.png) <br>

#### Generating jitter values - Eye diagram

Eye diagram is given by the foundry.<br>

![image](https://user-images.githubusercontent.com/62461290/190887256-debe28a7-fa98-47af-b19a-0fdef2456d95.png) <br>

Count the number of edges and combine the two versions of clk to form a eye diagram. This eye diagram is the ideal eye diagram. <br>

![image](https://user-images.githubusercontent.com/62461290/190887272-33e0477d-389a-4207-986f-add9ac6aeccf.png)<br>

In practical scenario considering the clock network. The clock does not appear at 0ns at every flipflop. It is bound to arrive at different time. This consideration gives one step better realistic/practical eye diagram. <br>

![image](https://user-images.githubusercontent.com/62461290/190887681-14f1e8ff-84ed-4098-8db1-4d73830ce733.png) <br>

Another important consideration to be taken is the power rails. In the above cases it is assumed that the power is constant and ideal which is not practical. Power Supply variations cause voltage drop and ground bounce. <br>

![image](https://user-images.githubusercontent.com/62461290/190887815-abac1c2a-395d-4e05-9f30-0b40feb2b00d.png) <br>

This is the most realistic eye diagram one can expect. <br>

![image](https://user-images.githubusercontent.com/62461290/190887833-3fde63ed-e163-42d3-ba37-1cefc821d478.png) <br>

![image](https://user-images.githubusercontent.com/62461290/190887893-49c81405-4e73-40c5-bc12-6872b3554953.png) <br>

* <I> Noise Margin: </I> Amount of distortion allowed. It is considered as logic 1 or logic 0 if the received signal lies in between the respective noise margin range. <br>

![image](https://user-images.githubusercontent.com/62461290/190888206-884c7e44-3466-435e-a5f0-1a004815a27f.png) <br>

* <I>Window where data is reliable : </I> It is the region outside which the distortion is observed. The non-corrupted data is observed in this area. If the data is launched or captured in this window it is considered as reliable data.<br>

![image](https://user-images.githubusercontent.com/62461290/190888390-57efccee-cf8a-4303-a9ef-dd8c3ad3a442.png) <br>

* <b><I> Jitter : </I></b> The window where the distortion is observed is called jitter. This has to be accounted for in the clock period as well. The new clock period can be 0&plusmn;&Delta; to T&plusmn;&Delta; 

![image](https://user-images.githubusercontent.com/62461290/190888576-b0fc4818-c794-411c-a8b6-f018643bab37.png) <br>

Jitter has to be acccounted for in the timing reports. We model this using one more parameter called Uncertainty. <br>

Example : Uncertainty = 90ps = 0.09ns <br>

![image](https://user-images.githubusercontent.com/62461290/190888874-147cbad4-7acc-4202-b8fa-e5662fd926d9.png) <br>

The Analysis is now accounted by the following equation <b> &Theta;+&Delta;<sub>1</sub> < T+&Delta;<sub>2</sub> - S - SU </b> <br>

![image](https://user-images.githubusercontent.com/62461290/190888967-24e46dfa-a59e-4bcd-8a9a-1e600f88677e.png) <br>

Data Arrival Time should be less than Data Required time. (Slack = Data Required Time - Data Arrival Time) <br>

Slack should be zero or positive. <br>

## Section 4: Textual Timing Reports and Hold Analysis

<b> Setup Analysis Textual Representation </b> <br>

Inputs (b1/a,b2/a etc) represents net delay and Outputs (b1/y,b2/y etc) represents cell delay. <br>

![image](https://user-images.githubusercontent.com/62461290/190898233-e1989fc2-bcc8-4ec5-a62f-bf8d7959bac0.png) <br>

![image](https://user-images.githubusercontent.com/62461290/190898253-2880efe8-acda-4b1b-ad90-0d7ac20f9d1d.png) <br>

Example of textual representation <br>

![image](https://user-images.githubusercontent.com/62461290/190898353-450f824c-d9c8-491e-9125-788bb8c9ca71.png) <br>

### reg2reg Hold (min) analysis - Single Clock

Hold analysis is mostly dependent on launch flop. It is the time required to launch the data. In this analysis only the edge of the clock is considered not the whole period. In case of setup time the whole period was considered. <br>

Clock is ideal below. <br>
![image](https://user-images.githubusercontent.com/62461290/190898518-933ae73c-5b36-40f9-9213-94258465c067.png) <br>

By adding clock buffers the condition changes to  <b> &Theta;+&Delta;<sub>1</sub> > H+&Delta;<sub>2</sub> </b> <br>

![image](https://user-images.githubusercontent.com/62461290/190898649-0a3adb47-4e69-466c-9cd7-3f51e20c142f.png) <br>

The uncertainity caused because of the jitter has less impact in hold analysis because we consider only the launch edge of the clk, incase of setup analysis we consider both the launch edge and capture edge of the flop hence increasing the jitter thereby increasing the uncertainity. Hence incase of hold analysis we will have a lower uncertainty value. <br>

Considering Uncertainity : <b> &Theta;+&Delta;<sub>1</sub> < T+&Delta;<sub>2</sub> + SU </b> <br>

![image](https://user-images.githubusercontent.com/62461290/190899159-df695baf-1945-4cd6-bc8d-51c10c481742.png) <br>

Data Arrival Time should be greater than Data Required time. (Slack = Data Arrival Time - Data Required Time) <br>

Slack should be zero or positive. <br>

<b> Hold Analysis Textual Representation </b> <br>

![image](https://user-images.githubusercontent.com/62461290/190899291-935a8399-82c3-4984-80a5-70e6ee66df32.png) <br>

![image](https://user-images.githubusercontent.com/62461290/190899315-b321a649-a141-48d8-9e9b-2dbc56d06ae4.png)

Example of textual representation <br>

![image](https://user-images.githubusercontent.com/62461290/190899449-1cda5439-f766-4636-963d-56f03d6fcfbf.png) <br>

## Section 5 : On-chip Variation

-> <b><I> Etching Process Variation </I></b> <br>

 <I> Etching process effecting the behaviour of single inverter. </I> <br>
 
 ![image](https://user-images.githubusercontent.com/62461290/190911055-b2effb80-8eeb-4ae7-a8f4-c544a620597e.png) <br>
 
 Inverter chain: <br>
 
 ![image](https://user-images.githubusercontent.com/62461290/190911089-c585bacb-15eb-4584-9def-8958f7c7c3bd.png) <br>
 
 Etching process: <br>
 
![image](https://user-images.githubusercontent.com/62461290/190911216-69113c65-c633-4408-b1c0-a6c4885d0108.png) <br>

This variation can be present for each and every structure. This modified W/L ratio will effect the drain current. <br>

![image](https://user-images.githubusercontent.com/62461290/190911357-a7af4569-db96-46d2-9287-a2f28671ae10.png) <br>

-> <b><I> Oxide Thickness Variation </I></b> <br>

<I> Oxide Thickness Variation effecting the behaviour of single inverter. </I> <br>

![image](https://user-images.githubusercontent.com/62461290/190911408-be4133bc-9c53-4610-acd2-6bc67fc2cc57.png) <br>

 Oxide process: oxide thickness is not constant and will persist for all the transistors. <br>

![image](https://user-images.githubusercontent.com/62461290/190911473-0968d8e8-9963-414c-a9cc-9adcc681c520.png) <br>

The variation in thickness directly impacts the Drain Current. <br>

![image](https://user-images.githubusercontent.com/62461290/190912824-99f93937-96b9-4f26-af18-f017b434c743.png) <br>

<b><I> Propagatin Delay of Inverter Cell  </b></I> <br>

The inverter can be modelled as a switch with RC components. The charging and discharging of the capacitor is the output of the inverter. The charging takes place based on the current Id. <br>

![image](https://user-images.githubusercontent.com/62461290/190913051-0c96d8a9-f7ec-41a5-852c-902dfaaecac4.png) <br>

Output Voltage depends on the amount of current supplied to the capacitor, Which inturns becomes a function of the R and C values. <br>

![image](https://user-images.githubusercontent.com/62461290/190913147-df1d8568-369c-4082-b8f6-f6df4a5034d8.png) <br>

We have to get the Drain current in terms of resistance. <br>

![image](https://user-images.githubusercontent.com/62461290/190913476-a050ee2b-be0c-49c3-a760-df3a0574fb5a.png) <br>

<I> R of inverter cell : </I> R is not constant but varies with Id. <br>

![image](https://user-images.githubusercontent.com/62461290/190913581-2bbad35f-3472-4fea-aedc-af4e62a46af4.png)

Connecting all the parameters together. <br>

![image](https://user-images.githubusercontent.com/62461290/190913617-37f36d75-b8c0-4efc-b353-75ce73dbecf9.png) <br>

Each inverter can give different delays based on the above parameters. The inverters in the corner might deviate more because the cell they are connected to on the other end might have a significant impact on these cells. <br>

![image](https://user-images.githubusercontent.com/62461290/190913710-67b201dd-e3ab-4822-b1d8-640b0ad7306c.png) <br>

Graphically plotting these variations in inverter. <br>

Combining these variations together give a factor called on-chip derates. <br>

![image](https://user-images.githubusercontent.com/62461290/190913961-29f218ca-3a86-4c87-99c3-3a971c405b08.png) <br>

## Section 6: OCV timing and pessimism removal

-> <b><I> OCV for Setup analysis </I></b>

![image](https://user-images.githubusercontent.com/62461290/190919502-519015cf-38f2-4138-98ab-ddbf266e4425.png) <br>

OCV can be compensated in 4 different ways. <br>

1. DRT &uarr; DAT &uarr; <br>
2. DRT &uarr; DAT &darr; <br>
3. DRT &darr; DAT &uarr; <br>
4. DRT &darr; DAT &darr; <br>

When DRT is reduced it is called clock pull-in. <br>

![image](https://user-images.githubusercontent.com/62461290/190919605-2be34cc0-e523-4742-a8f5-fae5aa72e956.png) <br>

When DAT is increased it is called clock push-out. <br>

![image](https://user-images.githubusercontent.com/62461290/190919625-5fcf2c21-62d3-4ca1-9216-a3ef96837c7b.png) <br>

This gives a more realistic and conservative analysis. <br>

![image](https://user-images.githubusercontent.com/62461290/190919548-09848964-d48f-4bce-a2ee-5845058780e8.png) <br>

Pull in DRT by 20%. <br>

![image](https://user-images.githubusercontent.com/62461290/190919739-bfc92934-dc85-4c9b-ae90-abd9bb90d816.png) <br>

The similar sections have to be considered which was ignored before. <br>

![image](https://user-images.githubusercontent.com/62461290/190919805-2870074d-a6f7-4730-aa05-f5b291c00785.png) <br>

<I> A cell cannot have 2 delay values at same instance of time. </I> <br> 

Example: At a time instant the delay of cell 'b1' can be either 0.043ns or 0.0344ns. So there is an additional pessimism of |0.043ns - 0.0344ns| = 0.0086ns. We need to remove this pessimism. <br>

![image](https://user-images.githubusercontent.com/62461290/190919873-19a913c0-b67b-4d2c-aa76-015f263f6fa3.png) <br>

After adding pessimism to DRT we get positive slack. <br>

![image](https://user-images.githubusercontent.com/62461290/190920013-794464b2-cd92-443c-8a4f-542008f0c956.png) <br>

Additional pessimism has to be accounted while doing calculations. It is one of the important factor. <br>


-> <b><I> OCV for Hold analysis </I></b>

![image](https://user-images.githubusercontent.com/62461290/190921433-b1f400de-ed6c-4aa0-8ab6-9f63c31f8833.png)

OCV can be compensated in 4 different ways here as well. <br>

Here, When DAT is reduced it is called clock pull-in. When DRT is increased it is called clock push-out. Here we will do both pull-in and push-out to get the worst case analysis. <br>

![image](https://user-images.githubusercontent.com/62461290/190921562-272bdd39-4e56-4073-8d0d-f682ef7b8996.png) <br>

![image](https://user-images.githubusercontent.com/62461290/190921579-fb056a06-3bdb-4770-b2fa-774a8e4093fd.png) <br>

If hold analysis fails we cannot recover and the whole chip will fail. <br>

performed push-out by 20% and pull-in by 20% together. <br>
![image](https://user-images.githubusercontent.com/62461290/190921644-9c82d12a-7dec-40a3-a37b-336791bb3b04.png) <br>

Additional pessimism has to be considered here as well. 

![image](https://user-images.githubusercontent.com/62461290/190921692-225cc1b2-779b-4f09-8611-1aa4f9aab76a.png)

After considering additonal pessimism. <br>

![image](https://user-images.githubusercontent.com/62461290/190921740-f2d318f6-ba5d-4485-99a3-db67ccde5ed1.png) <br>

## Section 7 : Conclusion

- We summarized rer2reg timing analysis. The concepts we learned for reg2reg analysis can be applied to any other setup/hold analysis. <br>

- While doing Slew/Transition analysis we will be using library setup and hold time. <br>

- Clock analysis is highly dependent on on-chip variation and pessimism removal. <br>

## static timing analysis-2

### report_at command:
   
![image](https://user-images.githubusercontent.com/110079770/193732335-2b6f4796-aaac-492c-8183-6d99e62aad20.png)



![image](https://user-images.githubusercontent.com/110079770/193745293-a7b8145c-d558-4b7f-af1d-9e647f7a6704.png)

for launch path consider late delays and for capture path consider early paths.

![image](https://user-images.githubusercontent.com/110079770/193746489-719b08a5-ee73-46cb-b80f-2ff8aa29d612.png)


swapping the cells
![image](https://user-images.githubusercontent.com/110079770/193890117-cce6ec6a-f360-4bf5-9362-db33cd823d00.png)



problem

![image](https://user-images.githubusercontent.com/110079770/193755986-eb16ee2d-415f-4d66-a088-df8ce7f16b08.png)


## 14. Contributors 

- **GogiReddy Ravi Kiran Reddy** 
- **Kunal Ghosh** 



## 15. Acknowledgments

- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.

## 16. Contact Information

- GogiReddy Ravi Kiran Reddy, Postgraduate Student, International Institute of Information Technology, Bangalore.
- Email: gogireddyravikiranreddy1@gmail.com
- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com
