# Machine Technical Requirements

## 1. What It Is
The technical requirements specification establishes the functional, performance, physical, electrical, and environmental constraints that the smart mulberry cutting machine must fulfill to be viable in sericultural operations.

## 2. Why It Matters
Clear, quantifiable specifications prevent scope creep and ensure that mechanical sizing, motor selection, sensor integration, and software architectures directly satisfy real agricultural working conditions without unnecessary complexity or cost.

## 3. Key Concepts & Requirements Matrix

### Functional Requirements (FR)
- **FR-1: Variable Cut Length Range**: System must produce cut particle sizes across the biological spectrum:
  - Mode A (Chawki 1st/2nd Instar): 5 mm to 15 mm ($ \pm 15\% $ tolerance).
  - Mode B (Intermediate 3rd Instar): 20 mm to 35 mm.
  - Mode C (Late-Age 4th/5th Instar): 50 mm to 100 mm (or whole shoot sectioning).
- **FR-2: Throughput Capacity**:
  - Chawki mode: 15–30 kg/hour (sufficient for 100–300 DFL chawki centers).
  - Late-age mode: 50–120 kg/hour.
- **FR-3: Feed Material Flexibility**:
  - Must accept loose leaf bundles, whole tender shoots, and woody branches up to 12 mm diameter without manual pre-trimming.
- **FR-4: Clean Cutting Action**:
  - Cell rupture and visible sap bleeding along cut margins must be minimized (target < 5% crushed margin by surface area).
- **FR-5: Anti-Jam & Overload Protection**:
  - Real-time automatic detection of rotor stall or material compaction with automated reversal/clearance sequence in < 500 ms.

### Non-Functional Requirements (NFR)
- **NFR-1: Electrical & Power**:
  - Single-phase AC (220–240 V, 50 Hz, < 1.5 kW total peak power) or optional 24V/48V DC battery-compatible architecture for rural microgrid resilience.
- **NFR-2: Hygiene & Sanitization**:
  - All contact surfaces fabricated from AISI 304 stainless steel or FDA-compliant food-grade polymer.
  - Ingress Protection rating: minimum IP65 for cutting head and motor enclosures to permit high-pressure water/disinfectant washdown.
- **NFR-3: Physical Footprint & Ergonomics**:
  - Maximum dimensions: 800 mm (L) × 500 mm (W) × 900 mm (H).
  - Maximum weight: < 65 kg; mounted on lockable casters for portability within rearing premises.
  - Feed table height: 750–850 mm (ergonomically matched to 5th–95th percentile Indian adult operators).
- **NFR-4: Acoustic Noise**:
  - Operational noise level < 75 dBA at 1 meter distance (to prevent noise distress in silkworm rearing houses).
- **NFR-5: Operator Safety**:
  - Full compliance with agricultural safety guidelines: mechanical tunnel guarding preventing finger reach into cutting hazard zone; redundant emergency stop; dual magnetic interlock switches on hopper/covers.

## 4. Engineering Relevance
- These specifications dictate the motor sizing (minimum 750W–1100W drive for cutting drum; 100W–200W for feed rollers), gear reduction ratios, frame rigidity, and sensor sampling rates.
- The requirement for sub-15 mm chawki cutting simultaneously with 12 mm woody shoot cutting requires high mechanical stiffness: frame deflection must not allow blade-ledger clearance to open beyond 0.2 mm during maximum stem shear load.

## 5. Questions to Investigate
- What is the maximum peak power drawn during a single 12 mm stem shear event?
- What are the voltage fluctuation limits encountered in typical rural sericulture belts (e.g., Ramanagara, Kolar, Chittoor), and does the control system require a wide-input power supply (90–265V AC)?
- What is the cost target for the complete assembled unit to achieve a < 2-season return on investment (ROI) for a 100-DFL farmer?

## 6. Sources
1. Indian Standards Institution (BIS), *IS 11459: Specification for Power-Operated Chaff Cutter*, Bureau of Indian Standards.
2. ISO 4254-1: *Agricultural machinery — Safety — Part 1: General requirements*, International Organization for Standardization.
3. Central Silk Board (CSB), *Technical Specifications for Sericulture Appliances*, Ministry of Textiles, Govt. of India.
