# 03 - Machine Engineering & Mechanical Design

This directory covers the engineering problem definition, kinematics, mechanical cutting mechanisms, drive systems, blade dynamics, and safety standards for the smart mulberry cutting machine.

## Document Index

1. [`problem-definition.md`](problem-definition.md) — Comprehensive problem formulation: Current situation → Problems → Requirements → Possible automation → Research questions.
2. [`existing-cutting-methods.md`](existing-cutting-methods.md) — Benchmarking manual chopping, sickle cutting, chaff cutters, and motorized rotary cutters.
3. [`cutting-mechanisms.md`](cutting-mechanisms.md) — Mechanical principles: scissor shear, rotary drum cutting, anvil/guillotine impact, and specific cutting energy.
4. [`machine-requirements.md`](machine-requirements.md) — Functional and non-functional requirements (throughput, sizing, power, weight, hygiene, service life).
5. [`blade-systems.md`](blade-systems.md) — Metallurgy, edge geometries, shear clearance, wear patterns, resharpening, and acoustic/vibration wear signatures.
6. [`motor-and-drive-systems.md`](motor-and-drive-systems.md) — Power transmission, stepper/BLDC/AC motors, torque requirements, gearboxes, and speed modulation.
7. [`safety-requirements.md`](safety-requirements.md) — Operator physical protection, emergency braking, interlocking guards, electrical isolation, and agricultural safety standards (ISO 4254-1).

## Mechanical Design Philosophy
- **Evidence Before Design Lock**: No mechanical configuration (rotary drum vs. oscillating scissor vs. fly-knife cutter) is selected without empirical comparative analysis.
- **Biomass Adaptability**: The mechanism must accommodate high variability in stem diameter, fibrousness, and leaf moisture without stalling or jamming.
- **Operator Safety**: Industrial safety standards must be integrated from the first CAD concept, not retrofitted as an afterthought.
