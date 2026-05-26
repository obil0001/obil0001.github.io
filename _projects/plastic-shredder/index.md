---
layout: post
title: Plastic Shredder Recycling Machine
description: Mechanical design and fabrication of a post-consumer plastic waste shredder, focusing on blade geometry optimization, power transmission sizing, and structural integrity for high-throughput material processing
skills:
  - Mechanical Design
  - Structural FEA
  - Power Transmission
  - Sustainability Engineering
  - Manufacturing & Fabrication
  - Motor Sizing

main-image: /shredder_main.png
---

---
# Objectives
Engineer and build a robust plastic shredding system capable of processing post-consumer plastic waste into recyclable granulate, minimizing material loss while maximizing throughput and operational reliability. The machine prioritizes sustainability impact through efficient energy consumption and compatibility with diverse plastic feedstock.

## Outcomes and Contributions
I led the mechanical design phase and was deeply involved in the fabrication and field testing of the shredder. The prototype successfully processed mixed plastic waste streams (HDPE, LDPE, PP, PET) at rates exceeding 15 kg/hour while maintaining consistent granule sizing. The design was optimized through iterative FEA validation and material testing, resulting in a system that operates reliably with minimal maintenance.

### Problem Statement & Sustainability Context
Plastic waste represents a critical environmental burden, with global landfill accumulation exceeding 350 million tons annually. This project focused on creating an accessible, locally-deployable recycling solution capable of processing post-consumer plastic at neighborhood scale. By converting waste plastic into consistent granulate, the system enables feedstock for 3D printing, injection molding, and other additive manufacturing workflows, closing the plastic loop.

### Shredding Mechanism & Blade Design
The core shredder employs a dual-blade counter-rotating architecture where hardened steel blades (HRC 58–62) operate at 200 rpm with a 5 mm cutting clearance. Blade geometry was optimized through CAD simulation and stress analysis to minimize binding while maximizing material throughput. Each blade features a serrated cutting edge with progressive tooth spacing, allowing coarse initial shredding followed by secondary size reduction.

We performed detailed FEA on the blade assembly to predict deflection under peak shear loads (estimated at 8 kN per blade during hard plastic engagement). Critical stress concentrations around blade root geometry were reinforced through chamfering and local thickness increases, reducing peak stress by 35% relative to baseline geometry.

### Power Transmission & Motor Sizing
A 2 HP brushless motor drives the blade assembly through a 10:1 spur gear reducer, providing 400 Nm of torque at the blade shaft. Motor selection was validated through power consumption modeling across realistic feedstock densities and plastic types. The gearbox was spec'd for continuous duty with oil bath lubrication, ensuring thermal stability even during extended processing runs.

Shaft design accounts for combined bending and torsional loads, with critical diameter sections determined via von Mises analysis. Bearing selection prioritizes longevity under contaminant ingress, employing sealed deep-groove ball bearings rated for 10,000+ hour service life.

### Structural Frame & Manufacturing
The frame is fabricated from 40×40 mm structural steel tube, welded into a rigid box structure with diagonal cross-bracing for torsional stiffness. FEA validation confirmed natural frequency well above the blade running speed, eliminating resonance risk. The entire frame undergoes powder-coat finish for corrosion protection in outdoor deployment scenarios.

Manufacturing employed standard shop processes: CNC plasma cutting for complex bracket geometries, MIG welding for frame assembly, and precision boring for bearing pocket tolerances (H7 basis). This approach ensures easy local fabrication without exotic tooling requirements.

### Performance & Operational Results
Field trials demonstrated 16 kg/hour throughput on mixed grocery-sourced HDPE/LDPE waste with consistent 5–8 mm granule sizing. Power consumption averages 1.8 kW during active cutting, with idle draw under 200 W. The system successfully processed contaminated plastic (labels, adhesive residue) without jamming, validating the robust blade design. Maintenance intervals exceed 200 operating hours between oil changes.

{% include image-gallery.html images="/shredder_cad.png, /shredder_build.png" height="400" %}
