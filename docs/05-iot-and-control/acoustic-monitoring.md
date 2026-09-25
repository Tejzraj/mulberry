# Acoustic Emission and Sound Analysis

## 1. What It Is
Acoustic monitoring involves capturing and analyzing airborne sound waves (audio band: 20 Hz to 20 kHz) and structural acoustic emissions (ultrasonic band: 20 kHz to 500 kHz) generated during the cutting stroke, blade-ledger shear interaction, and plant tissue fracturing.

## 2. Why It Matters
When a plant stem or leaf lamina is severed by a sharp blade, it produces a distinct, high-frequency shear fracture acoustic signature. When the blade is dull, the material is crushed, torn, and folded against the ledger plate, producing a duller, lower-frequency compaction sound with extended decay. Acoustic sensing offers a completely non-contact modality to continuously monitor tool sharpness and cutting quality without placing mechanical strain on sensors.

## 3. Key Concepts & Acoustic Dynamics
- **Acoustic Regimes**:
  - *Clean Shear Fracture*: Crisp, short-duration impulse (< 15 ms), high spectral energy in the 2 kHz to 8 kHz band, rapid decay.
  - *Cellular Mashing / Tensile Rupture*: Protracted acoustic transient (30–80 ms), dominant low-frequency rumble (200 Hz – 1 kHz) caused by continuous friction and tearing.
  - *Tool-to-Tool Rubbing*: High-pitch squeal or narrow-band tone if blade-ledger clearance closes to zero and metal contacts metal.
- **Microphone Hardware & Enclosure**:
  - Industrial MEMS microphone (e.g., I2S digital output, Knowles / STMicroelectronics) or directional electret condenser.
  - Directional acoustic waveguide / horn aimed directly at the blade-ledger cutting zone, housed within an acoustically damped baffle to attenuate ambient farm noise.

## 4. Engineering Relevance: Feasibility & Noise Rejection (Proposed Research)
- **The Challenge of Ambient Agricultural Noise**:
  - Real sericulture rearing sheds include background noise from ventilation fans, human voices, nearby diesel tractors, and the cutting machine's own electric motor and gear train.
- **Proposed Noise Mitigation Strategies**:
  1. *Differential Microphone Array*: One primary microphone focused on the cutting zone and a secondary reference microphone capturing ambient room noise, using adaptive noise cancellation (ANC / spectral subtraction).
  2. *Ultrasonic Acoustic Emission (AE)*: Sensing above 30 kHz (above audible farm noise), where background interference is negligible and plant tissue fracture emissions are still prominent.
  - *Status*: Acoustic degradation monitoring is a **proposed concept to be experimentally tested** on the test bench.

## 5. Questions to Investigate
- What is the acoustic signal-to-noise ratio (SNR) in the cutting chamber during normal operation at 600 RPM?
- Can a standard 44.1 kHz 16-bit audio stream provide enough spectral resolution to distinguish between a fresh blade and a blade with 0.1 mm edge rounding?
- How much acoustic shielding is required to prevent ventilation fan noise from triggering false blade wear alerts?

## 6. Sources
1. Barber, A.D. (1992). *Handbook of Noise and Vibration Control*, Elsevier.
2. Teti, R., et al. (2010). *Advanced monitoring of machining operations: Acoustic emission and vibration*, CIRP Annals, 59(2), 717-739.
3. Central Silk Board (CSB), *Technical Reports on Farm Equipment Sound Emissions*.
