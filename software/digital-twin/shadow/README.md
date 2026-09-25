# Real-Time Telemetry & Shadow State Synchronization

This directory contains services that ingest physical telemetry from the edge gateway, maintain a synchronized virtual shadow, and estimate unmeasured mechanical states.

## Components
- `mqtt_ingest.py`: High-throughput MQTT client subscribing to microcontroller sensor and actuator streams.
- `state_estimator.py`: Extended Kalman Filter (EKF) combining noisy sensor observations with physical ODE model predictions.
- `drift_detector.py`: Statistical process control comparing virtual model predictions against observed telemetry to detect mechanical degradation or belt slip.
