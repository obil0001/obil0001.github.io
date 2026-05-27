---
layout: post
title: Autonomous Hybrid Propulsion Vessel (ASV)
description: Design, construction and field testing of an autonomous surface vessel for coastal environmental monitoring, featuring a propeller-sail hybrid propulsion system.
    I contributed across hull stability analysis, rigid wing sail aerodynamic design, keel and rudder structural design, power systems, and autonomous navigation integration.
skills:
  - Hydrodynamic & Stability Analysis
  - Aerodynamic Design (MATLAB)
  - Structural Analysis & FEA
  - Composite Manufacturing (Wet Layup)
  - Embedded Systems & Avionics
  - Autonomous Navigation (ArduPilot)
  - Power Systems Design

main-image: /asv_main.jpg
---

---
# Objectives
This is an ongoing final year project (FYP) completed as part of a team of four from the Department of Mechanical and Aerospace Engineering. The vessel — named *Shellington* — is a 1.211 m monohull autonomous surface vessel (ASV) designed for continuous coastal monitoring operations, capable of accommodating drop-in research sensor packages.

The motivation is the growing need for persistent, low-cost marine data collection in Australia's coastal environments, where traditional methods are resource-intensive and risk-prone. The ASV addresses this through hybrid sail-electric propulsion, achieving energy efficiency an order of magnitude better than thrust-only alternatives.

Key system requirements:
- Maintain net-positive energy balance over a full operation cycle
- Autonomously navigate to specified waypoints within a Circular Error Probable (CEP) of 10 m, performing loop manoeuvres
- Accommodate a 200 × 150 × 100 mm payload of up to 2 kg, with 15 W continuous supply

## Outcomes and Contributions

I contributed across the majority of the vessel's engineering design, including the hull stability analysis and waterline extension remediation, the full rigid wing sail aerodynamic design pipeline (implemented in MATLAB), keel structural analysis and ballast sizing, power system architecture, and autonomy stack integration and field testing.

The sail-based propulsion system demonstrated an average power demand of **47.23 W**, compared to an estimated **390–440 W** for an equivalent thrust-only configuration — an order-of-magnitude improvement in energy efficiency. Under sail, estimated operational endurance is **7.2 to 9.8 hours** on a single 22,000 mAh 6S LiPo battery (488.4 Wh capacity). The vessel successfully completed an autonomous waypoint navigation mission at sea, validating the full propulsion, control, and navigation stack.

### Hull Design & Stability

The supplied hull is a fibreglass skin with Soric core, 1.211 m LOA, 0.27 m beam, and a target draft of 0.12 m. The flat-bottom geometry presented significant stability deficiencies for a sailing application — a flat-bottom form produces a GZ curve that peaks at a very low heel angle and falls steeply, offering little reserve stability under sail loads.

To address this, a fibreglass waterline extension was applied to increase the effective waterplane beam, raising the second moment of waterplane area Ixx and consequently the metacentric radius BM and metacentric height GM. Stability was quantified using both a small-angle approximation (valid to ≤10°) and a wall-sided correction at moderate angles (10°–40°):

- Displaced volume: ∇ = 0.07463 m³
- Second moment of waterplane area: Ixx = 5053.39 × 10⁻⁶ m⁴
- Metacentric radius BM = 0.0677 m
- Metacentric height GM = 0.6759 m

The extended hull exhibited significantly improved GZ curve shape across the full 0°–40° operational heel range.

The internal load-bearing structure is a conventional bulkhead-and-stringer design, manufactured from 18 mm marine plywood and aluminium plate at high-stress regions. The hull skin uses Scotttech Flowcoat, a wax-additive marine coating for seawater and UV resistance.

### Rigid Wing Sail — Aerodynamic Design

The rigid wing sail aerodynamic design was implemented as a sequential MATLAB pipeline. The design is anchored by prescribed aerodynamic coefficients at a trim angle of attack β = 10°: CL = 1.0742, CD = 0.02534.

Key design parameters:

| Parameter | Value |
|---|---|
| Mast height (span) | 1.0 m |
| Taper ratio λ | 0.45 |
| Constant-chord root section limit | 0.30 m |
| Air density | 1.225 kg/m³ |
| Reference wind speed | 7 m/s at 1.2 m height |

The planform uses a two-zone chord distribution: a constant-chord root section to simplify the mast collar structural interface, and a linearly tapered tip section (λ = 0.45) to approximate an elliptical spanwise load distribution and minimise induced drag. Wind velocity follows a logarithmic atmospheric boundary layer profile over the sea surface (roughness length z₀ = 0.0002 m).

Strip-based force integration across N = 100 spanwise stations gave a total aerodynamic driving force of **13.57 N** in ideal conditions. Following a 9 cm height reduction to the sail base (required to improve heeling angle margins), the sail still delivers **12 N** of forward drive — well above the 2.93 N hull resistance — with a large safety factor retained.

A stepper motor and spur gear actuator system rotates and holds the sail at the prescribed angle of attack. The minimum gear ratio required was determined as G = 4.33 (rp = 30 mm, rg = 130 mm), delivering an output holding torque of 10.62 Nm against a required 9.846 Nm. Gear components are 3D-printed PLA for low cost and iterability, clamped to the mast via nut-and-bolt connections. The stepper motor is rated at τ_motor = 2.45 Nm, Irated = 3 A, Vrated = 3.6 V.

### Sail Manufacturing

The sail uses a composite skin-on-frame architecture. The internal skeleton is a cylindrical carbon fibre tube mast (primary bending and shear loads) with marine-grade plywood ribs laser-cut to the NACA airfoil profile. The external skin is five plies of 380 g/m² herringbone fibreglass applied by wet layup (resin-to-fibre ratio 100:32 by weight), bonding to the ribs to form a unified monocoque-like structure. The two sail halves were manufactured separately and joined with resin after internal assembly.

### Keel & Rudder

The fin keel has an aspect ratio AR = 1.69, span 420 mm, root chord 297 mm, tip chord 200 mm, and 6 mm uniform aluminium thickness. A trapezoidal planform shifts the centre of lateral resistance forward to balance the sail's centre of effort. The keel is attached to the hull via two 50 × 50 × 3 mm aluminium L-brackets and eight M8 bolts through the hull, with a 16 mm marine plywood backing plate and 4 mm aluminium stiffener plate to distribute the cyclic cantilever loads away from the GRP skin and into fatigue-resistant materials.

Ballast sizing was driven by the aerodynamic heeling moment (scaling as v²). With lever arm constrained to 420 mm by manufacturing limits, **6.65 kg of ballast** was required; the final lead bulb cast into a 316 mm × ⌀50 mm 316 stainless steel tube came out at **6.78 kg**. The keel was finished with 3D-printed fairings, metallic primer, and enamel paint.

The rudder uses a NACA0012 profile. A worst-case flat-plate analysis at maximum deflection and maximum hull speed gave a required holding torque of 4 Nm. The rudder shaft was initially unidirectional pultruded carbon rod (ϕ3 mm, torsional stiffness 70,685 Nm/rad); this was revised to steel, increasing torsional stiffness by 1900%. The shaft passes through a brass sleeve into the hull above the waterline, avoiding water ingress by hydrostatic pressure.

### Power & Avionics

The vessel uses a 22,000 mAh 6S1P 25C LiPo battery (nominal 488.4 Wh). Power is distributed across multi-rail architecture using buck converters and UBECs:
- 5 V regulated: telemetry radio, wind vane, Arduino mast controller
- 6 V regulated: rudder servo
- High-voltage rail: stepper motor driver
- Dedicated Mauch battery monitor for Cube Orange+ flight controller

The flight controller is a **Cube Orange+** running ArduRover (sailboat variant), with a **Here4 GPS** over DroneCAN CAN bus, and an **RFD900x** 900 MHz telemetry modem for long-range ground station communication. Mast rotation is controlled via an Arduino intermediary that converts PWM signals from the Cube into step/direction commands for the stepper driver, with a 10-turn 10 kΩ potentiometer providing closed-loop mast angle feedback.

Electromagnetic interference from the stepper driver was a significant issue during integration; resolved through physical separation of high-noise components, a shared aluminium grounding plate bonded to the keel structure, and additional bulk capacitance filtering throughout.

### Endurance Testing & Results

A one-hour hardware-in-the-loop (HITL) endurance test validated the power system:

| Parameter | Result |
|---|---|
| Test duration | 1 hour |
| SOC reduction | 5.1% – 8.1% |
| Estimated power consumption | 24.91 – 39.56 W |
| Final operating power (incl. 15 W payload) | 39.91 – 54.56 W |
| **Estimated endurance** | **7.2 – 9.8 hours** |

For fully energy-neutral continuous operation, approximately 453 W of installed solar capacity would be required (accounting for 50% real-world derating). For daytime-offset operation only, approximately 94 W of installed solar would suffice.

### Assembly & Sea Trial

{% include image-gallery.html images="/asv_assembly.jpg, /asv_sea_trial.jpg" height="400" %}

### Manufacturing

<!-- Add manufacturing photos here when available -->
{% include image-gallery.html images="/asv_manufacturing_1.jpg, /asv_manufacturing_2.jpg" height="400" %}

### Sail & Keel Detail

{% include image-gallery.html images="/asv_sail.jpg, /asv_keel.jpg" height="400" %}
