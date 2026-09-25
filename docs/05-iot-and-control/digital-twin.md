# Digital Twin Architecture & Cyber-Physical Modeling

## 1. What It Is
In this project, the **Digital Twin** is a high-fidelity cyber-physical simulation and real-time virtual shadow of the physical smart mulberry cutting machine. It integrates 3D kinematic mechanisms, electromechanical drive dynamics, non-linear biomass comminution physics, and live IoT telemetry to mirror the state, operational health, and cutting performance of the physical asset.

```
+-----------------------------------------------------------------------------------+
|                            PHYSICAL ASSET (FIELD/LAB)                             |
|                                                                                   |
|   +-------------------+    +----------------------+    +----------------------+   |
|   |  Cutter Motor &   |    |  Sensors (Current,   |    |  Incoming Mulberry   |   |
|   |  Feed Rollers     |    |  Vibration, Camera)  |    |  Stems & Leaves      |   |
|   +---------+---------+    +----------+-----------+    +----------+-----------+   |
+-------------|-------------------------|---------------------------|---------------+
              |                         | (Telemetry Streams)       | (Physical Samples)
              | (Control Setpoints)     v                           v
+-------------|---------------------------------------------------------------------+
|             |          EDGE IOT GATEWAY & TELEMETRY BROKER                        |
|             |          (MQTT / Protobuf / WebSockets / ZeroMQ)                    |
+-------------|-------------------------+-------------------------------------------+
              |                         |
              | (HIL / Virtual Tuning)  v
+-------------v---------------------------------------------------------------------+
|                            DIGITAL TWIN (VIRTUAL ASSET)                           |
|                                                                                   |
|  +-----------------------------------------------------------------------------+  |
|  | Multi-Physics Simulation Layer                                              |  |
|  | - Kinematic & CAD Geometry (Shaft velocities, shear clearances)             |  |
|  | - Electromechanical Motor Model (Back-EMF, torque constant, current draw)   |  |
|  | - Biomass Cutting Physics (Stem shear resistance tau, diameter distribution)|  |
|  +-------------------------------------+---------------------------------------+  |
|                                        |                                          |
|  +-------------------------------------v---------------------------------------+  |
|  | Real-Time Shadow State & Telemetry Synchronization                          |  |
|  | - Tracks instantaneous load, blade RPM, and vibration frequency shifts     |  |
|  | - Virtual Sensor Estimation (Blade edge temperature, instantaneous torque)  |  |
|  +-------------------------------------+---------------------------------------+  |
|                                        |                                          |
|  +-------------------------------------v---------------------------------------+  |
|  | Predictive Analytics & Virtual Commissioning                                |  |
|  | - Software-in-the-Loop (SIL) / Hardware-in-the-Loop (HIL) control testing   |  |
|  | - Blade degradation & Remaining Useful Life (RUL) estimation                |  |
|  | - Synthetic sensor failure & jam scenario generator                         |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

---

## 2. Why It Matters & Where It Fits
Agricultural comminution machinery operates in harsh, highly variable environments. Physical prototyping and destructive testing of high-speed cutting blades on irregular biological materials (mulberry stalks with varying lignification) carry significant costs, hardware failure risks, and safety hazards.

The Digital Twin fits into the engineering and research lifecycle across 4 distinct phases:

### A. Pre-Hardware: Virtual Commissioning (Phases 4–6)
- **Kinematic & Clearance Verification**: Before machining steel parts, the virtual twin evaluates blade-to-shear-bar clearance tolerances (e.g., 0.05 mm – 0.20 mm) across thermal expansion regimes.
- **Drive Sizing Validation**: Simulates dynamic cutting torque requirements for maximum stem diameter bundles (15 mm) to verify motor torque-speed curves and gearbox reduction ratios.
- **Safety & Interlock Prototyping**: Validates emergency stop response times and guard enclosure interlocks virtually.

### B. Hardware-in-the-Loop (HIL) & Firmware Validation (Phases 6–9)
- **Virtual Plant Testing**: Connects the physical microcontroller (ESP32-S3 / STM32) to the simulated physics model over high-speed serial/CAN-bus.
- **Anti-Jam Routine Stress-Testing**: Injects simulated extreme material density surges and mechanical chokes to verify anti-jam feed-reversal firmware without breaking real blades or burning motor drivers.

### C. Live Telemetry Shadowing (Phases 9–11)
- **Real-Time Digital Shadow**: Ingests live telemetry (cutter current, accelerometer FFT, optical feed rate) over MQTT to mirror operational state with < 100 ms latency.
- **Virtual Sensing**: Derives unmeasurable internal parameters, such as instantaneous shear blade core temperature and micro-deflection under shock loads, using multi-physics observer models.

### D. Predictive Maintenance & Edge AI Synthetic Training (Phases 8 & 11)
- **Degradation Modeling**: Models cumulative blade edge wear as a function of cut cycles and stem hardness, predicting edge dullness before cellular bruising damages silkworm feed.
- **Synthetic Fault Generation**: Synthesizes edge cases (bearing spalling, unbalance, foreign stone ingestion, dull blade harmonic drift) to train and evaluate ML classifiers when physical defect datasets are scarce.

---

## 3. Mathematical & Multi-Physics Formulation

### A. Electromechanical Cutter Drive Subsystem
The cutter drum motor is modeled as a permanent magnet DC / BLDC prime mover:
$$V(t) = R \cdot i(t) + L \frac{di(t)}{dt} + K_e \cdot \omega(t)$$
$$J_{eff} \frac{d\omega(t)}{dt} = T_m(t) - T_{loss}(\omega) - T_{cutting}(t)$$
$$T_m(t) = K_t \cdot i(t)$$

Where:
- $V(t)$: Applied motor terminal voltage (V)
- $i(t)$: Motor winding current (A)
- $\omega(t)$: Cutter drum angular velocity (rad/s)
- $R, L$: Winding resistance ($\Omega$) and inductance (H)
- $K_e, K_t$: Back-EMF constant (V/(rad/s)) and torque constant (N·m/A)
- $J_{eff}$: Effective inertia reflected to motor shaft ($J_{rotor} + J_{drum} / N^2$) ($kg\cdot m^2$)
- $T_{loss}(\omega)$: Viscous and Coulomb friction ($B \cdot \omega + T_f$)
- $T_{cutting}(t)$: Dynamic load torque exerted by mulberry shearing (N·m)

### B. Biomass Cutting Resistance Model
The instantaneous cutting torque $T_{cutting}(t)$ depends on the blade engagement angle $\theta(t)$, stem radius $r_s$, cutting edge radius $R_c$, and variety-specific shear strength $\tau_{stem}$:
$$T_{cutting}(t) = \sum_{k=1}^{N_{stems}} F_{shear, k}(t) \cdot R_c$$
$$F_{shear}(x) = \tau_{stem}(M, \rho) \cdot A_{res}(x) + F_{friction}(x)$$

Where:
- $A_{res}(x)$ is the instantaneous cross-sectional area of stem material being severed at blade penetration depth $x$.
- $\tau_{stem}(M, \rho)$ is the ultimate shear strength (MPa), parameterized by stem moisture content $M$ (%) and lignification density $\rho$ ($g/cm^3$).
- $F_{friction}(x)$ represents normal blade-stem face friction.

### C. Blade Edge Degradation Model
Blade blunting is modeled using a modified Archard wear formulation parameterized by cumulative cutting work:
$$W_{edge}(t) = k_{wear} \int_0^t F_{shear}(\zeta) \cdot v_{blade}(\zeta) \, d\zeta$$
$$\Delta r_{edge}(t) \propto \frac{W_{edge}(t)}{H_{blade}}$$

Where:
- $r_{edge}$: Blade edge tip radius (sharp: 5–15 $\mu m$; dull: > 60 $\mu m$).
- $H_{blade}$: Blade surface hardness (Rockwell C / Vickers).
- $k_{wear}$: Empirical wear coefficient for mulberry fiber abrasion.

---

## 4. Cyber-Physical Digital Twin Architecture

| Layer | Component | Functionality | Technology Candidate |
|---|---|---|---|
| **Tier 1: Physical Asset** | Prototype Machine | Cuts biomass; outputs sensor signals and actuator feedback. | BLDC drive, stepper feed, shunt, accelerometer, optical camera. |
| **Tier 2: Edge Telemetry** | Edge Broker & Ingestion | Samples at deterministic rates; serializes and dispatches telemetry packets. | MQTT broker (Mosquitto), Protocol Buffers, WebSockets, ZeroMQ. |
| **Tier 3: Simulation Engine** | Kinematics & Multi-Physics | Computes dynamic equations of motion, cutting loads, and thermal drift. | Python (NumPy/SciPy), MATLAB/Simulink Simscape, PyBullet, or ROS2 Gazebo. |
| **Tier 4: State Estimation** | Extended Kalman Filter (EKF) | Combines noisy physical telemetry with physics equations to estimate unmeasured states. | C++ / Python algorithmic observer. |
| **Tier 5: Visualization & UI** | 3D Twin Dashboard | Renders live 3D orientation, speed, stress heatmap, and alerts for operators. | WebGL / Three.js / React Web Dashboard. |

---

## 5. Implementation Workflow: From Virtual to Physical

```
1. CAD & Kinematics Modeling (URDF / OnShape / FreeCAD)
                       |
                       v
2. Physics & Cutting Dynamics Parameterization (Python / Simulink)
                       |
                       v
3. Software-in-the-Loop (SIL) Firmware Evaluation (Simulated MCU)
                       |
                       v
4. Hardware-in-the-Loop (HIL) Real MCU Integration (CAN / Serial Test Harness)
                       |
                       v
5. Physical Prototype Commissioning & Telemetry Streaming (MQTT / InfluxDB)
                       |
                       v
6. Model Parameter Identification & Drift Calibration (Physical vs. Virtual)
                       |
                       v
7. Continuous Shadow State & Predictive Maintenance Execution
```

---

## 6. Hypotheses vs. Validated Capabilities

> [!IMPORTANT]
> The Digital Twin is currently in the **conceptual and mathematical formulation phase**. No dynamic simulation claim is verified until empirical sensor and mechanical test-bench datasets are captured.

- **Hypothesis 1**: An electromechanical motor model can predict cutter stall events > 50 ms in advance by monitoring rate-of-change of current ($di/dt$) during stem engagement. *(To be experimentally validated in Phase 6/9)*.
- **Hypothesis 2**: High-frequency vibration frequency shifts in the digital shadow will reliably correlate with physical blade edge blunting ($\Delta r_{edge} > 30 \mu m$). *(To be tested in Phase 7/11)*.
- **Hypothesis 3**: Synthetic sensor data generated by the physics engine can improve edge ML model robustness to rare jamming events. *(To be tested in Phase 8)*.

---

## 7. Open Research Questions
1. What is the minimum computational budget required to execute a real-time physics observer alongside live telemetry on an edge computer (e.g., Raspberry Pi 4 vs. Jetson Nano)?
2. How sensitive is the biomass cutting resistance model to variety-specific variations between V-1, S-36, and local wild cultivars?
3. What is the maximum acceptable latency between physical sensor sampling and digital shadow rendering for meaningful operator intervention?

---

## 8. References
- **REF-TWIN-01**: Grieves, M., & Vickers, J., *Digital Twin: Mitigating Unpredictable, Undesirable Emergent Behavior in Complex Systems*, Transdisciplinary Perspectives on System Complexity, Springer (2017).
- **REF-TWIN-02**: ISO 23247:2021, *Automation systems and integration — Digital twin framework for manufacturing*, International Organization for Standardization.
- **REF-CTRL-01**: Ogata, K., *Modern Control Engineering* (5th ed.), Prentice Hall (2010).
- **REF-MECH-02**: Srivastava, A. K., Goering, C. E., Rohrbach, R. P., & Buckmaster, D. R., *Engineering Principles of Agricultural Machines* (2nd ed.), ASABE (2006).
