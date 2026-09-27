# Preliminary Bill of Materials (BOM) & Budget Estimation

> **Project**: Design and Development of a Compact Electric Plant Cutting, Gathering and Binding Machine for Future Mulberry Application  
> **Phase**: Stage 1 — Prototype-1 Mini Model (Proof of Concept)  
> **Target Prototype Budget**: **₹45,000 INR** (~$540 USD)

---

## 1. Prototype-1 Target Cost Breakdown

| Subsystem / Category | Key Included Components | Target Cost (INR) | % of Budget |
|---|---|---|---|
| **Battery & Power System** | 24V (~30Ah) LiFePO4 battery pack, BMS, charger | ₹9,000 | 20.0% |
| **Chassis & Fabrication** | MS square tubing (25×25×2mm, 8-12m), sheet metal, welding/machining | ₹8,000 | 17.8% |
| **Motors & Controllers** | 24V ~500W cutter motor, 24V ~250W geared traction motor, motor drivers | ₹7,000 | 15.6% |
| **Transmission System** | Shafts, UCP pillow blocks, chains, sprockets, pulleys, timing belts | ₹4,500 | 10.0% |
| **Binding Mechanism** | Spool mount, guide ring, small gear motor / actuator, twine tensioner, cutter | ₹3,500 | 7.8% |
| **Electronics & Sensors** | ESP32 MCU, Hall RPM sensor, ACS712 current sensor, wheel encoder, limit switches | ₹3,000 | 6.7% |
| **Wheels & Mobility** | Drive wheels (250–350mm dia), front caster / support skid assembly | ₹2,500 | 5.6% |
| **Cutter Assembly** | Rotary cutting blade, hub adapter, blade guard enclosure | ₹2,000 | 4.4% |
| **Safety & Miscellaneous** | Heavy-duty E-stop switch, main fuse, wiring, hardware fasteners, contingency | ₹5,500 | 12.2% |
| **TOTAL TARGET COST** | **Complete Prototype-1 Proof-of-Concept Machine** | **₹45,000** | **100%** |

*Note: Component pricing represents preliminary engineering estimates sourced from domestic Indian industrial and hobbyist suppliers. Actual procurement costs will be verified prior to final purchasing.*

---

## 2. Detailed Itemized Subsystem Breakdown

### 2.1 Mechanical & Frame Subsystem
- **MS Square Tubing**: 25 mm × 25 mm × 2 mm (8 – 12 metres required for chassis backbone and uprights)
- **MS Sheet Metal**: 1.5 – 2.0 mm thickness for gathering chute, deflector plates, and blade guard
- **Cutter Shaft**: Precision-turned mild steel or EN8 shaft (20–25 mm diameter)
- **Bearings**: UCP 204 / UCP 205 pillow-block ball bearings (self-aligning)
- **Plant Guide Rods**: 8 – 10 mm MS round bars angled into divergent wedge profile
- **Hardware & Fasteners**: Grade 8.8 M6/M8/M10 bolts, nyloc nuts, tension springs

### 2.2 Powertrain & Actuation Subsystem
- **Traction Drive**: 24V DC geared motor (~250W nominal, 30–60 RPM output)
- **Cutter Drive**: 24V DC motor (~500W, 3000–4000 RPM base speed) with 3:1 to 5:1 speed reduction
- **Motor Speed Drivers**: High-current dual H-bridge / PWM DC motor controllers (24V, 30–40A peak)
- **Binding Drive**: Small high-torque 12V/24V worm geared motor or linear actuator (~30–50W)

### 2.3 Electrical, Sensing & Safety Subsystem
- **Primary Energy Storage**: 24V LiFePO4 battery pack (~30Ah nominal, ~720 Wh) with built-in Battery Management System (BMS)
- **Microcontroller**: ESP32 Dev Module (Dual-core 240 MHz, Wi-Fi/Bluetooth, hardware timer PWM)
- **Current Sensing**: ACS712 (30A) or ACS724 Hall-effect current sensor module
- **Speed & RPM Sensing**: A3144 Hall-effect sensor with neodymium magnet disk on cutter shaft
- **Mobility Feedback**: Optical or magnetic quadrature encoder on drive wheel axle
- **Mechanical Endstops**: Micro-switch limit switches on binding ring and compression arms
- **Safety Interlock**: Latching red mushroom Emergency Stop (E-Stop) switch and 40A DC inline fuse

---

## 3. Market Cost Comparison

Indicative market prices in India for existing commercial harvesting and binding machinery:

| Equipment Category | Commercial Market Price Range (India) | Characteristics & Limitations |
|---|---|---|
| **Mini Power Reaper (Petrol/Diesel)** | ₹35,000 – ₹60,000 | Cuts crops (paddy/wheat) and lays them in windrows; **no gathering or binding** capability. |
| **Commercial Walking Reaper** | ₹1,30,000+ | High-throughput, heavy IC engine; non-modular, unwieldy for small plots, noisy. |
| **Commercial Reaper-Binder** | ₹2,40,000 – ₹5,00,000+ | Large self-propelled diesel machines for wheat/rice. Incompatible with sericultural row spacings or mulberry shoots. |
| **Proposed Electric Prototype-1** | **~₹45,000** | **Compact, battery-electric, zero-emissions, modular platform** validating cutting, gathering, and binding with low mechanical risk. |

> [!NOTE]
> This comparison does not claim equivalent industrial throughput. Commercial machines have high mass, high horsepower, and are designed for large cereal crop monocultures. The purpose of this student prototype is to pioneer an affordable, modular, clean-energy research platform specifically oriented toward the ergonomics and row constraints of sericultural mulberry farming.
