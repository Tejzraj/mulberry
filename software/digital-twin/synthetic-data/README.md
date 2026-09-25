# Synthetic Telemetry & Fault Data Generation

This directory houses generators that simulate edge cases, abnormal mechanical events, and hazardous operational regimes without endangering physical equipment.

## Components
- `jam_generator.py`: Generates synthetic motor current and deceleration profiles representing severe stem choking.
- `blade_wear_emulator.py`: Generates simulated vibration FFT harmonics corresponding to progressive blade blunting and micro-chipping.
- `dataset_exporter.py`: Packages generated time-series into standard formats (Parquet / CSV / JSON) for training edge ML classifiers in `software/control-system/` and `software/computer-vision/`.
