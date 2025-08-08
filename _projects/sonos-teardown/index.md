---
layout: post
title: Retractable Landing Gear
description:  This was a collaborative project, design novel retractable landing gear, to specific requirements for our humanitarian drone

skills: 
  - Structural analysis
  - CAD
  - Structural FEA
  
main-image: /sys2.png
---

---
# Objectives 
Create a pair of BLDC motors that were exactly designed for our intended propeller torque spec and required power generation and beat the COTS solution.
## Outcomes and Contributions 
This project is still ongoing! But as of August 2025, I have performed extensive theoretical analysis, 2d and 3d EMAG FEA simulations, created Simulink Thermal Models, validated data, and optimized the proposed designs to exactly fit our spec!
### Technical Details
Much of these technical specs I will keep secret due to the nature of this project being intended for competition. However, I will tell you that this is a 12/8 slot pole BLDC motor that was primarily designed using Ansys Maxwell Software. These motors were designed for the sole purpose of being better than the OTS solutions, and to achieve that I focused on some key metrics, Efficiency and Mass. COTS solutions only currently achieve 400g and efficiencies hovering around 80%, where this solution should see masses of sub 200g and efficiencies approaching 95%.




### EMAG FEA 
{% include image-gallery.html images="/Fullsys.png, /Foot.png, /leadscrew.png" height="400" %}
