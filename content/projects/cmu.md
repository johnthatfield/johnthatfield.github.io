+++
title = 'Cell Monitoring Unit (CMU)'
date = 2023-12-17T16:56:51+01:00
draft = false
showInHome = false
socialShare = false
toc = false
+++


# Introduction

Cell Monitoring Unit
- Talks to slave cell monitoring units (CMUs) over IsoSPI
- Filters and monitors reported cell voltages and tempeatures
- Runs cell balancing algorithm
- Interface to charger to put BMU in charge state and take commands from charger about when to pre-charge
- Has shutdown interface for Insulation Monitoring Device (IMD), precharge resistor thermal sensor (PDOC), connector interlocks, and BMU battery state. Detection for these interfaces. 


Joint project with Thomas Hulbert. 



# Design Requirements

## FSAE Rules 2023

### CMU (AMS) Rules
At QUT Motorsport we refer to the 'Accumulator Management System' as a combination of the BMU (battery monitoring unit) and CMU (cell monitoring units)

The relevant rules from below are
- The AMS system must have galvanic isolation at every segment to segment boundary - i.e. isolation transformers
- Work in progress

<div style="text-align: center;">
<img src="/images/bmu/Rules_AMS.png" alt="AMS FSAE Ruleset 2023" style="max-width: 800px;"/>
</div>




<!-- ### Voltage Separation
- The GLV and the Tractive circuits must be galvanically isolated 

<div style="text-align: center;">
<img src="/images/tsal/FSAERuleVoltageSeparation.png" alt="Voltage Separation FSAE Ruleset 2023" style="max-width: 800px;"/>
</div> -->

<!-- ### PCB Clearance
- 12.7mm clearance over uncoated surface, or 4mm clearance under conformal coating
<div style="text-align: center;">
<img src="/images/tsal/GLVTSClearance.png" alt="Clearance FSAE Ruleset 2023" style="max-width: 800px;"/>
</div> -->



## IPC Design Requirements for TS to TS clearances
On surface of uncoated PCB
- 0.6mm spacing between nets >=31V potential to each other
- 0.1mm spacing for nets <= 30V potential to each other

## Team Design Requirements


# Revision B - QEV-3 Only
A long time solution of a 'Revision A' BMU strategy, using a BMU chip, a microcontroller and canbus between each slave device was used. We had some systemic issues with this which caused the upgrade. 

The revision A of the CMU was designed to interface in the same position as the previous generation QEV-3 BMS system. It would feature only 10 out of 14 cells. 

Assembly of this device is shown below. The pototypes were hand placed at uni and soldered in a vapour phase oven.
![CMU Rev B Assembly](/images/cmu/cmu_rev_b_placed.jpg "CMU Rev B Assembly")

<!-- 
Testing of the Revision B CMUs. Two CMUs, one connected to a battery, one connected to a battery emulator board, 

![CMU Rev B Testing](/images/cmu/cmu_rev_b_testing.jpg "CMU Rev B Testing") -->

An implementation error with unused voltage taps was found - a fix was prototyped on the PCB as shown in the photo below.
![CMU Rev B](/images/cmu/cmu_rev_b.jpg "CMU Rev B")

# Revision C
It was decided that the same CMU architecture should be used for the new vehicle - QEV-4. All 14 cells are required for QEV-4, so a 14 cell CMU should be designed and un-used cells tied together as per the datasheet. 

Below shown is the full implementation of the L9963E cell monitoring unit. It was designed around a small, double sided component load form factor, enabling it to fit atop of the small QEV-4 battery assembly. 

A board to board connector was chosne, enabling it to either sit atop of a carrier PCB, or, connected with a custom flat flex cable.

<div style="text-align: center;">
<img src="/images/cmu/CMU_Altium.png" alt="CMU Altium" style="max-width: 800px;"/>
</div>



## Prototype Assembly
Prototypes were assembled by hand and reflowed in a vapour phase oven.
<div style="text-align: center;">
<img src="/images/cmu/cmu_rev_c_hand_assembly_camera2.jpg" alt="CMU Altium" style="max-width: 800px;"/>
</div>

## Prototype testing
The initial prototypes were then thoroughly tested using a breakout board to validate cell voltage readings and temperature analog inputs.
<div style="text-align: center;">
<img src="/images/cmu/CMU_rev_c_test_assembly.png" alt="CMU Rev C Test Assembly" style="max-width: 600px;"/>
</div>

## QEV-3 Adaptor
The adaptor for the previous generation car shown below connects the 10 cells, tying the remaining 4 cells together. It also has a temperature multiplexer to enable the CMU to read more tempearture cells for the larger battery assembly.
<div style="text-align: center;">
<img src="/images/cmu/cmu_qev3_carrier.jpg" alt="CMU Carrier QEV-3" style="max-width: 800px;"/>
</div>


## Pick and place assembly
We then worked with our pick and place sponsor, Taylormade Electronics, to pick and place enough CMU's for QEV-3, QEV-4 and several spares. Working with Cameron from Taylormade Electronics has been an invaluable experience. It has enabled my understanding of the full design and assembly lifecycle, seeing first hand impacts of design decisions and changes on ease of assembly and reliability. 

### Solder Paste Application
<div style="text-align: center;">
<img src="/images/cmu/cmu_paste.jpg" alt="CMU Solder Paste Application" style="max-width: 600px;"/>
</div>

### Pick and Place Setup
<div style="text-align: center;">
<img src="/images/cmu/cmu_pick_place_setup.jpg" alt="CMU Pick and Place Setup" />
</div>


### Assembled CMUs
<div style="text-align: center;">
<img src="/images/cmu/cmu_assembled.jpg" alt="CMU Assembled" style="max-width: 600px;"/>
</div>


# Schematics 
Not published. Please contact me for more information.

