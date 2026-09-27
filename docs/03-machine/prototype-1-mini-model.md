# Prototype-1: Mini Model Specification & Subsystems

> **Project**: Design and Development of a Compact Electric Plant Cutting, Gathering and Binding Machine for Future Mulberry Application  
> **Phase**: Stage 1 — Proof-of-Concept Mini Model  
> **Focus Vegetation**: Coriander, Congress Grass, and Soft-Stem Vegetation  

---

## 1. Executive Summary & Purpose

The **Prototype-1 Mini Model** serves as a modular, low-cost proof-of-concept platform designed to validate the complete automated sequence:

```
PLANT → GUIDE → CUT → GATHER → ALIGN → COMPRESS → BIND → RELEASE BUNDLE
```

Rather than jumping directly to high-torque cutting of mature, woody mulberry branches (which presents significant mechanical hazard, fabrication expense, and motor stall risks), Prototype-1 evaluates the electromechanical coordination on soft-stem plants. After physical validation, the modular subsystems (cutter, gathering geometry, transmission) can be incrementally scaled to handle thicker stems and ultimately woody mulberry shoots.

---

## 2. Preliminary Machine Dimensions & Mass Targets

| Parameter | Preliminary Target Range | Engineering Note / Constraint |
|---|---|---|
| **Overall Length** | 900 – 1100 mm | Accommodates gathering tray, binding ring, and operator handle |
| **Overall Width** | 500 – 650 mm | Sized for narrow crop rows and garden beds |
| **Overall Height** | 850 – 1000 mm | Ergonomic handle height for semi-autonomous / guided operation |
| **Cutting Width** | 300 – 400 mm | Front intake width matching guide teeth / divider |
| **Cutting Height** | 30 – 150 mm (adjustable) | Adjustable via front caster / skid mount |
| **Wheel Diameter** | 250 – 350 mm | High ground clearance for uneven soil |
| **Total Prototype Mass** | < 60 kg | Portable for student fabrication, transport, and safety |

---

## 3. Structural Frame & Chassis Design

### 3.1 Material Specification
- **Primary Material**: Mild Steel (MS) square tubing, **25 mm × 25 mm × 2 mm wall thickness**.
- **Material Requirement**: Approximately **8 – 12 metres** total linear length.
- **Joinery**: Welded joints with gusset reinforcement plates at high-stress motor and bearing mount locations.

### 3.2 Chassis Layout & Supported Assemblies
The welded MS chassis acts as a rigid backbone supporting:
1. **Front Sub-assembly**: Plant guiding fingers, rotary cutter housing, pillow-block bearings.
2. **Intermediate Sub-assembly**: Gathering conveyor/fingers and alignment compression chute.
3. **Rear Sub-assembly**: Twine spool, binding ring/actuator mechanism, bundle release gate.
4. **Lower Platform**: 24V LiFePO4 battery pack, traction motor, drive axle with pillow blocks.
5. **Upper / Handle Platform**: Electronic control enclosure (ESP32, motor controllers), emergency stop, operator push handle, and status indicators.

---

## 4. Mechanical Subsystems Breakdown

### Subsystem A: Plant Guiding Mechanism
- **Function**: Separates standing plants in the crop row and funnels stems smoothly toward the cutting blade without knocking them flat.
- **Design**: Two divergent MS / polymer guide rods / divider wedges positioned ahead of the cutter guard.

### Subsystem B: Cutting Mechanism
- **Type**: Modular, replaceable rotary cutter blade mechanism.
- **Drive Transmission**:
  ```
  24V DC Cutter Motor (~500W) 
        ↓
  Belt / Chain / Gear Reduction (Torque Multiplication)
        ↓
  Precision Ground Cutter Shaft (supported by UCP Pillow Blocks)
        ↓
  Rotary Cutting Blade
  ```
- **Rationale**: Direct drive is strictly avoided; high motor RPM must be reduced to an optimal torque-RPM operating envelope to prevent stalling under transient stem loads.
- **Safety**: Fully enclosed metal blade shroud with a front intake slit and rear deflector shield.

### Subsystem C: Gathering Mechanism
- **Function**: Captures severed plant stems and conveys them backwards toward the bundle-forming zone, preventing stems from falling onto the ground or tangling.
- **Configuration Options**: Rotating gather fingers, rubber-lugged conveyor belt, or oscillating sweep arms.
- **Target Clearance**: Smooth guide channels to prevent fibrous stems from wrapping around rotating shafts.

### Subsystem D: Alignment and Compression Chute
- **Function**: Gathers loose stems into an orderly parallel orientation and compresses them into a cylindrical bundle prior to binding.
- **Mechanism**: Funneling side guide plates, spring-loaded compression arms, and guide rollers.
- **Target Bundle Size**: **50 – 100 mm diameter** for Prototype-1 soft-stem materials.

### Subsystem E: Binding and Knotting/Twine System
- **Sequence**:
  ```
  Compressed Bundle → Wrap String → Tension String → Lock/Knot → Cut String → Release
  ```
- **Prototype-1 Implementation**: Semi-automated motorized binding ring. A rotating guide ring carries the twine around the compressed bundle; a tensioner maintains string tightness; an automated or solenoid-assisted cutter severs the twine.
- **Binding Material**: Biodegradable jute twine or synthetic agricultural string.

### Subsystem F: Traction & Mobility Drive
- **Configuration**: 2-wheel rear-drive with front swivel caster / skid plates.
- **Motor**: 24V geared DC motor (~250W) with high starting torque.
- **Drive Linkage**: Roller chain and sprocket reduction to rear live axle or dual independent geared hubs.
- **Operating Speed**: **0.2 – 0.5 m/s** (low speed for maximum control and safe evaluation).

---

## 5. Powertrain & Electrical Architecture

```
                       +-----------------------------+
                       |  24V, 30Ah LiFePO4 Battery  |
                       |          (~720 Wh)          |
                       +--------------+--------------+
                                      |
                         [ Main Fuse (40A/50A) ]
                                      |
                       [ Emergency Stop Switch (E-Stop) ]
                                      |
                       +--------------v--------------+
                       |   Power Distribution Bus    |
                       +------+-------+-------+------+
                              |       |       |
              +---------------+       |       +---------------+
              |                       |                       |
              v                       v                       v
      +---------------+       +---------------+       +---------------+
      |Traction Driver|       | Cutter Driver |       |Binding Driver |
      +-------+-------+       +-------+-------+       +-------+-------+
              |                       |                       |
              v                       v                       v
       Traction Motor           Cutter Motor          Binding Actuator
        (~250W DC)              (~500W DC)               (~50W DC)
```

- **Microcontroller**: ESP32 dual-core MCU (handling telemetry, motor PWM, sensor polling, safety lockouts).
- **Sensors Integrated**:
  - Hall-effect sensor on cutter shaft (RPM monitoring).
  - ACS712 / ACS724 Hall current sensor on cutter feed line (jam / stall detection).
  - Resistor divider voltage sensor (battery state of charge).
  - Wheel optical/magnetic encoder (distance and travel speed).
  - Mechanical / optical limit switches (binding ring travel and bundle release gate).

---

## 6. Safety & Risk Mitigation Protocols

1. **Immediate Blade Interlock**: Dual-redundant emergency stop cuts motor coil power in under 1.0 second.
2. **Rotating Component Guards**: 100% enclosure of chains, belts, sprockets, and rotating blades with removable inspection covers.
3. **Anti-Stall Current Cutoff**: ESP32 firmware monitors cutter motor current. If current exceeds 150% rated stall threshold for > 250 ms, the cutter is automatically stopped and an alert sounds.
4. **Safe Testing Environment**: Initial cutting trials will be conducted exclusively in a cordoned test plot with personal protective equipment (safety goggles, cut-resistant gloves, steel-toe boots).
