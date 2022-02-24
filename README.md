# NAND_GATE
NAND Gate Using 28nm CMOS Technology
# NAND using 28nm CMOS Technology
  * [Abstract](#abstract)
  * [Reference Circuit Details](#reference-circuit-details)
  * [Reference Circuit Diagram](#reference-circuit-diagram)
  * [Reference Circuit Waveform](#reference-circuit-waveform)
  * [Desirable Truth Table](#desirable-truth-table)
  * [Tools Used](#tools-used)
- [Simulation in Synopsys](#simulation-in-synopsys)
  * [Parameters set for Voltage Source for Input A](#parameters-set-for-voltage-source-for-input-a)
  * [Parameters set for Voltage Source for Input B](#parameters-set-for-voltage-source-for-input-b)
  * [Transient Settings](#transient-settings)
  * [Schematic of NAND_Gate using the above Blocks](#schematic-of-full_adder-using-the-above-blocks)
  * [Output Waveform](#output-waveform)
  * [Netlist](#netlist)
  * [Conclusion](#conclusion)
  * [Author](#author)
  * [Acknowledgement](#acknowlegement)
  * [References](#references)


## Abstract
Full adder is an essential component for the design and development of all types of processors like digital signal processors (DSP), microprocessors etc. In most of these systems adder lies in the critical path that affects the overall speed of the system.An adder is a digital circuit that performs addition of numbers and it plays an important role in today’s digital world. In processors and other kinds of computing devices, Adders are used in the arithmetic logic units. They are also utilized in other parts of the processors for calculating addresses, table indices, increment and decrement operations and other similar operations because it is the basic building block of on-chip libraries. Also, it can be used for the construction of many number representations and it is a trivial to modify an adder into an adder-subtractor. Full adder reduces circuit complexity and can be integrated in the calculators for addition and subtraction operations. At DSP oriented system and at networking side full adder is used mostly. Full adders can be cascaded (e.g.: ripple carry adder) easily so that one can make a cascade to add any number of bits that form the word- width of a system.
## Reference Circuit Details

Conventional CMOS Full Adder is the most basic full adder implementation techniques. Conventional CMOS Full Adder consists of 28 transistors. A, B and Cin are the inputs and Sum & Cout are the outputs. Static logic provides robustness against noise effects, so automatically provides a reliable operation. Pseudo NMOS pass-transistor logic and reduce the number of transistors required to implement a given logic function but these suffer from static power dissipation. On the other hand, dynamic logic requires less silicon area for implementation of complex function but charge leakage and charge refreshing are required which reduces the frequency of operation. This circuit uses both NMOS and PMOS transistors. In Conventional CMOS Full Adder, there are many leakage paths which lead to more sub threshold leakage.

## Reference Circuit Diagram
![image](https://user-images.githubusercontent.com/72511316/155567229-ca600174-c3a2-48e6-a41e-a7f7c72d8743.png)

## Reference Circuit Waveform
![image](https://user-images.githubusercontent.com/72511316/155567312-0289011b-28c1-4021-ab3e-084785b4859e.png)

## Desirable Truth Table
![image](https://user-images.githubusercontent.com/72511316/155567530-8436d6c4-dd39-4e05-b796-503b7eef6ae4.png)

## Tools Used:
• Synopsys Custom Compiler:
 The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.
 
 ![custom_compiler](https://user-images.githubusercontent.com/59500283/155473715-c6a1fd5b-71c7-4655-936a-5fe3befabfd8.png)


• Synopsys Primewave:
 PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.

• Synopsys 28nm PDK:
 The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.

# Simulation in Synopsys
## NAND_Gate_Block
![Screenshot 2022-02-24 011629](https://user-images.githubusercontent.com/72511316/155566303-41e980f4-8bfe-4acd-9ba7-afc749a36f4b.png)
![Screenshot 2022-02-24 215736](https://user-images.githubusercontent.com/72511316/155566387-c41768c9-0654-4e99-becf-080c523cbb06.png)

## Parameters set for Voltage Source for Input A
![Screenshot 2022-02-24 230123](https://user-images.githubusercontent.com/72511316/155578396-a6f7a29a-2c92-4415-a481-bccab147d648.png)

## Parameters set for Voltage Source for Input B
![Screenshot 2022-02-24 230509](https://user-images.githubusercontent.com/72511316/155578357-f1759c35-3a9c-4815-bd85-7bf36d679bd0.png)

## Transient Settings
![Screenshot 2022-02-24 230805](https://user-images.githubusercontent.com/72511316/155578276-492a34b9-28c1-40e0-a37a-94ae2b999fbe.png)

## Schematic of NAND_Gate using the above Blocks
![Screenshot 2022-02-23 220716](https://user-images.githubusercontent.com/72511316/155573505-242ef3ea-58af-43d5-ad2d-ac204a0b62c1.png)

## Output Waveform
![Screenshot 2022-02-23 220532](https://user-images.githubusercontent.com/72511316/155573612-45a13e04-754b-4c9b-b4dc-bf889185333c.png)



## Netlist
```


*  Generated for: PrimeSim
*  Design library name: ng_gateftw
*  Design cell name: ng_gate_tb
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Thu Feb 24 16:39:01 2022

.global gnd!
********************************************************************************
* Library          : ng_gateftw
* Cell             : ng_gate
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt ng_gate a b gnd_1 vdd vout
xm1 vout b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm0 vout a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm3 net13 b gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm2 vout a net13 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
.ends ng_gate

********************************************************************************
* Library          : ng_gateftw
* Cell             : ng_gate_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 a b gnd! net6 op ng_gate
v24 net6 gnd! dc=1.05
v21 a gnd! dc=0 pulse ( 0 1 0 0.1u 0.1u 6u 10u )
v26 b gnd! dc=0 pulse ( 0 1 0 0.1u 0.1u 10u 20u )








.tran '0.1u' '60u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(op)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end

```

## Conclusion
Thus, the addition for a single-bit is achieved using 28T full adder.

## Author
Roshan Kumar, National Institute of Science and Technoology,Berhampur.
## Acknowledgement
1. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
2. Chinmaya Panda, IIT Hyderabad
3. Sameer Durgoji, NIT Karnataka
4. [Synopsys Team/Company](https://www.synopsys.com/)
5. https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/
## References
1)Analysis and Performance Evaluation of 1-bit Full Adder Using Different Topologies
http://pnrsolution.org/Datacenter/Vol5/Issue1/26.pdf

2)Power and Delay Comparison in between Different types of Full Adder Circuits
https://www.ijareeie.com/upload/september/7_Power%20and%20Delay%20Comparison.pdf

3)Youtube Video - https://www.youtube.com/watch?v=AXU_J4wr_yA
  

