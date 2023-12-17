+++
title = 'SiC Inverter - Honours Thesis - QUT Motorsport'
date = 2023-12-17T16:56:51+01:00
draft = false
showInHome = false
socialShare = false
toc = false
+++

# Introduction
FSAE vehicles, such as the QUT Motorsport vehicle, use four motors, one in each motor hub. This enables better delivery of torque and torque vectoring. As a result, these already small vehicles now have 4 relatively low powered motors. There are some existing solutions used by teams, such as the Bucher 60kW dual control unit, the Sevcon HVLP 20, and the VESC 100/250. However, these drives are made for auxiliary pumps and fans in larger buses and tractors, not meeting the packaging or performance requirements, or in the case of the VESC, designed for a skateboard, and so lacks the isolated safety requirements.  

The goal of this project was to design a robust, power-dense motor control solution that can fit into small vehicle spaces. The solution should minimise unnecessary complexity, focusing on delivering working and validated hardware


# Initial Design
Refer to thesis

# Solution
The final device assembly is shown below, with control board on top, interface breakout, gate drives and power PCB on the bottom. Aluminum section has been used as a heatsink for initial testing.

![Assembled Inverter with Dummy Heatsink](/images/inverter/inverter.jpg "Inverter Assembly")

# Low Voltage (600V) Testing
The goal was to perform double pulse testing to validate
- Turn on and turn off characteristics. Tuning of the on/off gate resistors on the drivers
- Turn on and turn off delays in digital and analog systems
- Deadzone calibration
- Phase current shunt calibration
- Delay in delta sigma modulator phase current from real current

## Test Setup
Testing at hazardous voltages, an isolation barrier between the test device and test interfaces was important. A basic enclosure was used as a physical barrier. An emergency stop was present to turn off the supply and connect a dicharge resistor across the capacitors.
![Test Setup](/images/inverter/complete_test_setup.jpg "Test Setup")

## Scope Connections
The below shows the test setup.
- The co-located control board during testing enables the MMCX +/- 50V probe to connect to the gate MMCX connector.
- VDS 0.200" probe connection connected to pre-made lead.  

![Iso Probe Setup](/images/inverter/isovu_scope.jpg "Iso Probe Setup")

A close up of the connection shows the MMCX connector, as well as an additional differential probe used to measure the delta sigma modulator output. 
![Scope Close Up](/images/inverter/measurement_close.jpg "Scope Close Up")