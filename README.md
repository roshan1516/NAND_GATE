# NAND_GATE
# NAND Gate using 28nm CMOS Technology
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
In this paper I am going to implement NAND gate using CMOS technology and here we will design a NAND gate using a series and parallel connection of pMOS and nMOS transistors using 28nm technology. Basically, pMOS and nMOS transistors act as ideal switches. The circuit design and implementation will be done using esim and ngspice software. A NAND Gate is a logic gate that produces a low output (0) only if all its inputs are true, and high output (1) otherwise.We can verify the output using circuit waveform. This complete design and implementation is done using CMOS VLSI technology. Also the simulation results of both the gates are obtained at the same node with rise time, fall time,area,delay and power dissipation (dynamic power and static power). All the processes have been carried out using the Synopsys Custom Compiler tool.

## Reference Circuit Details

The figure 1 shows the 2-input CMOS NAND Gate,to design a 2-input CMOS NAND Gate,two pMOS are connected in parallel and two nMOS are connected in series. 
Case-1 : VA – Low & VB – Low::As VA and VB both are low, both the pMOS will be ON and both the nMOS will be OFF. The output line will maintain the voltage level at Vdd; so,High.
Case-2 : VA – Low & VB – High,VA – Low: pMOS1 – ON; nMOS1 – OFF,VB – High: pMOS2 – OFF; nMOS2 – ON.This in turn results the Vout to be maintained at the level of Vdd; so,High.
Case-3 :VA –High &VB –Low,VA – High: pMOS1 – OFF; nMOS1 – ON,VB – Low: pMOS2 – ON; nMOS2 – OFF,The explanation is similar as case-2. Vout level will be High.
Case-4 : VA – High & VB – High,VA – High: pMOS1 – OFF;nMOS1 – ON,VB – High: pMOS2 – OFF; nMOS2 – ON;Vout will be discharged; so, Low.


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
Thus, we designed and simulated a 2 input NAND Gate using Synopsys Custom Compiler using 28nm technology and we observed that when both the inputs are 1 the output is 0.

## Author
Roshan Kumar, National Institute of Science and Technoology,Berhampur.

## Acknowledgement
1. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
2. Chinmaya Panda, IIT Hyderabad
3. Sameer Durgoji, NIT Karnataka
4. [Synopsys Team/Company](https://www.synopsys.com/)
5. https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/

## References
1) http://cmosedu.com/jbaker/courses/ee421L/f18/students/sendad1/lab6/lab6.htm
2) https://www.electrical4u.com/nand-gate/ 
3) Sung-Mo Kang, Yusuf Leblebici. “CMOS Digital Integrated Circuits (Analysis and Design),” 3rd edition, Tata McGraw-Hill.

