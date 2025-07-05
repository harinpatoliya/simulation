# Acetic anhydride production from ketene

## Overview

This repository contains the Aspen plus simulation and supporting documentation for the speciality chemical acetic anhydride production process via ketene. First keten is produced from aceton, followed by purification and then synthesis of acetic anhydride.

## Process Description

The production process involves the following stages:

1. **Keten synthesis**  
   - Feed: 7850 kg/h CH₄ at 1035 K and 1.6 atm
   - Reactor: Adiabatic PFR reactor
              - volume is adjusted to get 20% conversion  
   - Power law reaction:
     - CH3COCH3 → CH2CO + CH4
     - Kinetic: 1.125 * exp((-285521.7/R) * (1/T - 1/1000))

2. **Compression of reaction products**  
   - compresssed to 3 bar pressure.
   - compression model: Polytropic using ASME

3. **Separation of keten and other gases**  
   - Absorption column with partial vapor-liquid condenser with feed from bottom
   - Methane is separateed from column top, unreacted aceton is separated fromm bottom.
   - Keten is obtained from condensor as a liquid
   - Parameter: 18 theoritical stages, bottom rate 6250 Kg/h (To recover almoost all acetone)
                -130 °C condensor temperature and column at 1.8 bar with no pressure drop

4. **Distillation of Ketene**  
   - Parameter: 12 theoritical stages, Distillate rate 150 Kg/h, Reflux ratio 3 (mole)
   -            Feed stage: 6, column pressure 1.8 bar    

5. **Synthesis of Acetic Anhydride**
   - CSTR reactor at 50 °C and 0.1 bar with 20000 l volume
   - Feed: 1) Keten from distillation column
           2) Fresh 27.44 Kmol/h acetic acid at 25 °C and 1 bar
   - Reaction: No kinetic informattion is available, so it is assumed that reaction attained it equllibirum.
           C2H2O + CH3COOH → C4H6O3


## Simulation Tool

- **Software**: Aspen Plus
- **Version**: 12
- **Thermodynamic Model**: WILS-NTH
