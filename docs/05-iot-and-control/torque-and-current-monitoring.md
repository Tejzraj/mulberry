# Torque and Motor Current Monitoring

## 1. What It Is
Torque and current monitoring involves the real-time measurement of the electrical current drawn by the prime movers (cutter motor and feed motor) to estimate instantaneous mechanical shaft torque, material shear resistance, and rotational drag.

## 2. Why It Matters
In electric motors (especially DC and permanent-magnet BLDC motors), electromagnetic torque is directly proportional to armature current:
$$\tau \approx K_t \times I_a$$
where $K_t$ is the motor torque constant ($N\cdot m / A$) and $I_a$ is the active current. Continuous current sensing provides a non-invasive, low-cost window into instantaneous cutting resistance without requiring expensive inline mechanical strain gauges.

## 3. Key Concepts & Electrical Architectures
- **Sensing Techniques**:
  - *Current Sense Shunt Resistor*: Low-resistance precision resistor (e.g., $10 \text{ m}\Omega$, 1%) placed on the low side of the motor H-bridge/inverter. High bandwidth, ultra-low cost ($< $1), requires differential amplification.
  - *Isolated Hall-Effect Current Sensor (e.g., ACS712 / ACS724)*: Galvanically isolated, non-intrusive, linear analog voltage output, moderate bandwidth (up to 120 kHz).
  - *Current Transformer (CT) / Hall Clamp*: Suitable for monitoring single-phase AC induction motors without breaking high-voltage line connections.
- **Signal Characteristics During Cutting**:
  - *Idling Current*: Baseline current drawn by mechanical friction of bearings, seals, and windage.
  - *Cutting Transient Spike*: Sharp current peak as the blade enters a stem, lasting 10–50 ms.
  - *Stall / Compaction Signature*: Sustained, steep ramp-up in current approaching locked-rotor rating when biomass binds or jams between blade and ledger plate.

## 4. Engineering Relevance: Real-Time Jam Prevention & Adaptation (Proposed Research)
- **Multi-Level Threshold Control Scheme**:
  ```
  Current Thresholds:
  [Level 1: Normal Cut]  --> Maintain target feed speed
  [Level 2: High Resistance] (e.g., thick woody stem) --> Temporarily slow feed roller by 30%
  [Level 3: Impending Jam] (e.g., current > 200% nominal for > 150 ms) --> Immediate feed stop & cutter torque boost
  [Level 4: Rotor Lock / Stall] (e.g., current > 350% nominal for > 50 ms) --> Emergency reverse feed roller for 300 ms, alert operator
  ```
- **Material-Density Adaptation (Proposed Concept)**:
  - By integrating current consumption over continuous 1-second rolling windows, the supervisory controller can estimate the incoming biomass bulk density and adjust feed velocity to keep mechanical cutting power within an optimal efficiency envelope.

## 5. Questions to Investigate
- What is the electrical response time (in milliseconds) from mechanical blade contact on a 10 mm stem to measurable current spike at the ADC pin?
- How much does temperature rise in the motor winding affect the torque constant $K_t$ during continuous operation?
- Can motor current ripple distinguish between a single hard stem cut and a dense mass of soft leaves?

## 6. Sources
1. Hughes, A., and Drury, B. (2019). *Electric Motors and Drives*, Newnes.
2. Mohan, N., Undeland, T.M., and Robbins, W.P. (2007). *Power Electronics: Converters, Applications, and Design*, Wiley.
3. Central Silk Board (CSB), *Technical Specifications for Sericultural Cutting Appliances*.
