# Isolated 10W Dual-Output Flyback Converter (8.0V / 2.1V)

## Overview
This project involves the design, calculation, and hardware implementation of an isolated flyback SMPS (Switched-Mode Power Supply) capable of delivering a total output power of ~10W across two regulated DC rails. The system converts a 220V AC input into isolated 8.0V and 2.1V outputs.

## Specifications
- **Input:** 220V AC (RMS)
- **Outputs:** - Rail 1: 8.0V @ 1.0A
  - Rail 2: 2.1V @ 1.0A (Tap-out from 8.0V winding)
- **Total Power:** 10.1W
- **Switching Frequency:** 132 kHz
- **Target Efficiency:** 74%
- **Measured Primary Inductance ($L_P$):** 1.335 mH

## Key Components
- **Controller:** TinySwitch-III **TNY275PN** (Integrated PWM and MOSFET)
- **Transformer:** Custom-wound **EE25 Ferrite Core** with a 0.5 mm air gap
- **Feedback:** **TL431** Shunt Regulator and **PS2505-1** Optocoupler for primary-side regulation
- **Rectification:** 1N4007-E Bridge Rectifier and SR360/1N5822 Schottky Diodes for secondary output

## Design Highlights
- **Stacked Winding Topology:** Utilized a stacked secondary winding to improve cross-regulation and efficiency between the 8.0V and 2.1V rails.
- **Transformer Construction:** - Primary: 83 Turns (#33 AWG)
  - Secondary: 1 Turn (#24 TIW) for 8.0V and 3 Turns (#25 TIW) for 2.1V
- **Feedback Loop:** The 8.0V rail is sensed via a TL431 error amplifier, which modulates the TNY275PN duty cycle to ensure stable regulation for both outputs.
- **Hardware Implementation:** Prototyped on a Zero PCB with optimized high-current paths to minimize parasitic inductance and EMI.

## Results
Experimental verification using a DSO and LCR meter confirmed:
- Steady-state regulated outputs of ~7.89V and ~2.37V.
- Transformer primary inductance of 1.335 mH, aligning with design calculations.

## 📁 Files Included
- `Flyback_Converter_Report.pdf`: Full technical documentation and calculations.
- `Schematic/`: Circuit diagrams and component identifications.
- `PCB_Design/`: Proposed trace layouts and 3D visualizations.
