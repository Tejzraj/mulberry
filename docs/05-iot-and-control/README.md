# 05 - IoT, Sensing, and Control Systems

This directory focuses on sensory instrumentation, signal conditioning, actuator technologies, and closed-loop control architectures for the smart mulberry cutting machine.

## Document Index

1. [`sensor-research.md`](sensor-research.md) — Comprehensive comparative study of sensors (vibration, current, torque, acoustics, optical, environment) with full trade-off matrix.
2. [`vibration-monitoring.md`](vibration-monitoring.md) — Accelerometer placement, frequency spectrum analysis, unbalance detection, and mechanical chatter characterization.
3. [`torque-and-current-monitoring.md`](torque-and-current-monitoring.md) — Motor current sensing (Hall effect / shunt), dynamic torque estimation, stall detection, and anti-jam feedback.
4. [`acoustic-monitoring.md`](acoustic-monitoring.md) — Sound emission analysis, microphone hardware, acoustic signatures of clean shearing vs. crushing, and background noise cancellation.
5. [`actuator-research.md`](actuator-research.md) — Stepper motors, BLDC drives, pneumatic actuators, solenoids, and linear servos for adaptive mechanical regulation.
6. [`closed-loop-control.md`](closed-loop-control.md) — Fundamental closed-loop vs. open-loop architectures, end-to-end control flow, PID regulation, and dynamic feed adjustment routines.
7. [`digital-twin.md`](digital-twin.md) — Cyber-physical architecture, multi-physics kinematics and motor ODEs, biomass cutting resistance modeling, virtual commissioning, and live telemetry shadow state.

## Engineering Philosophy
- **Signal Fidelity First**: A sophisticated control or machine learning algorithm cannot compensate for a noisy, unshielded, or poorly placed physical sensor.
- **Sensor Redundancy**: Critical conditions such as mechanical jamming and safety guard breaches are monitored by dual, independent sensing modalities.
- **Empirical Validation**: Sensor utility and detection thresholds are treated as engineering hypotheses until verified on a physical test bench.
