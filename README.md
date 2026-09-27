# Design and Development of a Compact Electric Plant Cutting, Gathering and Binding Machine for Future Mulberry Application

> **Project Positioning**: “Design and Development of a Compact Electric Smart Plant Cutting and Binding Machine with Modular Cutting, Gathering and Automated Bundling Mechanisms for Future Mulberry Application.”  
> **Development Strategy**: **Mini Model First** (Stage 1 Proof of Concept)  
> **Team**: Interdisciplinary Engineering Team (2 Mechanical, 2 CSE, 1 ECE)  
> **Current Status**: Prototype-1 Design & Specifications Phase  
> **Target Budget**: ₹45,000 INR  

---

## 1. Project Overview

The proposed project aims to design and develop a compact, self-propelled electric machine capable of cutting, gathering, aligning and binding plants into bundles. The ultimate objective is to develop a machine specifically suitable for mulberry plant/shoot cutting and bundling. However, the first prototype will be developed and tested using small and soft-stem plants such as coriander, Congress grass (*Parthenium hysterophorus*) and similar vegetation.

The first prototype acts as a proof-of-concept platform. It allows the team to validate the cutting, gathering, conveying, alignment and binding mechanisms at a lower cost and with lower mechanical risk. After successful validation, the same modular architecture will be upgraded with a stronger cutting mechanism, improved transmission and suitable gathering geometry for mulberry plants.

The proposed machine follows the operational sequence:

```
PLANT ──> GUIDE ──> CUT ──> GATHER ──> ALIGN ──> COMPRESS ──> BIND ──> RELEASE BUNDLE
```

The project combines **Mechanical Engineering**, **Electronics and Communication Engineering**, and **Computer Science/AI-ML**.

---

## 2. Problem Statement

Manual cutting and collection of plants requires significant labour and repetitive effort. In sericulture, harvesting mulberry leaves and shoots accounts for substantial operating costs and physical strain on farmers. 

Existing agricultural reaper and reaper-binder machines are generally designed for large cereal crops such as rice and wheat:
- They are bulky, heavy, petrol/diesel powered, and expensive (often ₹2.4 lakh to ₹5 lakh+).
- They are not optimized for the narrow inter-row spacings or cutting heights of mulberry plants.
- Commercial harvesters lack modularity and are too large for smallholder farming plots.

This project attempts to develop a compact and modular machine that can perform cutting and bundling operations automatically or semi-automatically. The first prototype will be designed for small plants and weeds, while the final objective is adaptation for mulberry cultivation.

---

## 3. Main Objective

The main objective is to design, fabricate and test a compact electric plant cutting and binding machine that can:

1. **Move** through a plant bed or row under controlled electric traction.
2. **Guide** plants smoothly toward the cutting mechanism without flattening them.
3. **Cut** the plant stems cleanly at an adjustable height.
4. **Gather** the cut material continuously into a collection chute.
5. **Align and compress** the cut material into a uniform cylindrical bundle.
6. **Wrap and bind** the bundle securely using string or twine.
7. **Release** the finished bundle onto the field.
8. **Monitor** important machine parameters electronically (current, RPM, battery, safety interlocks).
9. **Provide a modular platform** for future mulberry application.

---

## 4. Prototype Development Strategy

The project will be developed across five progressive stages to minimize failure risk and capital expense:

```
+------------------------------------------------------------------------+
| Stage 1: Prototype-1 (Mini Model)                                      |
| Test Material: Coriander, Congress grass, and soft-stem plants         |
| Primary Goal: Validate full cutting, gathering, binding mechanics      |
+-----------------------------------+------------------------------------+
                                    |
                                    v
+------------------------------------------------------------------------+
| Stage 2: Prototype-1.5                                                 |
| Test Material: Thicker weeds and semi-woody vegetation                 |
| Primary Goal: Optimize gathering clearances, motor torque, twine knots |
+-----------------------------------+------------------------------------+
                                    |
                                    v
+------------------------------------------------------------------------+
| Stage 3: Prototype-2                                                   |
| Test Material: Small mulberry shoots (tender green shoots)             |
| Primary Goal: Redesigned high-shear blade, reinforced drive shaft      |
+-----------------------------------+------------------------------------+
                                    |
                                    v
+------------------------------------------------------------------------+
| Stage 4: Field Prototype                                               |
| Test Material: Mulberry plants under controlled field conditions       |
| Primary Goal: Field terrain traction, row steering, bundle discharge   |
+-----------------------------------+------------------------------------+
                                    |
                                    v
+------------------------------------------------------------------------+
| Stage 5: Smart Mulberry Machine                                        |
| Test Material: Comprehensive mulberry harvesting operations            |
| Primary Goal: Edge AI/CV plant detection, auto cutting-height, IoT     |
+------------------------------------------------------------------------+
```

> [!NOTE]
> The first prototype is **not** expected to perform full-scale mature woody mulberry cutting. Its core purpose is to physically validate the fundamental cutting-gathering-binding sequence at low mechanical risk.

---

## 5. Proposed Machine Architecture

The recommended Prototype-1 power system is a clean **24V electric system**:

```
                  +---------------------------+
                  |   24V LiFePO4 Battery     |
                  +-------------+-------------+
                                |
                   [ Main Fuse (40A / 50A) ]
                                |
                   [ Emergency Stop (E-Stop) ]
                                |
                  +-------------v-------------+
                  |  Power Distribution Bus   |
                  +------+------+------+------+
                         |      |      |
         +---------------+      |      +---------------+
         |                      |                      |
         v                      v                      v
+-----------------+    +-----------------+    +-----------------+
| Traction Motor  |    |  Cutting Motor  |    | Binding Motor / |
|   Controller    |    |   Controller    |    |    Actuator     |
+--------+--------+    +--------+--------+    +--------+--------+
         |                      |                      |
         v                      v                      v
   Traction Motor         Cutting Motor         Binding Actuator
  (24V ~250W geared)    (24V ~500W + red.)      (12/24V ~30-50W)
         |                      |                      |
         v                      v                      v
    Drive Axle             Cutter Shaft          Binding Ring &
   & Wheels (2)          & Rotary Blades          Twine Cutter
```

- **Traction Motor**: Drives the wheels via chain/sprocket reduction for controlled speed.
- **Cutting Motor**: Drives the cutting shaft through a belt, chain, or gear reduction to match optimal torque-RPM requirements.
- **Binding Motor/Actuator**: Operates the rotating twine ring and string tensioning/cutting assembly.
- **Embedded Control**: An **ESP32 microcontroller** monitors sensors, regulates motor PWM, provides anti-stall protection, and logs telemetry.

---

## 6. Major Machine Subsystems

The machine is structured into 10 modular subsystems:

| Module | Subsystem Name | Key Function |
|:---:|---|---|
| **A** | **Main Chassis** | Welded 25×25×2 mm MS structural frame supporting all mechanical and electrical assemblies. |
| **B** | **Wheel & Traction System** | Dual drive wheels with geared DC motor delivering 0.2–0.5 m/s travel. |
| **C** | **Cutting System** | Replaceable rotary blade mechanism driven via speed/torque reduction transmission. |
| **D** | **Plant Guiding System** | Forward-projecting divider rods guiding stems smoothly into the cutter throat. |
| **E** | **Gathering System** | Conveying arms/fingers moving cut stems rearward to prevent field scattering. |
| **F** | **Alignment & Compression System** | Guide chutes and spring-loaded arms compressing stems into 50–100 mm bundles. |
| **G** | **Binding System** | Motorized ring and guide feeding twine, tensioning, tying/locking, and cutting. |
| **H** | **Battery & Power System** | 24V LiFePO4 battery pack (~30Ah, ~720Wh) with high-current BMS and main fuse. |
| **I** | **Electronic Control System** | ESP32 MCU executing motor PWM, sensor data acquisition, and state machine control. |
| **J** | **Sensors & Safety System** | Hall RPM, current overload sensor, wheel encoders, limit switches, and latching E-stop. |

*Modularity ensures that the cutting module can later be upgraded for woody mulberry stems without redesigning the chassis or powertrain.*

---

## 7. Main Frame & Chassis

- **Material**: Mild Steel (MS) square tubing, **25 mm × 25 mm × 2 mm** wall thickness.
- **Estimated Material Requirement**: **8 – 12 metres** based on CAD layout.
- **Mountings Supported**:
  - 24V Battery pack in a low center-of-gravity tray.
  - Traction motor and cutter motor mount plates with belt/chain tensioning slots.
  - Pillow-block bearings (UCP series) for cutter shaft and drive axle.
  - Gathering and alignment chute.
  - Binding mechanism sub-frame and string spool holder.
  - Ergonomic operator handle and electrical control box.
  - Steel sheet protective guards (covering all pinch points and rotating blades).

---

## 8. Preliminary Machine Dimensions & Technical Targets

| Parameter | Preliminary Target Value | Engineering Rationale |
|---|---|---|
| **Overall Length** | 900 – 1100 mm | Space for guiding, cutting, gathering, and binding in sequence |
| **Overall Width** | 500 – 650 mm | Compact footprint for standard agricultural rows |
| **Overall Height** | 850 – 1000 mm | Ergonomic handle height for operator guiding |
| **Cutting Width** | 300 – 400 mm | Sized for Prototype-1 intake throat |
| **Cutting Height** | 30 – 150 mm (adjustable) | Height adjustment via front skids / caster wheels |
| **Wheel Diameter** | 250 – 350 mm | High ground clearance over rough soil and weeds |
| **Target Prototype Mass**| < 60 kg | Portable for student workshop fabrication and safe testing |
| **Battery Energy** | 24V, 30Ah (~720 Wh) | LiFePO4 chemistry for lightweight safety and long cycle life |
| **Traction Motor** | ~250 W geared DC | High starting torque at low travel speed (0.2–0.5 m/s) |
| **Cutter Motor** | ~500 W DC motor | Ample torque after 3:1 to 5:1 reduction |

---

## 9. Cutting System

The cutting mechanism is central to the machine's reliability:

```
CUTTING MOTOR (24V, ~500W) ──> BELT / CHAIN REDUCTION ──> CUTTER SHAFT ──> ROTARY CUTTER BLADE
```

- **Torque vs. Speed Matching**: Direct motor coupling is avoided because DC motors spin at high RPM (3000–4000 RPM) where torque is insufficient to resist stem shear. A 3:1 to 5:1 reduction drops the shaft speed to 600–1000 RPM, multiplying torque to prevent stalling.
- **Shaft & Bearings**: Precision-ground steel shaft supported by two self-aligning pillow-block bearings (UCP 204).
- **Safety**: Fully shrouded cutting chamber with safety guards protecting the operator from flying debris.
- **Mulberry Upgrade Path**: For the future mulberry version, the cutter geometry, blade metallurgy (hardened tool steel), and shaft torque will be scaled based on measured cutting forces of woody shoots.

---

## 10. Gathering System

Severed stems must be systematically swept into the bundle-forming zone rather than scattered onto the ground:
- **Components**: Angled guide plates, rotating collection fingers/paddles, or rubber-lugged conveyor.
- **Geometry**: Funnels material smoothly into a narrowing throat without wrapping around rotating axles.
- **Clearances**: Designed with smooth internal walls to eliminate fiber snag points.

---

## 11. Alignment and Compression System

Before binding, stems must be gathered into a compact, parallel orientation:
- **Mechanisms**: Converging side guide plates, spring-loaded compression arms, and guiding rollers.
- **Target Bundle Size**: **50 – 100 mm diameter** for Prototype-1 soft-stem materials.
- **Compression Function**: Holds the stems under positive tension while the twine is wrapped, ensuring a tight, stable bundle that does not disintegrate upon release.

---

## 12. Binding System

The binding mechanism operates as a separate, modular unit:

```
CUT PLANTS ──> GATHER ──> ALIGN ──> COMPRESS ──> WRAP STRING ──> TENSION ──> LOCK/KNOT ──> CUT STRING ──> RELEASE
```

- **Prototype-1 Implementation**: Semi-automatic motorized binding ring.
- **Operation**: A spool supplies jute/agricultural twine through a tensioner. A rotating guide ring feeds the string around the compressed bundle.
- **Twine Cut & Release**: A small motor or solenoid-driven cutter severs the twine once secured, and the compression gate opens to release the finished bundle.
- **Full Automation Path**: Knotting/looping mechanism refinements will be phased in once cutting and gathering consistency is proven.

---

## 13. Traction System

- **Configuration**: 2-wheel rear-drive axle with front caster/skid support.
- **Power Flow**:
  ```
  24V BATTERY ──> MOTOR CONTROLLER ──> GEARED DC MOTOR (~250W) ──> CHAIN/SPROCKET ──> DRIVE AXLE ──> WHEELS
  ```
- **Operational Speed**: Kept strictly low at **0.2 – 0.5 m/s** to ensure stability, safety, and thorough cutting performance during trials.

---

## 14. Battery & Power System

- **Chemistry**: **Lithium Iron Phosphate (LiFePO4)**.
- **Specification**: **24 V nominal, ~30 Ah capacity (~720 Wh nominal energy)**.
- **Selection Rationale vs. Lead-Acid**:
  - Over 60% weight reduction for the same energy capacity.
  - Flatter discharge voltage curve under motor current draws.
  - Superior thermal and chemical stability in outdoor environments.
  - Cycle life exceeding 2000 cycles.
- **Safety**: Dedicated internal Battery Management System (BMS) with high-current isolation, inline fuse, and heavy-duty battery retention cage.

---

## 15. Electronics & Control System

The electronic architecture is centered around an **ESP32 dual-core microcontroller**:

```
                          +------------------------+
                          |       ESP32 MCU        |
                          +-----------+------------+
                                      |
       +------------------+-----------+-----------+------------------+
       |                  |                       |                  |
       v                  v                       v                  v
[ Motor PWM Control ] [ RPM & Speed ]     [ Current & Voltage ] [ Safety & State ]
- Traction driver     - Cutter Hall pulse - ACS712 cutter load  - E-Stop monitor
- Cutter driver       - Wheel encoder     - Battery divider     - Limit switches
- Binding actuator    - Travel velocity   - Overload cutoff     - Data logging
```

The ESP32 communicates operational telemetry (RPM, current draw, battery state of charge) wirelessly via Wi-Fi/Bluetooth to a mobile or laptop dashboard.

---

## 16. Sensors & Instrumentation Suite

1. **Hall-Effect RPM Sensor**: Digital latch on the cutter shaft to monitor blade velocity and detect speed drops under load.
2. **Current Overload Sensor**: ACS712 / ACS724 Hall-effect sensor inline with the cutter motor to trigger anti-stall shutdown.
3. **Battery Voltage Divider**: Precision analog voltage monitor for real-time State-of-Charge (SoC) tracking.
4. **Wheel Encoder**: Quadrature optical or magnetic encoder on the drive axle for travel speed and odometry.
5. **Limit Switches**: Heavy-duty microswitches for binding ring home position and bundle compression release.
6. **Height Adjustment Indicators**: Visual scale/switch for cutter height setting.
7. **Emergency Stop Switch**: Hardwired dual-circuit latching mushroom button.

---

## 17. Future AI & Computer Vision System

Once the mechanical and sensor foundation is proven reliable, the Computer Science team will integrate edge computer vision:

```
CAMERA ──> PLANT DETECTION ──> STEM REGION ──> HEIGHT ESTIMATION ──> DENSITY ESTIMATION ──> CUT DECISION ──> MACHINE CONTROL
```

- **Objective**: Identify plant rows, estimate stem thickness/density, detect obstacles, and dynamically adjust machine ground speed and cutting height.
- **Development Rule**: AI enhancements will be integrated in Stage 5, ensuring the physical machine operates reliably on mechanical and basic sensor control first.

---

## 18. Powertrain Comparison: Electric (EV) vs. Internal Combustion (IC)

| Feature / Criteria | Electric Prototype (Selected for Prototype-1) | Internal Combustion (IC) Machine |
|---|---|---|
| **Power Source** | 24V LiFePO4 rechargeable battery | Petrol / Diesel small engine |
| **Noise & Emissions** | Near-silent operation; zero local emissions | High engine noise, exhaust fumes |
| **Speed & Throttle Control** | Precise, instant electronic PWM control | Mechanical throttle cables and clutch |
| **Sensor & MCU Integration** | Seamless integration with ESP32 & telemetry | Requires external alternator and noise filtering |
| **Emergency Shutdown** | Instant electrical cutoff (< 1 second) | Mechanical kill switch or fuel valve shutoff |
| **Powertrain Maintenance** | Brush/bearing checks; zero oil/filter changes | Frequent oil changes, spark plugs, carb cleaning |
| **Vibration** | Minimal vibration; protects sensor mountings | Severe engine vibration; loosens fasteners |
| **Suitability for Student Team** | **Ideal for university lab fabrication & safety** | High mechanical complexity, fire/exhaust hazard |

*Note: While electric power is ideal for Prototype-1 development and indoor/outdoor lab testing, final powertrain choices for production mulberry machines will evaluate actual field duty cycles and energy requirements.*

---

## 19. Preliminary Bill of Materials (BOM)

```
Mechanical Subsystem:
├── MS square tube (25×25×2 mm, 8-12 m)
├── MS sheet metal (1.5-2.0 mm)
├── Drive wheels (250–350 mm dia) & caster/skid
├── Precision cutter shaft & drive axle
├── Pillow-block bearings (UCP 204/205)
├── Chains, sprockets, timing pulleys & belts
├── Shaft couplings, tensioners, springs & fasteners
├── Plant guide rods & diverter wedges
└── Replaceable cutter blade & protective sheet guards

Electrical & Control Subsystem:
├── 24V LiFePO4 battery pack (~30 Ah, ~720 Wh)
├── Battery Management System (BMS) & 24V charger
├── 24V DC cutter motor (~500W) & high-current controller
├── 24V DC geared traction motor (~250W) & controller
├── ESP32 microcontroller development board
├── Hall RPM sensor & ACS712/724 current sensor
├── Drive wheel encoder & mechanical limit switches
├── Heavy-duty latching Emergency Stop switch & 40A fuse
└── Step-down DC-DC buck converter, wiring harness & enclosure

Binding Subsystem:
├── Twine/jute spool & tensioning arm
├── Rotating guide ring / semi-automatic binding frame
├── Small geared actuator/motor (~30-50W)
├── Twine cutting blade & compression guide plates
└── Bundle release gate & return springs
```

---

## 20. Preliminary Cost Estimation

The target budget for the complete Prototype-1 proof-of-concept is **₹45,000 INR**:

| Category | Estimated Cost (INR) |
|---|---|
| 24V LiFePO4 Battery & BMS | ₹9,000 |
| Chassis Frame & Workshop Fabrication | ₹8,000 |
| Motors & Speed Controllers | ₹7,000 |
| Transmission (Shafts, Bearings, Chains, Belts) | ₹4,500 |
| Binding Mechanism Assembly | ₹3,500 |
| Electronics, ESP32 & Sensors | ₹3,000 |
| Cutting Blade & Adapter Assembly | ₹2,000 |
| Wheels & Axle Mounts | ₹2,500 |
| Safety Switches, Wiring, Fasteners & Contingency | ₹5,500 |
| **TOTAL ESTIMATED PROTOTYPE BUDGET** | **₹45,000** |

---

## 21. Market Cost Comparison

| Machine Type | Typical Indian Market Price | Capabilities & Limitations |
|---|---|---|
| **Mini Power Reaper** | ₹35,000 – ₹60,000 | Cuts crops and windrows them; no gathering or binding; noisy petrol engine. |
| **Commercial Walking Reaper** | ₹1,30,000 and above | Heavy, single-purpose, non-modular; unsuitable for sericulture plots. |
| **Commercial Reaper-Binder** | ₹2,40,000 – ₹5,00,000+ | Large diesel equipment built exclusively for rice/wheat monoculture. |
| **Proposed Electric Prototype-1** | **~₹45,000** | **Compact, electric, modular, cutting + gathering + binding proof-of-concept.** |

---

## 22. Performance Targets (Prototype-1)

- **Cutting Success Rate**: > 90% on soft-stem vegetation.
- **Gathering Success Rate**: > 85% of severed material collected into chute.
- **Binding Success Rate**: > 80% initially on compressed bundles.
- **Cutting Width**: 300 – 400 mm.
- **Ground Speed**: 0.2 – 0.5 m/s.
- **Bundle Diameter**: 50 – 100 mm.
- **Continuous Runtime**: At least 30 minutes on single charge.
- **Emergency-Stop Response Time**: < 1.0 second electrical cutoff.
- **Total Prototype Mass**: < 60 kg.

---

## 23. Progressive 9-Step Testing Plan

1. **Test 1: No-load Motor Test** — Verify motor speed, no-load current draw, vibration, and thermal stability.
2. **Test 2: Cutter Bench Test** — Test rotary cutting blade on soft stems; record RPM drop and current signature.
3. **Test 3: Mobility & Steering Test** — Assess traction, wheel slip, speed regulation (0.2–0.5 m/s), and chassis stability.
4. **Test 4: Plant Cutting Field Trial** — Test in standing patches of coriander and Congress grass.
5. **Test 5: Gathering Test** — Measure percentage of cut stems successfully conveyed without jamming.
6. **Test 6: Alignment & Binding Test** — Evaluate bundle uniformity, twine tension, knot/lock retention, and bundle release.
7. **Test 7: Battery Endurance Test** — Measure voltage sag, discharge curve, and operating duration under continuous duty.
8. **Test 8: Progressive Stem Thickness Test** — Gradually increase stem thickness/toughness to map the torque boundary of Prototype-1.
9. **Test 9: Controlled Mulberry Shoot Test** — Controlled test on young, tender mulberry shoots to empirically determine torque requirements for Stage 2.

---

## 24. Data Collection Protocol

For every field and bench trial, the team logs:
- Trial Number & Date
- Plant Type & Mean Stem Diameter (mm)
- Machine Travel Speed (m/s)
- Cutter RPM & Motor Current Draw (A)
- Cutting, Gathering, and Binding Success Rates (%)
- Battery Voltage (V) & Run Duration (min)
- Failure Modes & Engineering Observations

---

## 25. Team Work Distribution

| Team Member | Role | Core Deliverables |
|---|---|---|
| **Mechanical Student 1** | **Machine Design Lead** | CAD assembly, MS frame fabrication, shaft & bearing design, wheel traction mounting. |
| **Mechanical Student 2** | **Cutting, Gathering & Binding Lead** | Working cutter mechanism, gathering guides, alignment chute, semi-auto binding unit. |
| **CSE Student 1** | **Embedded & Control Lead** | ESP32 firmware, motor control PWM, sensor acquisition, anti-jam current cutoff, data logging. |
| **CSE Student 2** | **Computer Vision & Data Lead** | Telemetry dashboard, performance plots, image processing, future AI plant detection research. |
| **ECE Student** | **Power Electronics & Safety Lead** | 24V battery & BMS, motor drivers, power distribution bus, safety E-stop, electrical enclosure. |

---

## 26. 12-Week Project Roadmap

```
Week 01: Literature review, reference machine study, patent analysis.
Week 02: Vegetation stem measurements (coriander, Congress grass, mulberry); freeze specs.
Week 03: 3D CAD modeling of 25×25×2 mm MS chassis and rotary cutter.
Week 04: Mechanical design of gathering and binding units; electrical schematic.
Week 05: Engineering calculations (shaft, torque, gear ratios) & BOM finalization.
Week 06: Component procurement & workshop material sourcing.
Week 07: Fabrication of MS frame, wheel axle mounts, and motor brackets.
Week 08: Installation of cutter motor, shaft, blade, and gathering chute.
Week 09: Assembly of binding ring, twine tensioner, and structural safety guards.
Week 10: Installation of 24V battery, controllers, ESP32 MCU, and sensors.
Week 11: Integrated 9-step system testing, tuning, and failure logging.
Week 12: Final demonstration, data analysis, report submission & future mulberry upgrade plan.
```

---

## 27. Risk Management Matrix

- **Cutter Motor Stall**: Mitigated by belt reduction ratio, high-current sensing, and immediate firmware PWM cut-off.
- **Binding Mechanism Failure**: Mitigated by developing a semi-automated binding system first, calibrating twine tension before full knot automation.
- **Battery Overheating / Short Circuit**: Mitigated by certified LiFePO4 BMS, inline 40A fuse, and isolated steel battery compartment.
- **Plant Tangling / Jamming**: Mitigated by smooth internal guide chutes, zero exposed rotating axles in the flow channel, and accessible quick-release clearance gates.
- **Structural Vibration**: Mitigated by rigid 25×25×2 mm MS tubing, gusseted bearing supports, and dynamic blade balancing.
- **Budget Escalation**: Phased purchasing schedule with a dedicated 12% contingency buffer.
- **Scope Creep**: Prioritize mechanical cutting-gathering-binding MVP before introducing complex AI/CV layers.
- **Mulberry Cutting Premature Failure**: Soft-stem validation precedes all woody shoot testing; no unverified claims.

---

## 28. Safety Requirements

1. **Guards**: 100% enclosure of cutting blades, belts, pulleys, and chain sprockets with metal shrouds.
2. **Emergency Stop**: Hardwired, latching mushroom switch accessible from operator position (< 1 s cutoff).
3. **Electrical Safety**: Main fuse adjacent to battery positive terminal; insulated wiring channels.
4. **Interlocks**: Machine cannot be energized during maintenance or battery charging.
5. **Operating Protocol**: Operators must wear safety glasses, cut-resistant gloves, and safety shoes in marked test zones. No testing near bystanders or animals.

---

## 29. Future Mulberry Development (Post Prototype-1)

Following empirical validation of Prototype-1, the platform will be upgraded for mature mulberry cultivation:
- **Field Measurements**: Measure shear force, wood hardness, shoot diameter (8–20 mm), and moisture content of mulberry varieties.
- **Cutter Upgrade**: High-torque planetary gearbox, hardened high-carbon tool steel blades (58–60 HRC), reinforced cutter shaft.
- **Gathering & Chute Scaling**: Widened geometry to handle stiff, leafy mulberry branches without branch breakage.
- **Heavy-Duty Binding**: High-tensile twine and heavy bundle binding mechanism sized for mulberry shoot bundles.

---

## 30. Future Smart Features (Stage 5 Vision)

- **RGB / Depth Camera**: Row following and plant boundary detection.
- **AI Stem Sizing**: Automated estimation of stem diameter and cutting height.
- **Adaptive Ground Speed**: Real-time closed-loop speed regulation based on crop density.
- **IoT Cloud Dashboard**: Real-time field telemetry, motor thermal tracking, and predictive maintenance alerts.

---

## 31. Final System Vision: Smart Mulberry Machine

```
CAMERA ──> ROW & STEM DETECTION ──> CUTTING-HEIGHT ESTIMATION ──> CONTROLLED TRACTION
                                                                          │
                                                                          ▼
RELEASE BUNDLE <── AUTOMATIC BINDING <── COMPRESSION <── GATHERING <── CUTTING
      │
      ▼
PERFORMANCE TELEMETRY & DIGITAL TWIN MONITORING
```

---

## 32. Expected Final Outcome

At the conclusion of the Prototype-1 project phase, the team will deliver:
1. **A fully functional physical electric machine** demonstrating controlled mobility, cutting, gathering, compression, twine wrapping, and bundle release on soft-stem plants.
2. **Comprehensive sensor telemetry data** documenting motor current, cutter RPM, battery discharge, and travel speed.
3. **An empirical engineering evaluation report** with failure mode analysis and verified design equations.
4. **An actionable engineering roadmap** for upgrading the modular chassis to harvest full-scale mulberry shoots.

---

## 33. Project Positioning

> “Design and Development of a Compact Electric Smart Plant Cutting and Binding Machine with Modular Cutting, Gathering and Automated Bundling Mechanisms for Future Mulberry Application.”

The primary innovation lies in creating an **affordable, modular, clean-energy cutting-gathering-binding platform** that validates complex agricultural mechanics with low-risk soft-stem plants before systematically upgrading to sericultural mulberry harvesting.

```
PROTOTYPE ──> TEST ──> MEASURE ──> IMPROVE ──> UPGRADE ──> MULBERRY FIELD PROTOTYPE
```
