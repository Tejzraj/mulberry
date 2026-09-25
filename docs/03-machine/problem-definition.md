# Machine Problem Definition

## 1. Current Situation
In sericultural farming across India and other major silk-producing regions:
- Mulberry feed preparation for young silkworms (Chawki: 1st and 2nd instars) is performed primarily by manual chopping using kitchen knives, hand sickles (*kathi*), or pedal-operated manual paper-cutter style guillotines on wooden cutting boards.
- For intermediate and late-age rearing (3rd to 5th instars), leaves or whole shoots are either fed uncut, chopped coarsely by hand, or fed into generalized motorized agricultural chaff cutters originally designed for cattle forage (sorghum, maize stalks).
- A commercial rearing batch of 100 Disease-Free Layings (DFLs) (~40,000 larvae) requires cutting and feeding approximately 900 to 1,100 kg of fresh mulberry foliage over 24 to 28 days, peaking at 150–200 kg/day during the 5th instar.
- Farmers typically spend 2 to 4 hours daily solely on leaf harvesting, cutting, and bed distribution during peak feeding periods.

↓

## 2. Problems
1. **Inconsistent Particle Geometry**:
   - Manual cutting results in substantial size variation across batches.
   - Oversized pieces cannot be consumed by young instars; undersized pieces desiccate prematurely.
2. **Cellular Bruising and Moisture Depletion**:
   - Dull blades or impact-based chopping mechanisms crush leaf mesophyll cells, releasing cellular sap that oxidizes into a darkened border.
   - Bruised foliage loses moisture rapidly in dry ambient air, rendering it unpalatable to larvae and lowering ingestion rates.
3. **Inability to Adapt to Larval Instar**:
   - Standard motorized forage choppers feature fixed-ratio gearboxes or single-speed cutters designed for cattle feed (yielding coarse chunks of 20–50 mm).
   - They cannot modulate feed particle dimensions down to 5 mm or dynamically switch between delicate leaf slicing and woody stem chopping.
4. **Mechanical Jamming and Variable Material Resistance**:
   - Mulberry biomass contains both succulent pliable leaves and fibrous, tough lignified shoots (diameters from 2 mm to 15 mm).
   - Wet, flexible leaves tend to wrap around rotating shafts, while dense basal stems cause sudden torque spikes, motor stalling, and belt slipping.
5. **Operator Ergonomics and Safety Hazards**:
   - Manual chopping involves repetitive wrist strain (repetitive strain injury) and knife laceration risks.
   - Traditional motorized chaff cutters frequently lack safety interlocks, contributing to severe hand and finger injuries in rural agricultural settings.
6. **Tool Degradation & Contamination Vectors**:
   - Unmonitored blade dulling leads to gradual degradation in cut cleanliness without operator awareness.
   - Machine accumulation of decaying leaf sap and lack of easy sanitization create disease vectors for silkworm pathogens.

↓

## 3. Requirements
- **Functional Requirements**:
  - *Adjustable Cut Length*: Continuously or incrementally adjustable from 5 mm (Chawki) up to 50–100 mm (late-age shoots).
  - *Clean Shear Action*: Scissor-like shear cutting with minimal clearance to eliminate cellular crushing and weeping edges.
  - *Material Flexibility*: Ability to process pure foliage, mixed leaf-petiole batches, and woody shoots up to 12 mm diameter.
  - *Throughput*: Target processing throughput scaled to farm size (e.g., 20–50 kg/hour for chawki/small farms; scalable to higher throughput for large operations).
- **Engineering & Operational Requirements**:
  - *Anti-Jamming Resilience*: Active sensing of material resistance with automated response (e.g., feed reversal or speed adjustment).
  - *Food-Grade / Washdown Construction*: Stainless steel contact surfaces (AISI 304) and washdown-safe electronics allowing daily disinfection with bleaching powder or formalin.
  - *Operator Safety*: Guarded feeding chutes, emergency stop switches, and physical interlocks complying with agricultural machinery safety guidelines.
  - *Low Power Consumption*: Compatible with single-phase rural electrical supplies (230V, 50 Hz) or low-voltage DC / battery backup systems.

↓

## 4. Possible Automation (Proposed Concepts — To Be Researched)
- **Computer Vision for Quality and Dimension Control**:
  - Proposed use of an edge camera to monitor input material condition (leaf tenderness vs. stem thickness) and verify output cut particle sizing.
- **Dynamic Torque/Current Feedback**:
  - Proposed continuous monitoring of drive motor current to detect material density spikes, anticipate jams, and automatically modulate feed roller speed.
- **Blade Degradation Monitoring**:
  - Proposed monitoring of acoustic emissions or high-frequency vibration signals during cutting cycles to infer blade sharpness degradation before cutting quality deteriorates.
- **Closed-Loop Actuation**:
  - Proposed micro-controller driven feed rollers and variable-speed cutter motors operating in a closed loop to dynamically maintain consistent cut length under varying feed densities.

*(Note: Every proposed automation feature remains a hypothesis to be experimentally validated; no architecture is locked).*

↓

## 5. Research Questions
1. What is the quantitative threshold of blade clearance and edge sharpness below which cellular sap exudation in cut mulberry leaves is eliminated?
2. How do current spikes in drive motors correlate with shear resistance across different stem diameters (4 mm, 8 mm, 12 mm)?
3. What is the minimum computational platform (e.g., 8-bit MCU, 32-bit ARM Cortex-M, or edge microprocessor) capable of executing real-time closed-loop feed regulation and jam detection?
4. What mechanical cutting geometry (rotary drum shear vs. counter-rotating disc blades vs. reciprocating guillotine) offers the lowest specific cutting energy and highest cut cleanliness?

## 6. Sources
1. Central Silk Board (CSB), *Hand Book of Sericulture Technologies*, Ministry of Textiles, Govt. of India (2014).
2. Kepner, R.A., Bainer, R., and Barger, E.L. (2005). *Principles of Farm Machinery*, CBS Publishers.
3. Srivastava, A.K., Goering, C.E., Rohrbach, R.P., and Buckmaster, D.R. (2006). *Engineering Principles of Agricultural Machines*, ASABE.
