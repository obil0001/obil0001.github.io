---
layout: post
title: Automatic Plastic Recycling Shredder
description: This project involved the full mechanical design, analysis, and optimisation of a compact household plastic shredder to convert PET and HDPE waste into ≤5 mm fragments for 3D printing filament reuse.
    I led the majority of the design work, covering the shaft assembly, blade and spacer system, geartrain, FEA studies, and technical documentation across all analysis sections.
skills:
  - Mechanical Design & CAD (SolidWorks)
  - Power Transmission & Gear Design
  - Shaft & Bearing Analysis (ASME)
  - Structural & Fatigue FEA (SolidWorks Simulation)
  - Tolerance & Fit Analysis
  - Sustainability & Lifecycle Analysis
  - Technical Reporting

main-image: /shredder_assembly.jpg
---

---
# Objectives

This was a university machine design project (MEC3416) completed as part of a team of six. I led the majority of the design and analysis work. The goal was to design a compact, household-scale plastic shredder capable of processing common PET and HDPE waste plastics — such as 375 mL bottles — into fragments no larger than 5 mm in any dimension, suitable for reuse as 3D printing filament.

Key design requirements:
- Footprint: ≤ L500 × W500 × H400 mm (comparable to a household trash compactor)
- Throughput: ≥ 6 × 375 mL bottles per minute
- Output fragment size: ≤ 5 mm in any dimension
- Prototype unit cost: ≤ $500 AUD per unit (initial 50-unit production run)

The final optimised design achieved a throughput of 7.1 bottles/minute, exceeding the requirement.

## Outcomes and Contributions

I was responsible for the majority of the design and analysis on this project, including: the shaft assembly CAD and engineering drawings, cutting blade and spacer design, tolerance and fit selection, gear design and material verification, the full FEA study suite, and the sustainability analysis. I also led the technical write-up across most sections of the final report.

The full design cycle covered load analysis, motor and geartrain selection, shaft design and fatigue analysis, bearing selection, tolerance analysis, three FEA studies (static, fatigue, and topology optimisation), fastener analysis, and a lifecycle sustainability assessment.

The final unit cost was reduced from an initial estimate of $1,309 AUD down to $643.76 AUD per unit — significantly undercutting the comparable commercial MSMK2 manual shredder at $3,499.48 AUD.

### Cost Summary

| Component | Part/Material Cost (AUD) | Manufacturing Cost (AUD) | Total (AUD) |
|---|---|---|---|
| Worm Gear | $1.30 | $6.24 | $7.54 |
| Spacer | $2.60 | $8.78 | $11.36 |
| Side Blade | $50.00 | $20.16 | $70.16 |
| Side Spacer | $50.00 | $20.16 | $70.16 |
| Shaft | $16.21 | $0.64 | $16.84 |
| Gear 42T | $2.52 | $6.32 | $8.52 |
| Gear 31T | $2.52 | $8.26 | $10.78 |
| Front Wall | $20.00 | $33.50 | $53.50 |
| Blades | $39.60 | $10.20 | $49.80 |
| Gear 13T | $0.25 | $3.10 | $3.35 |
| Bearing Housing | $23.68 | — | $23.68 |
| Bearings | $156.40 | — | $156.40 |
| Bushing | $0.03 | — | $0.03 |
| Funnel | $91.32 | — | $91.32 |
| Lid | $91.32 | — | $91.32 |
| **Total** | | | **$643.76** |

### Cutting Mechanism

The shredder uses a staggered dual-shaft cutter configuration. Each alloy steel shaft is 20 mm in diameter and 300 mm long, carrying 10 cutter blades and 20 spacers secured with an H7/k6 transition fit and keyed connection. Only 2 blades per shaft are active at any one time — a deliberate design decision to significantly reduce required torque and make motor sizing feasible. A 5 mm mesh screen below the blades controls output fragment size. The dual-shaft arrangement ensures opposite rotation, producing an inward-pulling shear action on the plastic.

Blade geometry:
- Blade diameter: 100 mm
- Blade cutting area: 25 mm²
- Angle of attack: 67°
- Blade material: Alloy steel | Spacer material: 5052 aluminium

### Motor & Geartrain

Load analysis using PET (shear strength 33 MPa, yield 55 MPa) and HDPE (shear strength 15 MPa, yield 25 MPa) material properties established a required blade shaft torque of 247.5 Nm and a minimum blade shaft speed of ~8.3 RPM. A throughput model based on material removal rate and bottle geometry set the required engagement frequency for 6 bottles/min.

The final geartrain is a three-stage compound system:

| Stage | Components | Ratio |
|---|---|---|
| Motor → Worm shaft | 13T and 42T spur gears (module 1.5) | 3.2:1 |
| Worm gear pair | Worm (acts as 1T) → 31T gear | 31:1 |
| Worm → Blade shafts | Two 31T spur gears (module 6.35) | 1:1 (counter-rotating) |
| **Total** | | **99.2:1** |

This reduces 3000 RPM motor speed to ~30 RPM at the blade shafts. A manual crank handle is also incorporated via the worm shaft as a supplementary input.

Selected motor: **Unite MY1020 — 1 kW, 3000 RPM, 48V DC.** The calculated power requirement was 0.84–1 kW (safety factor 1.25–1.50 applied to 673 W theoretical); a 1 kW standard unit was selected for margin.

All gears are alloy steel. Bending stress FOS: 13T = 3.66, 42T = 5.33, 31T = 1.11 — all acceptable.

### Shaft & Bearing Analysis

Shafts were sized to 20 mm diameter per ASME standards. Critical speed: 6,514 RPM — operating speed of ~30 RPM is far below the 50% threshold, eliminating whirl risk. Fatigue analysis confirmed no failure under combined loading.

The worm gear shaft was the critical shaft, receiving the full geartrain load. Key results:
- Shear: τ_max = 6.58 MPa (large FOS)
- Bending: σ = 88.99 MPa, Von Mises = 89.72 MPa, SOF = 6.92
- Fatigue: Se = 249 MPa, SOF = 2.78
- Buckling under worm axial force (Fa = 9,190 N): σ_cr = 606.2 MPa vs σ_applied = 28.9 MPa — no buckling

Bearing selected: **SKF YAR 204-2F** (deep groove ball bearing with set screw). Dynamic load rating: 12.7 kN, limiting speed: 8,500 RPM, mass: 0.145 kg. Shaft-to-bearing fit: H7/n6 medium interference (press-fit assembly).

### FEA Studies

Three FEA studies were completed in SolidWorks Simulation:

**Lid optimisation:** Static study under 250 N hand load initially showed Von Mises stress of 33.36 MPa — exceeding the 1060 aluminium yield strength. An optimisation study on handle and lid base thickness dimensions (targeting FOS ≥ 2) reduced peak stress to 13.56 MPa and cut lid mass by approximately 50%.

**Gear shaft FEA:** Forces from the spur gear, worm loads, and shaft self-weight were applied at the correct locations. FEA result: 89.24 MPa Von Mises — closely matching the hand-calculated 89.71 MPa, validating the analytical model. Fatigue study: alternating stresses everywhere below the SN curve; no fatigue damage.

**Shaft and blade FEA:** Two-blade, one-shaft assembly modelled under 850 N normal blade forces. Max Von Mises stress: 167 MPa at the blade radius stress concentration, FOS = 3.7. Max displacement: 3.374 mm — attributed to system compliance (bearing flexibility, backlash) rather than material deformation. Fatigue study: no failure under zero-based cyclic loading beyond 10⁶ cycles.

### Safety & Maintenance

The funnelled lid guides plastic into the cutter chamber while fully shielding the user from moving blades. The geartrain and motor are mounted at the rear of the machine. The 5 mm mesh screen and collection drawer are secured with thumbscrews for tool-free removal. The shredder housing sits on the stand frame via locating notches — no fasteners required — allowing the box to be lifted away for full bottom access. Estimated maintenance times: ~10 minutes to clear a blockage, 30–60 minutes for a full blade replacement.

### Assembly & CAD

{% include image-gallery.html images="shredder_assembly.jpg, shredder_blades.jpg" height="400" %}

### Geartrain & Drawings

{% include image-gallery.html images="shredder_gears.jpg, shredder_cad_exploded.jpg" height="400" %}
