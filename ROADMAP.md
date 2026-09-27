# Project Engineering Roadmap & Prototype Strategy

> **Project Title**: Design and Development of a Compact Electric Plant Cutting, Gathering and Binding Machine for Future Mulberry Application  
> **Development Philosophy**:  
> `PROTOTYPE → TEST → MEASURE → IMPROVE → UPGRADE → MULBERRY FIELD PROTOTYPE`

---

## 1. Five-Stage Progressive Prototype Strategy

Rather than building a full-scale machine for mature mulberry wood immediately (which carries high mechanical and financial risks), the project advances through five progressive stages:

```
+-----------------------------------------------------------------------+
| Stage 1: Prototype-1 (Mini Model)                                     |
| Test Material: Coriander, Congress grass, soft-stem vegetation        |
| Focus: Validate cutting, gathering, alignment, binding, release       |
+-----------------------------------+-----------------------------------+
                                    |
                                    v
+-----------------------------------------------------------------------+
| Stage 2: Prototype-1.5                                                |
| Test Material: Thicker weeds and semi-woody stems                     |
| Focus: Torque limits, gathering clearance tuning, twine knot strength |
+-----------------------------------+-----------------------------------+
                                    |
                                    v
+-----------------------------------------------------------------------+
| Stage 3: Prototype-2                                                  |
| Test Material: Small mulberry shoots (tender stems)                   |
| Focus: Upgraded cutter blades, reinforced shaft, motor load study     |
+-----------------------------------+-----------------------------------+
                                    |
                                    v
+-----------------------------------------------------------------------+
| Stage 4: Field Prototype                                              |
| Test Material: Mulberry plants under controlled sericulture field     |
| Focus: Field ground mobility, row alignment, bundle durability        |
+-----------------------------------+-----------------------------------+
                                    |
                                    v
+-----------------------------------------------------------------------+
| Stage 5: Smart Mulberry Machine                                       |
| Test Material: Full-scale mulberry crop                               |
| Focus: AI/CV plant detection, auto cutting-height, IoT digital shadow |
+-----------------------------------------------------------------------+
```

---

## 2. Twelve-Week Implementation Roadmap (Stage 1 / Prototype-1)

| Week | Milestone / Focus | Key Activities & Deliverables | Primary Responsible Roles |
|:---:|---|---|---|
| **Week 1** | **Prior-Art & Reference Machine Study** | Review reaper-binder patents, existing harvesting machines, and reference video mechanisms. Identify cutting, gathering, and binding principles. | All Team Members |
| **Week 2** | **Vegetation Characterization & Specs** | Measure stem diameters, cutting heights, and bundling specs for coriander, Congress grass, and mulberry baselines. Freeze initial parameters. | Mech Lead 1 & 2 |
| **Week 3** | **Chassis & Cutter CAD Modelling** | Create 3D CAD models of the 25×25×2 mm MS frame, wheel layout, and rotary cutter assembly. | Mech Lead 1 |
| **Week 4** | **Gathering, Binding & Electrical Architecture** | Design gathering chute, compression arms, binding ring mechanism. Finalize 24V electrical block diagram and schematic. | Mech Lead 2 & ECE Lead |
| **Week 5** | **Engineering Calculations & BOM Finalization** | Calculate shaft shear, torque requirements, bearing loads, reduction ratios, motor power. Finalize BOM (target ₹45,000) and verify suppliers. | Mech 1, Mech 2, ECE |
| **Week 6** | **Component Procurement & Material Sourcing** | Procure MS tubes, 24V LiFePO4 battery, motors, controllers, bearings, twine spool, ESP32, and safety switch. Begin fabrication prep. | All Team Members |
| **Week 7** | **Frame & Chassis Fabrication** | Cut, weld, and assemble MS chassis, wheel axles, pillow blocks, and motor mounting brackets. | Mech Lead 1 |
| **Week 8** | **Cutter & Gathering System Installation** | Mount cutter motor, shaft, blade, drive belts/chains, and front gathering guide plates. Conduct initial no-load spin test. | Mech Lead 1 & 2 |
| **Week 9** | **Binding Mechanism & Guards Installation** | Assemble semi-automatic binding ring, twine tensioner, cutting blade, and all structural protective guards. | Mech Lead 2 |
| **Week 10** | **Electrical, ESP32 & Sensor Integration** | Install 24V battery, BMS, motor controllers, E-stop, ESP32 MCU, Hall RPM sensor, and ACS712 current monitor. Complete wiring. | ECE Lead & CSE Lead 1 |
| **Week 11** | **Integrated System Testing & Tuning** | Execute progressive 9-step test plan (no-load → mobility → cutting → gathering → binding on soft stems). Measure RPM, current, slip. | All Team Members |
| **Week 12** | **Demonstration, Data Analysis & Reporting** | Demonstrate full automated sequence; compile telemetry and performance graphs; draft technical project report and Mulberry upgrade roadmap. | All Team Members |

---

## 3. Prototype-1 Progressive 9-Step Testing Plan

1. **Test 1: No-load Motor Test** — Measure RPM, current draw, vibration, and thermal rise for all motors.
2. **Test 2: Bench Cutter Test** — Validate cutting success, RPM drop, and current spikes on soft stems.
3. **Test 3: Mobility & Traction Test** — Evaluate speed (0.2–0.5 m/s), wheel slip, steering stability, and ground clearance.
4. **Test 4: Plant Cutting Field Run** — Test cutting in standing plots of coriander and Congress grass.
5. **Test 5: Gathering Efficiency Test** — Measure the percentage of cut material gathered into the chute (> 85% target).
6. **Test 6: Alignment & Binding Test** — Validate bundle compression (50–100 mm dia), string tension, knot/lock, and bundle ejection (> 80% target).
7. **Test 7: Battery & Electrical Duty Test** — Evaluate continuous runtime (> 30 min), voltage sag under load, and temperature.
8. **Test 8: Progressive Stem Diameter Test** — Incrementally increase stem hardness to map the mechanical torque boundary.
9. **Test 9: Controlled Mulberry Shoot Test** — Safe, controlled test on young tender mulberry shoots to establish empirical cutting requirements for Stage 2.
