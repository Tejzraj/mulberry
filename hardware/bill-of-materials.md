# Preliminary Bill of Materials (BOM)

> [!NOTE]
> This Bill of Materials represents a preliminary, exploratory estimate for the laboratory testbench and Phase 6 prototype instrumentation. Component selections and costs are subject to engineering revision following empirical trade-off studies.

---

## 1. Mechanical Subsystem

| Item # | Component Description | Specification | Qty | Target Unit Cost (INR / USD) | Status |
|---|---|---|---|---|---|
| M-01 | Rotary Cutter Drum Assembly | Cylindrical steel drum, 3 helical knife mounts, 150 mm dia × 250 mm length | 1 | ₹8,500 / $102 | Concept Design |
| M-02 | Helical Shear Blades | Hardened AISI 440C / D2 tool steel (58–60 HRC), single bevel 28° | 3 | ₹3,600 / $43 | Sourcing specs |
| M-03 | Stationary Ledger Bar (Anvil) | AISI D2 hardened shear plate with ground edge, clearance adjustment slot | 1 | ₹2,200 / $26 | Sourcing specs |
| M-04 | Fluted Intake Feed Rollers | Polyurethane fluted sleeve over steel core, spring-tensioned mounting | 2 | ₹3,000 / $36 | Concept Design |
| M-05 | Machine Chassis / Frame | 4040 / 3030 T-slot aluminum extrusion or welded mild-steel box section | 1 | ₹7,500 / $90 | Structural planning |
| M-06 | Cutting Chamber Enclosure | AISI 304 stainless steel sheet metal, hinged inspection hood | 1 | ₹6,000 / $72 | Safety planning |
| M-07 | Bearings & Housings | Heavy-duty pillow block bearings (UCP 205/206), double-sealed | 4 | ₹2,400 / $29 | Off-the-shelf |

---

## 2. Electromechanical & Drive Subsystem

| Item # | Component Description | Specification | Qty | Target Unit Cost (INR / USD) | Status |
|---|---|---|---|---|---|
| E-01 | Cutter Drum Motor | 48V DC, 1000W BLDC Motor, 3000 RPM nominal, Hall sensors | 1 | ₹9,500 / $114 | Research phase |
| E-02 | BLDC Motor Controller / Driver | 48V, 30A continuous, UART/PWM/CAN interface, regenerative braking | 1 | ₹4,500 / $54 | Research phase |
| E-03 | Feed Roller Stepper Motor | NEMA 34 High Torque (4.5 N·m) with 5:1 planetary gearbox | 1 | ₹5,500 / $66 | Research phase |
| E-04 | Stepper Motor Driver | Digital Microstepping Driver (e.g., DM860 / TMC5160) | 1 | ₹2,200 / $26 | Off-the-shelf |
| E-05 | Main Power Supply (48V) | 48V DC, 25A (1200W) Industrial SMPS | 1 | ₹5,000 / $60 | Off-the-shelf |
| E-06 | Auxiliary Power Supply (24V/5V) | 24V DC / 5A SMPS + DC-DC 5V Buck | 1 | ₹1,800 / $22 | Off-the-shelf |

---

## 3. Sensing & IoT Subsystem

| Item # | Component Description | Specification | Qty | Target Unit Cost (INR / USD) | Status |
|---|---|---|---|---|---|
| S-01 | Motor Current Sensor | ACS724 (50A, Hall-effect isolated) or INA240 current shunt module | 2 | ₹800 / $10 | Off-the-shelf |
| S-02 | Accelerometer (Vibration) | ADXL345 (SPI/I2C 3-axis) or industrial 4–20mA IEPE | 1 | ₹600 / $7 | Off-the-shelf |
| S-03 | Optical RPM Encoder / Hall | Hall proximity sensor with multi-pole magnetic target disc | 2 | ₹500 / $6 | Off-the-shelf |
| S-04 | Camera Module | Raspberry Pi Global Shutter Camera (Sony IMX296, C-mount lens) | 1 | ₹4,200 / $50 | Research phase |
| S-05 | Acoustic Microphone Module | I2S Digital MEMS Microphone (e.g., INMP441) with acoustic horn | 1 | ₹350 / $4 | Off-the-shelf |

---

## 4. Compute, Control & Safety

| Item # | Component Description | Specification | Qty | Target Unit Cost (INR / USD) | Status |
|---|---|---|---|---|---|
| C-01 | Low-Level Controller | ESP32-S3 DevKit (Dual-core 240MHz, FreeRTOS, CAN/UART/ADC) | 1 | ₹750 / $9 | Off-the-shelf |
| C-02 | Edge AI SBC | Raspberry Pi 5 (4GB RAM) + Active Heatsink Cooler | 1 | ₹6,800 / $82 | Bench evaluation |
| C-03 | Safety Relays & E-Stop | Latching Mushroom E-stop switch + Dual-channel safety contactor | 1 | ₹2,800 / $34 | Mandatory safety |
| C-04 | Interlock Switches | Magnetic non-contact safety door switches (IP67) | 2 | ₹1,500 / $18 | Mandatory safety |
| C-05 | Electrical Enclosure | IP65 Polycarbonate/steel hinged enclosure with cable glands | 1 | ₹2,500 / $30 | Off-the-shelf |

---

## Cost Summary (Preliminary Testbench)

- **Mechanical Subsystem**: ~₹30,700 ($368)
- **Drive Subsystem**: ~₹28,500 ($342)
- **Sensing Subsystem**: ~₹6,450 ($77)
- **Compute, Control & Safety**: ~₹14,350 ($173)
- **Estimated Prototype Total**: **~₹80,000 (~$960 USD)**
- *Commercial Target Target at Scale (1,000 units)*: **< ₹35,000 (~$420 USD)** achieved via consolidated sheet metal tooling, custom BLDC stator winding, integrated PCB, and volume procurement.
