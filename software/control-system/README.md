# Supervisory Control System

This directory houses the supervisory control layer executing on the edge single-board computer (Raspberry Pi 5) or high-level microcontroller.

## Responsibilities
- User Interface / HMI: Instar selection mode (Chawki 1st/2nd, 3rd, 4th, 5th instar) and cut dimension setpoint configuration.
- Closed-Loop Adaptation Engine: Dynamic adjustment of target feed rate based on incoming biomass density and motor torque feedback.
- Telemetry & Data Logging: High-speed logging of cutting parameters, motor current curves, vibration metrics, and throughput statistics to local SQLite / CSV logs.
- System Diagnostics: State machine supervising operational readiness, fault detection, thermal monitoring, and blade health metrics.
