# Op-Amp Over-Voltage Protection Circuit
**Type:** Analog Hardware Project  
**Tools:** LTspice, Breadboard, Multimeter  

## Overview
Designed and built a hardware overvoltage cutoff circuit that 
automatically disconnects a load when input voltage exceeds a 
set threshold. Built from first principles — simulated in LTspice 
first, then verified on breadboard.

## Problem Solved
Unprotected loads can be damaged when supply voltage spikes 
unexpectedly. This circuit detects overvoltage and cuts the load 
automatically with no microcontroller needed — pure analog 
hardware protection.

## How It Works
- R1/R2 voltage divider scales input voltage to safe range for op-amp
- LM358 op-amp compares scaled input against fixed Vref (4.5V)
- When input exceeds trip threshold → op-amp output swings LOW
- IRFZ44N NMOS MOSFET turns OFF → load is disconnected

## Verified Results
- Trip voltage: 9V (theory predicted 9V — perfect match)
- Vref: 4.5V (generated from 9V battery ÷ 2 resistor divider)
- Load voltage before trip: ~4V across R3
- Load voltage after trip: 0V confirmed

## Components
- LM358 dual op-amp (DIP-8)
- IRFZ44N N-channel MOSFET
- 4x 10kΩ resistors (voltage dividers)
- 100Ω load resistor (R3)
- 9V battery (Vref supply)
- Bench supply (variable V1 input)

## Files
- `/ltspice/overvoltage_cutoff.asc` — LTspice simulation schematic
- `/photos/breadboard.jpg` — working breadboard
- `/photos/trip_before.jpg` — multimeter showing load voltage before trip
- `/photos/trip_after.jpg` — multimeter showing 0V after trip

## Key Concepts Learned
- Comparator circuit design (Sense → Compare → React)
- Voltage divider as analog signal scaler
- MOSFET gate drive requirements
- Common ground rule in multi-supply circuits
- Real hardware vs simulation differences
