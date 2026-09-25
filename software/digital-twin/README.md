# Digital Twin Software Architecture

This module implements the cyber-physical digital twin simulation, telemetry synchronization, synthetic data generation, and state observer pipeline for the smart mulberry cutting machine.

---

## Directory Structure

```
digital-twin/
|-- README.md                     # Architecture overview, data schemas, and execution workflows
|-- simulation/                   # Multi-physics models (kinematics, motor ODEs, biomass cutting physics)
|   `-- README.md
|-- shadow/                       # Real-time telemetry ingestion, shadow state sync, and EKF observer
|   `-- README.md
|-- synthetic-data/               # Generators for synthetic load spikes, jam faults, and sensor noise
|   `-- README.md
`-- visualization/                # 3D WebGL / Three.js model bindings and operator telemetry dashboard
    `-- README.md
```

---

## Subsystem Modules

### 1. `simulation/` (Multi-Physics Simulation Engine)
- **Kinematic Model**: Simulates rotary cutter drum angular acceleration, feed roller displacement, and blade-shear bar mechanical interaction.
- **Electromechanics ODE Solver**: Implements numerical integration (Runge-Kutta 4th order / SciPy `solve_ivp`) of motor equations:
  $$\frac{di}{dt} = \frac{1}{L} (V - R \cdot i - K_e \cdot \omega)$$
  $$\frac{d\omega}{dt} = \frac{1}{J_{eff}} (K_t \cdot i - B \cdot \omega - T_{cutting})$$
- **Biomass Resistance Engine**: Computes dynamic cutting forces based on input stem diameter distributions and moisture-dependent shear modulus.

### 2. `shadow/` (Real-Time Telemetry & State Shadowing)
- **Telemetry Ingestion**: Subscribes to MQTT topics (`mulberry/telemetry/sensors`, `mulberry/telemetry/actuators`) or reads ZeroMQ sockets from the edge gateway.
- **State Estimation (EKF)**: Extended Kalman Filter fusing physical current and vibration telemetry with virtual physics state predictions to estimate unmeasured parameters (e.g., instantaneous load torque, blade tip deflection).
- **Drift Tracker**: Compares real system deceleration vs. ideal simulated physics to detect mechanical anomaly or belt slip.

### 3. `synthetic-data/` (Synthetic Dataset Generation)
- **Fault Injection**: Simulates rare physical operating regimes (e.g., dry woody stem jamming, blade chipped edge, bearing chatter, sensor brownout).
- **Edge AI Pre-Training**: Emits synchronized time-series and labeled event logs to train downstream edge classification models (`software/computer-vision/` and `software/control-system/`).

### 4. `visualization/` (Live 3D & Telemetry Dashboard)
- **Web-Based 3D Render**: Displays a live 3D CAD/mesh representation of the cutter drum and feed rollers spinning synchronously with physical encoder telemetry.
- **Telemetry Overlay**: Real-time graphs showing phase current, vibration FFT, estimated blade wear metric, and automated safety alerts.

---

## Technical Standards & Interfaces
- **Language**: Python 3.10+ (NumPy, SciPy, Paho-MQTT, Pydantic) for simulation and shadow engine; JavaScript/TypeScript (Three.js, WebSockets) for 3D visualization.
- **Message Format**: Protocol Buffers / JSON over MQTT.
- **Synchronization Target**: < 100 ms telemetry latency from physical MCU event to virtual shadow update.
