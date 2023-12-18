+++
title = 'Battery Management Unit (BMU)'
date = 2023-12-17T16:56:51+01:00
draft = false
showInHome = false
socialShare = false
toc = false
+++


# Introduction

Battery Management Unit
- Talks to slave cell monitoring units (CMUs) over IsoSPI
- Filters and monitors reported cell voltages and tempeatures
- Runs cell balancing algorithm
- Interface to charger to put BMU in charge state and take commands from charger about when to pre-charge
- Has shutdown interface for Insulation Monitoring Device (IMD), precharge resistor thermal sensor (PDOC), connector interlocks, and BMU battery state. Detection for these interfaces. 


Joint project with Jarrod Fisher. 



# Design Requirements

## FSAE Rules 2023

### BMU Rules



### Voltage Separation
- The GLV and the Tractive circuits must be galvanically isolated 

<div style="text-align: center;">
<img src="/images/tsal/FSAERuleVoltageSeparation.png" alt="Voltage Separation FSAE Ruleset 2023" style="max-width: 800px;"/>
</div>

### PCB Clearance
- 12.7mm clearance over uncoated surface, or 4mm clearance under conformal coating
<div style="text-align: center;">
<img src="/images/tsal/GLVTSClearance.png" alt="Clearance FSAE Ruleset 2023" style="max-width: 800px;"/>
</div>



## IPC Design Requirements for TS to TS clearances
- 3mm clearance over surface for non conformal coated 600V nets
- 1.105mm clearance over surface for conformal coated 600V nets

## Team Design Requirements
In Progress


# Design Solution
![BMU](/images/bmu/BMU_Cropped.jpg "BMU")


# PCB Layout 
Layer view - Ground plane layers Mid Top and Mid Bottom hidden
![BMU](/images/bmu/BMULayerView.png "BMU")


# Schematics 
In Progress
