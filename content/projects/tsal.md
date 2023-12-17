+++
title = 'Tractive System Active Light (TSAL)'
date = 2023-12-17T16:56:51+01:00
draft = false
showInHome = false
socialShare = false
toc = false
+++

# Introduction
The tractive system active light (TSAL) in FSAE requires a flashing red light on top of the vehicle when the bus voltage is greater than 60V. When the voltage is below zero the light should be solid green indicating a safe state. 

The TSAL must be visible in daylight from a distance, meaning fairly high powered LEDs are required. The team has an LED board designed for the top of the vehicle which requires 600mA.

### Location In Vehicle 
An important design factor. Traditionally QUT Motorsport placed their TSAL control board in the battery assembly on the vehicle side of the DC contactors. However, with the battery pack removed there is still a large capacitance in the vehicle at the motor controllers that could remain live for 10+ minutes if the discharge system fails. For this reason, the decision was made to place the TSAL control in the vehicle junction box, meaning the TSAL will show accurate tractive system voltage stage even with the battery pack removed.

# Solution
