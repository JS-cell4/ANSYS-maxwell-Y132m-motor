# Y132M Induction Motor: Ansys Maxwell Transient FEA

Finite-element model of a Y132M three-phase, 4-pole, 7.5 kW (10 hp) squirrel-cage
induction motor built in 'Ansys Maxwell'. The 2D transient model is extended to
**Maxwell 3D** to study the instantaneous electromagnetic response of the machine.

## Overview

The motor is modelled in Maxwell 2D using the **Transient** magnetic solver
(Cartesian, XY geometry mode) and then fed into Maxwell 3D for a full 3D
instantaneous response study, including end effects that a 2D model cannot capture.

## Motor Specifications

 - Type  Y132M, three-phase squirrel-cage induction motor 
 -Rated power - 7.5 kW (10 hp) 
 - Poles - 4 
 - Synchronous speed - 1600 rpm  Rated slip - 0.04 (4 %) 
 - Rated rotor speed  ~1536 rpm (Ns x (1 - s)) 
 - Approx. rated shaft torque  ~46.6 N·m (P / omega) 

## Simulation Setup

### Maxwell 2D
- Solution type: Magnetic > Transient
- Geometry mode: Cartesian, XY
- Design name: `Maxwell2DDesign2`
- Stator and rotor geometry with slots, windings and rotor bars
- Three-phase winding excitation (voltage or current driven)
- Rotational motion band with the rotor speed set from the slip

### Maxwell 3D
- 2D model extended / imported into Maxwell 3D
- Transient solution for the instantaneous response, including end-winding
  and end-ring effects

## Results Obtained
- Instantaneous electromagnetic torque vs. time
- Phase currents (starting transient and steady state)
- Flux linkage and air-gap flux density
- Flux density distribution plots across stator and rotor
- Rotor speed build-up and torque ripple

## Requirements
- Ansys Electronics Desktop (Maxwell 2D / 3D)
- Transient solver licence

## How to Run
1. Clone the repository.
2. Open the `.aedt` project in Ansys Electronics Desktop.
3. Select `Maxwell2DDesign2` (Transient) and click 'Analyze'.
4. Open the Maxwell 3D design and run the analysis.
5. View results under Results > Create Transient Report.

## Related Work
Simulink model of an inverter-fed (SPWM) three-phase induction motor drive.
Add the link to your Simulink repository here.

## Possible Extensions
- Inverter-fed excitation through Maxwell-Simplorer/Twin Builder co-simulation
- Core loss and efficiency map
- Thermal coupling with Ansys Icepak
- Skewed rotor analysis and harmonic study

