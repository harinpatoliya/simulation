# Ammonia Production Simulation via Steam Reforming of Methane

## Overview

This repository contains the Aspen HYSYS simulation and supporting documentation for the ammonia production process via steam reforming, partial oxidation, and water–gas shift reactions, followed by ammonia synthesis. The simulation is based on a process description involving 100 kmol/h of pure methane (CH₄) feed.

## Process Description

The production process involves the following stages:

1. **Primary Reforming**  
   - Feed: 100 kmol/h CH₄ at 370°C and 3.45 MPa amd steam at 250°C
   - Steam-to-methane ratio: 2.5  
   - Reforming reactions at 930°C:
     - CH₄ + H₂O → 3H₂ + CO (43% conversion)
     - CH₄ + 2H₂O → 4H₂ + CO₂ (28% conversion)

2. **Secondary Reforming and Combustion**  
   - Combustor temperature: 930°C  
   - Air added at 20°C and 3.45 MPa to achieve H₂/N₂ = 3  
   - Additional steam used for temperature control  
   - Reactions:
     - CH₄ + 2O₂ → CO₂ + 2H₂O (100% conversion)
     - CH₄ + H₂O → 3H₂ + CO (35% conversion)
     - CH₄ + 2H₂O → 4H₂ + CO₂ (65% conversion)

3. **Water-Gas Shift Reactors**  
   - Two reactors: 450°C and 400°C  
   - Convert CO and H₂O to H₂ and CO₂
   - Reaction:
     - CO + H₂O ⇌ H₂ + CO₂ (equilibrium)

4. **Ammonia Synthesis**  
   - Gas compressed to 13 MPa and cooled to 270°C  
   - Reaction: 3H₂ + N₂ → 2NH₃ (30% N₂ conversion)  
   - Ammonia separated at 25°C in vapor-liquid separator  

## Simulation Tool

- **Software**: Aspen HYSYS
- **Version**: 12
- **Thermodynamic Model**: Peng-Robinson

## Inputs

- CH₄: 100 kmol/h
- Steam: As required per reaction step
- Air: Adjusted to maintain H₂/N₂ = 3

## Outputs

- Ammonia production: **66.52 kmol/h**
- Side products: CO₂, H₂O, unreacted H₂ and N₂ (recycled or vented depending on design)