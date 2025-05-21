# MOSFET
MOSFETs are particularly useful in amplifiers due to their input impedance being nearly infinite which allows the amplifier to capture almost all the incoming signal. The main advantage is that it requires almost no input current to control the load current and that’s why we choose MOSFET over BJT.
# Structure:
![image](https://github.com/user-attachments/assets/93a2d56c-d1cc-4bec-a619-49e806219c35)

It is a four-terminal device with Source (S), Drain (D), Gate (G), and body (B) terminals. The body (B) is frequently connected to the source terminal, reducing the terminals to three. It works by varying the width of a channel along which charge carriers flow (electrons or holes).
The charge carriers enter the channel at the source and exit via the drain. The width of the channel is controlled by the voltage on an electrode called Gate which is located between the source and the drain. It is insulated from the channel near an extremely thin layer of metal oxide. 

A metal-insulator-semiconductor field-effect transistor or MOSFET is a term almost synonymous with MOSFET. Another synonym is IGFET for the insulated-gate field-effect transistor.

## Different Types of MOSFET
MOSFET works in two modes-

1. Depletion Mode: The transistor requires the Gate-Source voltage (VGS) to switch the device “OFF”. The depletion-mode MOSFET is equivalent to a “Normally Closed” switch.

2. Enhancement Mode: The transistor requires a Gate-Source voltage (VGS) to switch the device “ON”. The enhancement mode MOSFET is equivalent to a “Normally Open” switch.

Now with respect to the working principle, MOSFET is classified as follows:

P-Channel Depletion MOSFET
P-Channel Enhancement MOSFET
N-Channel Depletion MOSFET
N-Channel Enhancement MOSFET 

## P-Channel MOSFET

![image](https://github.com/user-attachments/assets/61a34e98-3d5d-49bf-8c45-4303cbb90e37)

The drain and source are heavily doped p+ region and the substrate is in n-type. The current flows due to the flow of positively charged holes, and that’s why known as p-channel MOSFET. 

When we apply negative gate voltage, the electrons present beneath the oxide layer experience repulsive force and are pushed downward into the substrate, the depletion region is populated by the bound positive charges which are associated with the donor atoms. 

The negative gate voltage also attracts holes from the P+ source and drain region into the channel region.

## N-Channel MOSFET

![image](https://github.com/user-attachments/assets/105cece4-e562-4af5-a462-7765b71fe445)

The drain and source are heavily doped N+ region and the substrate is p-type. The current flows due to the flow of negatively charged electrons and that’s why known as n-channel MOSFET. 

When we apply the positive gate voltage, the holes present beneath the oxide layer experience repulsive force, and the holes are pushed downwards into the bound negative charges which are associated with the acceptor atoms. 

The positive gate voltage also attracts electrons from the N+ source and drain region into the channel thus an electron-rich channel is formed.

## Operation of n channel MOSFET
Body and source are tied to ground.
When VDS= 0 and VGS=0, source-body
and drain-body diode are off hence no
current can flow & MOSFET is in cutoff.

When VDS= 0 and 0 < VGS < Vt ,Vertical
electric field established. Holes repelled
and depletion region under gate oxide
forms.

When VDS= 0 and VGS > Vt, A n type
inversion layer formed underneath the
gate oxide when VGS reaches a critical
value Vt, called threshold voltage. The
channel connects source to drain and
current flow between them.

When VGS > Vt and a small VDS is applied
– Current flows from D to S (Electrons flow from S to D) and IDS
∝ VDS

Increase VDS Decrease VGD less electrons at the drain side of the channel

When VDS ≥ VGS – Vt then VGD ≤ Vt so no channel exists at the drain side. The
channel “pinches-off”
When channel pinches off, electrons still flows from S to D
Electrons are diffused from the channel to the depletion region near D, where they
are drifted by the lateral E-field to the D
Further increase of VDS
 Further increase of V - no effect on the channel - current is “saturated” and the DS
- no effect on the channel - current is “saturated” and the
transistor is in “Saturation Mode”

![image](https://github.com/user-attachments/assets/c99a827b-42c4-436e-a290-56181aabd24a)

## Body Effect in mosfet

Whenever there is a voltage (potential) difference between the source and substrate (body), this leads to an increase or decrease in the threshold voltage of the transistor. This is called a “body effect.
Body effect refers to the change in the transistor threshold voltage resulting from a voltage differnce between the source and body affects the Vt the body can be thought of ass a second gate that helps to determine how the transistor turns on and off.
Body effect oocurs when the body or substrate of the transistor is not biased at the same level as that of the source.
And this voltage difference between source and bulk leads to an increase or decrease of the threshold voltage.

## CHANNEL LENGTH MODULATION 

Channel length modulation (CLM) is an effect in field effect transistors, a shortening of the length of the inverted channel region with increase in drain bias for large drain biases. The result of CLM is an increase in current with drain bias and a reduction of output resistance. It is one of several short-channel effects in MOSFET scaling. It also causes distortion in JFET amplifiers.
To understand the effect, first the notion of pinch-off of the channel is introduced. The channel is formed by attraction of carriers to the gate, and the current drawn through the channel is nearly a constant independent of drain voltage in saturation mode. However, near the drain, the gate and drain jointly determine the electric field pattern. Instead of flowing in a channel, beyond the pinch-off point the carriers flow in a subsurface pattern made possible because the drain and the gate both control the current. In the figure at the right, the channel is indicated by a dashed line and becomes weaker as the drain is approached, leaving a gap of uninverted silicon between the end of the formed inversion layer and the drain (the pinch-off region). 

![image](https://github.com/user-attachments/assets/486832e8-e360-4b9c-a42b-3e1749b8d779)

As the drain voltage increases, its control over the current extends further toward the source, so the uninverted region expands toward the source, shortening the length of the channel region, the effect called channel-length modulation. Because resistance is proportional to length, shortening the channel decreases its resistance, causing an increase in current with increase in drain bias for a MOSFET operating in saturation. The effect is more pronounced the shorter the source-to-drain separation, the deeper the drain junction, and the thicker the oxide insulator. 

![image](https://github.com/user-attachments/assets/1bb9415a-9869-4b3a-82af-3de2a9d623a2)

In the weak inversion region, the influence of the drain analogous to channellength modulation leads to poorer device turn off behavior known as drain-induced barrier lowering, a drain induced lowering of threshold voltage.
In bipolar devices, a similar increase in current is seen with increased collector voltage due to base-narrowing, known as the Early effect. The similarity in effect upon the current has led to use of the term "Early effect" for MOSFETs as well, as an alternative name for "channel-length modulation".
The effect of channel-length modulation upon the MOSFET output resistance varies both with the device, particularly its channel length, and with the applied bias. The main factor affecting the output resistance in longer MOSFETs is channel length modulation as just described. In shorter MOSFETs additional factors arise such as: draininduced barrier lowering (which lowers the threshold voltage, increasing the current and decreasing the output resistance), velocity saturation (which tends to limit the increase in channel current with drain voltage, thereby increasing the output resistance) and ballistic transport (which modifies the collection of current by the drain, and modifies drain induced barrier lowering so as to increase supply of carriers to the pinch-off region, increasing the current and decreasing the output resistance). 

## What is CMOS Inverter

![image](https://github.com/user-attachments/assets/88c774e9-1a8c-4cb2-b350-6a3aaf06e530)

The diagram is shown with two transistors tied up in series between the ground and the power source in it.
Unlike PMOS transistors where the source is linked to power supply and the drain is tied to the output , an NMOS transistor’s source is directly linked with earth while its drain is linked with output.
The input to the inverter is actually a mutual connection between the gates of the two transistors.
When the input level reaches logic level 0, the NMOS transistor is on which causes PMOS transistor to be cut-off therefore causing high output. On the contrary, in a scenario where NMOS transistor goes off, inverter’s output is low due to high input voltage.

## Operations of CMOS Inverter

In order to create a CMOS inverter, one has to merge two types of transistors : PMOS and NMOS respectively.
The process requires that you connect them in this way, thus, there must be one NMOS and one PMOS transistor consisting a CMOS inverter made on the same silicon chip.
The input terminal is made up of NMOS and PMOS transistors that have an input voltage applied to their gates together with an output terminal which is connected to drains of the two transistors.
The sources of PMOS and NMOS transistors are attached to distinct power supply voltages unlike in the case of the other terminals. Specifically speaking, the NMOS transistor is connected to ground (0 V) while its counterpart, PMOS transistor is connected to a positive power supply voltage (Vdd).

## Working of CMOS Inverter

Input High (Logic 1): An NMOS transistor is turned on by input of high voltage (logic 1) while a PMOS transistor is turned off there. When these two things happen, the output voltage (logic 0) is lowered through reduced resistance path between an output terminal and ground.
Input Low (Logic 0): In contrast, when a low voltage (logic 0) is provided to the input terminal, the NMOS transistor switches off and the PMOS transistor conducts. The output voltage (logic 1) rises as a result of the low resistance path that exists between the output terminal and the positive power supply voltage (VDD).
The CMOS inverter operates more easily because of the complimentary characteristics of the NMOS and PMOS transistors. Because one of the transistors conducts while the other is off depending on the input voltage, the output of the transistors is inverted with respect to the input signal.
CMOS inverters offer very low static power dissipation (no DC current flows between VDD and ground while the input is at a constant logic level) as a result of this complimentary pairing.

## Characteristics of CMOS Inverter

### Inverter Static Characteristics (VTC)

When the circuit is static, VTC shows how the output voltage changes with the input voltage. The threshold voltage is the point at which the output states abruptly change from high to low. The production decreases below this level and stays high above it. To ensure balanced functioning, CMOS inverters should ideally provide a symmetric VTC around the midpoint voltage.

The VTC is like an upside down step function because of the increased accuracy in turning ON/OFF transitions. Quality in the transition region is suggested by the existence of well-defined slopes that enable precise switching. By comparing the lowest input value within each ON or OFF operation region with the highest output value, one could calculate the tolerance for noise.

![image](https://github.com/user-attachments/assets/6cecdc4a-adbc-4a3d-bcc0-a6d44f21dc56)

### Inverter Dynamic Characteristics

These show how the inverter responds to changes in input signal over time, which is crucial for circuit speed and efficiency. Effective charging and discharging of the output node is possible in CMOS inverters due to the quick switching speeds offered by complementary NMOS and PMOS transistors.
Rise Time or tR: the time for a signal to go from 10% to 90% of its final value.
Peak Time or tP: Time taken for a response to reach maximum value.
Fall Time or tF: the time taken for 90%-10% drop in the signal depending on its value.

![image](https://github.com/user-attachments/assets/fa628184-55f8-4007-a9b9-1a1781a00550)

## CMOS Fabrication

Making of CMOS using N well
Step 1: First we choose a substrate as a base for fabrication. For N- well, a P-type silicon substrate is selected.
![image](https://github.com/user-attachments/assets/d512abae-c968-443c-b7c9-01694ab1257d)

Step 2 – Oxidation: The selective diffusion of n-type impurities is accomplished using SiO2 as a barrier which protects portions of the wafer against contamination of the substrate. SiO2 is laid out by oxidation process done exposing the substrate to high-quality oxygen and hydrogen in an oxidation chamber at approximately 10000c

![image](https://github.com/user-attachments/assets/d447a91b-111c-4fb8-892e-9bfeed9aee80)

Step 3 – Growing of Photoresist: At this stage to permit the selective etching, the SiO2 layer is subjected to the photolithography process. In this process, the wafer is coated with a uniform film of a photosensitive emulsion.

![image](https://github.com/user-attachments/assets/a3db47df-94b5-41ca-98a9-0fe3996ff750)

Step 4 – Masking: This step is the continuation of the photolithography process. In this step, a desired pattern of openness is made using a stencil. This stencil is used as a mask over the photoresist. The substrate is now exposed to UV rays the photoresist present under the exposed regions of mask gets polymerized.

![image](https://github.com/user-attachments/assets/6056df65-8344-4178-acdb-a8afac5b2d1e)

Step 5 – Removal of Unexposed Photoresist: The mask is removed and the unexposed region of photoresist is dissolved by developing wafer using a chemical such as Trichloroethylene.

![image](https://github.com/user-attachments/assets/50920c0b-d649-48da-9442-ab41e54c1c91)

Step 6 – Etching: The wafer is immersed in an etching solution of hydrofluoric acid, which removes the oxide from the areas through which dopants are to be diffused.

![image](https://github.com/user-attachments/assets/07efec6b-b63c-4cb6-880b-e888154b91ee)

Step 7 – Removal of Whole Photoresist Layer: During the etching process, those portions of SiO2 which are protected by the photoresist layer are not affected. The photoresist mask is now stripped off with a chemical solvent (hot H2SO4).

![image](https://github.com/user-attachments/assets/98b728a1-618a-4133-88be-2a633d631e91)

Step 8 – Formation of N-well: The n-type impurities are diffused into the p-type substrate through the exposed region thus forming an N- well.

![image](https://github.com/user-attachments/assets/21b1bce5-d297-4a4b-9dd0-3ca9b01afc09)

Step 9 – Removal of SiO2: The layer of SiO2 is now removed by using hydrofluoric acid.

![image](https://github.com/user-attachments/assets/4fd86a63-5cb9-4ec3-8b05-479389feffa1)

Step 10 – Deposition of Polysilicon: The misalignment of the gate of a CMOS transistor would lead to the unwanted capacitance which could harm circuit. So to prevent this “Self-aligned gate process” is preferred where gate regions are formed before the formation of source and drain using ion implantation.

![image](https://github.com/user-attachments/assets/e9a90390-9ea0-4196-bd97-1085cf9f1ba1)

Polysilicon is used for formation of the gate because it can withstand the high temperature greater than 80000c when a wafer is subjected to annealing methods for formation of source and drain. Polysilicon is deposited by using Chemical Deposition Process over a thin layer of gate oxide. This thin gate oxide under the Polysilicon layer prevents further doping under the gate region.

Step 11 – Formation of Gate Region: Except the two regions required for formation of the gate for NMOS and PMOS transistors the remaining portion of Polysilicon is stripped off.

![image](https://github.com/user-attachments/assets/9bb14aee-6cd0-487f-912d-1ee284a92fc0)

Step 12 – Oxidation Process: An oxidation layer is deposited over the wafer which acts as a shield for further diffusion and metallization processes.

![image](https://github.com/user-attachments/assets/49915b21-31ca-4517-8b0e-1a0c8108f3d7)

Step 13 – Masking and Diffusion: For making regions for diffusion of n-type impurities using masking process small gaps are made.

![image](https://github.com/user-attachments/assets/40e2cf0a-3395-4ccd-b130-389e01e6620f)

Using diffusion process three n+ regions are developed for the formation of terminals of NMOS


Step 14 – Removal of Oxide: The oxide layer is stripped off.

![image](https://github.com/user-attachments/assets/40f24223-fac0-42c2-a150-5fcd1a6b66d8)

Step 15 – P-type Diffusion: Similar to the n-type diffusion for forming the terminals of PMOS p-type diffusion are carried out.

![image](https://github.com/user-attachments/assets/de929195-e2d4-4dea-b97a-21f7e9dfae04)

Step 16 – Laying of Thick Field oxide: Before forming the metal terminals a thick field oxide is laid out to form a protective layer for the regions of the wafer where no terminals are required.

![image](https://github.com/user-attachments/assets/998484cb-e8b9-47bb-b27a-bf64d899b18c)

Step 17 – Metallization: This step is used for the formation of metal terminals which can provide interconnections. Aluminum is spread on the whole wafer.

![image](https://github.com/user-attachments/assets/1dddccdb-00f0-4793-afbf-8100f1e798fe)

Step 18 – Removal of Excess Metal: The excess metal is removed from the wafer.

Step 19 – Formation of Terminals: In the gaps formed after removal of excess metal terminals are formed for the interconnections.

Step 20 – Assigning the Terminal Names: Names are assigned to the terminals of NMOS and PMOS transistors.

![image](https://github.com/user-attachments/assets/c30e2dfd-6160-4cb3-bc04-166ead0aaaed)

## Implementation of NAND and NOR gate using CMOS Logic:

** NAND GATE **

![image](https://github.com/user-attachments/assets/39bb0a01-c1d1-421e-a4ed-122a1941054a)

For two input NAND gate, if A and B are the inputs then its output Y = (A.B)’.

In NMOS network when we have AND operation between the two variables, then two NMOS transistors will get connected in series. And the output will be complement of it.

The PMOS network is dual of the NMOS network. In the NMOS network, if two transistors are connected in series then in the PMOS network, the two PMOS transistors will get connected in parallel.

** NAND GATE **
![image](https://github.com/user-attachments/assets/84cc7828-be36-4db4-9b40-cbfeb94a746e)

For two input NOR gate, if A and B are the inputs then its output Y = (A+B)’.

In the NMOS network, whenever there is an OR operation between the two variables then two NMOS transistors will get connected in parallel. And the output will be complement of it.

The PMOS network will be the dual of the NMOS network. Therefore, in the PMOS network, the two PMOS transistors will get connected in series.

## Power Dissipation of a CMOS Inverter

### Dynamic Power Consumption

Power is consumed whenever current is flowing through a conductive element. We see this relationship in the basic formula for electric power:

P = I * V

Though a CMOS inverter doesn’t require current flow in its steady state, power is consumed during its logic transitions. This dynamic power loss comes in two types:

1. Switching power dissipation.
2. Short-circuit power dissipation.

## Switching Power Dissipation
When an input logic transition occurs, transient current must flow in order to charge or discharge capacitance in the circuit. During a low-to-high output transition, current flows to charge up the load capacitance as the output voltage increases to VDD. Figure 2 shows the path taken by this current.

![image](https://github.com/user-attachments/assets/ef72d882-5fe1-4038-bf07-3b9ab9b5494a)

Current also flows during a high-to-low output transition (Figure 3), discharging capacitance as the output voltage decreases to ground potential.

![image](https://github.com/user-attachments/assets/1fb854b1-4812-4a70-b1bb-d986a8330953)

To estimate the switching loss of a CMOS inverter, we use the following equation:

![image](https://github.com/user-attachments/assets/78d017d6-6b06-42d9-a8d5-61fdac7e4037)

where:

CL is the expected load capacitance

f is the switching frequency.

CL × VDD2 calculates the amount of energy required for one switching cycle.

## Short-Circuit Power Dissipation

Another type of dynamic power dissipation is caused by short-circuit current. Also known as shoot-through current, this is a transient condition that occurs during an inverter’s logic level transitions.

When a CMOS inverter is settled in a logic state, one of its two transistors is in a non-conductive mode. Consequently, current can’t easily flow from VDD to ground. When the inverter changes states, however, there’s a brief crossover period during which both the NMOS and the PMOS have some degree of conductivity. Energy is lost as current flows through the resulting short circuit

![image](https://github.com/user-attachments/assets/b498a616-774e-499f-a1dc-03b24f740317)

## Static Power Consumption
Throughout this article, I’ve avoided saying anything along the lines of “absolutely no steady-state power dissipation occurs in a CMOS inverter.” The fact is that field-effect transistors aren’t ideal switches. Even in the OFF state, leakage currents can flow from the drain to the source and from the drain or source to the substrate.

If the magnitude of these leakage currents is known, the resulting power dissipation can be calculated using the formula:

![image](https://github.com/user-attachments/assets/942f36ce-e6ee-4df5-9d63-da4195693c11)

Dynamic power consumption used to be much higher than static power consumption. Nowadays, static power can be significant. As CMOS feature sizes decrease, its contribution to total dissipation approaches that of dynamic power.

Finally, note that static power is a function of operating temperature. As temperature increases, static power dissipation also increases.

## Design a CMOS digital circuit that realizes the
Boolean function:

![image](https://github.com/user-attachments/assets/6461a5a2-782b-4c26-a77a-4d6cb46c4d1b)

Solution: Follow the steps of the design synthesis handout!

Step1: Design the PDN

First, we must rewrite the Boolean function as:

![image](https://github.com/user-attachments/assets/e9fbb25c-857a-4f06-a3cd-d7ceefc91c52)

In other words, write the complemented output in terms of
un-complemented inputs. 

![image](https://github.com/user-attachments/assets/e2c467d9-0c3a-4b28-86c3-d65544afa892)

We can thus realize this logic with the following NMOS PDN:

Step2: Design the PUN 

![image](https://github.com/user-attachments/assets/df3f1db8-3e86-4128-9151-6f878a719aec)


![image](https://github.com/user-attachments/assets/12ac342b-20a0-408e-beb9-9b2a6e2c9135)

We can thus realize this logic with the following PMOS PUN:

![image](https://github.com/user-attachments/assets/af08bef7-0bc3-4df7-9749-c02faf75d837)

Thus, the entire CMOS realization is

![image](https://github.com/user-attachments/assets/8b6438bd-9109-41a5-abae-2b397d48a88b)





