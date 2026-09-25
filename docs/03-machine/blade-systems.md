# Blade Systems and Edge Dynamics

## 1. What It Is
The blade system comprises the moving knives, stationary ledger bar (anvil), mounting hubs, tensioning mechanisms, and clearance adjustment hardware responsible for physical cutting in the machine.

## 2. Why It Matters
The blade is the primary tool-workpiece interface. Blade geometry, metallurgy, and edge sharpness govern cutting cleanliness, specific energy consumption, mechanical vibration, motor thermal load, and cellular bruising. A dull blade turns clean shear cutting into tearing and tensile rupture, directly degrading feed quality.

## 3. Key Concepts & Blade Engineering

### Metallurgy & Materials
- **High-Carbon Tool Steels (e.g., AISI D2 / SKD11)**: High wear resistance, 58–62 HRC after heat treatment; excellent edge holding, moderate corrosion resistance.
- **Martensitic Stainless Steels (e.g., AISI 440C, 420)**: High hardness (56–58 HRC), superior corrosion resistance against corrosive organic plant sap and sanitizing chemicals (chlorine/formalin). Recommended for sericulture contact.
- **Tungsten Carbide Inlays (WC-Co)**: Extreme abrasive wear resistance (68–72 HRC equivalent); brittle under sudden shock impact (e.g., if a stone or wire enters the hopper).
- **Surface Coatings**: Titanium Nitride (TiN) or Diamond-Like Carbon (DLC) physical vapor deposition (PVD) coatings to reduce friction coefficient and latex adhesion.

### Edge Geometry & Kinematics
- **Single vs. Double Bevel**: Single bevel (25°–30°) allows the flat side of the blade to slide flush against the ledger plate with minimal clearance.
- **Shear Clearance ($c$)**: Must be maintained between $0.05 \text{ mm}$ and $0.12 \text{ mm}$. If clearance expands beyond $0.2 \text{ mm}$, leaf laminae bend into the gap rather than cutting cleanly.
- **Helical / Oblique Edge Profile**: Helical blades on a rotary drum distribute the cutting force continuously along the cut stroke, replacing instantaneous impact shocks with continuous drawing shear.

### Wear Dynamics & Failure Modes
- **Abrasive Wear**: Driven by silica particles and dust adhered to field-harvested mulberry leaves.
- **Adhesive Wear & Gumming**: Latex and sap from mulberry stems adhere to blade faces, increasing frictional drag and dulling effective sharpness.
- **Micro-Chipping**: Brittle edge failure when processing thick, highly lignified basal stems.

## 4. Engineering Relevance: Blade Degradation Monitoring (Proposed Research)
- When a blade dulls:
  1. *Motor Current*: Peak and RMS current drawn by the cutting motor increase by 20% to 50% for equivalent biomass feed.
  2. *Vibration Spectrum*: Higher harmonic vibrations appear in bearing housings due to chatter and increased impact forces.
  3. *Acoustic Emission*: The acoustic signature shifts from a crisp high-frequency "snip" (shear) to a lower-frequency, broader thud/crush sound.
- *Status*: The automated monitoring of blade degradation using acoustic, vibration, or current sensing is a **proposed research direction** to be experimentally characterized.

## 5. Questions to Investigate
- What is the service life (in operating hours or kg of processed mulberry biomass) of AISI 440C blades before cut edge crushing becomes biologically noticeable?
- Can a simple passive gap adjustment mechanism maintain sub-0.1 mm clearance automatically under thermal expansion?
- What are the FFT frequency peaks associated with sharp vs. dull blade passes against the ledger bar?

## 6. Sources
1. Persson, S. (1987). *Mechanics of Cutting Plant Material*, ASAE Monograph.
2. Central Silk Board (CSB), *Machinery Standards for Sericultural Implements*, Ministry of Textiles, Govt. of India.
3. Trent, E.M., and Wright, P.K. (2000). *Metal Cutting* (4th ed.), Butterworth-Heinemann.
