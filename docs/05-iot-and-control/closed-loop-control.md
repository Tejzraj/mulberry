# Closed-Loop Control Architecture

## 1. What It Is
Closed-loop control is an engineering methodology where the operational outputs and mechanical states of a machine are continuously measured by sensors and compared against desired target setpoints, feeding error signals back into a controller to automatically adjust system actuators in real time.

## 2. Why It Matters
Traditional agricultural cutters operate in open loop: motors spin at fixed RPM regardless of whether the incoming material is soft foliage, wet tangled stems, or tough woody shoots. When resistance spikes, an open-loop machine stalls, jams, trips circuit breakers, or damages drive belts. A closed-loop smart cutter continuously monitors process variables and dynamically modulates feed velocity, motor torque, and clearance to prevent jams, optimize cut cleanliness, and adapt to varying biomass.

## 3. Key Concepts: Open-Loop vs. Closed-Loop Systems

### Open-Loop Control
- In an **open-loop system**, the control action is entirely independent of the system output.
  ```
  [User Setting: 10 mm Cut] ──> [Fixed Motor Speed Command] ──> [Motor Spins] ──> [Leaves Cut]
                                                                                       │
                                                                           (No feedback verification)
  ```
- *Consequences*:
  - If biomass density doubles, the feed rollers may slip, leading to uneven cuts.
  - If a 12 mm woody shoot enters the blades, the motor stalls and burns out or blows a fuse.
  - If blades dull, cut edges tear and bruise, but the machine continues operating without warning.

### Closed-Loop Control
- In a **closed-loop system**, sensors continuously measure output and internal states, computing an error term:
  $$e(t) = \text{Setpoint}(t) - \text{Measured Process Variable}(t)$$
  and adjusting actuator commands to drive the error toward zero.

### The Complete End-to-End Control Pipeline
The core architecture of the smart mulberry cutting machine is structured as an iterative feedback loop:

```
+-----------------------------------------------------------+
|                         Sensing                           |
|       (Optical Camera, Hall Current, RPM, Accelerometer)  |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                    Data Acquisition (DAQ)                 |
|        (ADC Sampling @ 1 kHz, Image Capture @ 30 FPS)     |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                     Feature Extraction                    |
|      (RMS Current, FFT Spectral Energy, Leaf Area Mask)   |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                 AI / Rule-Based Decision                  |
|    (Instar Sizing Rule, Jam Warning, Tool Wear Estimator) |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                        Controller                         |
|           (PID Speed Controller, State Machine)           |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                         Actuator                          |
|         (BLDC Inverter PWM, Stepper Pulse Generator)      |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                    Mechanical Response                    |
|    (Feed Roller Slows / Blade Speeds Up / Blade Clears)   |
+-----------------------------------------------------------+
                              │
                              ▼
+-----------------------------------------------------------+
|                  New Sensor Measurement                   |
|          (Current Stabilizes, Target RPM Restored)        |
+-----------------------------------------------------------+
```

## 4. Engineering Relevance & Multi-Loop Control Topology
The smart cutter incorporates two nested feedback loops:
1. **Inner High-Speed Loop (Firmware / Microcontroller, 1 kHz)**:
   - Proportional-Integral-Derivative (PID) motor speed regulation.
   - Fast overcurrent trip and active current limiting to prevent motor stall within < 20 ms.
2. **Outer Supervisory Loop (Embedded SBC / Edge AI, 10–30 Hz)**:
   - Optical biomass inspection: checks leaf area flow rate and signals the inner loop to accelerate/decelerate feed rollers.
   - Long-term tool health tracking: logs vibration RMS drift over minutes to update tool wear indices.

## 5. Questions to Investigate
- What are the optimal PID tuning parameters ($K_p, K_i, K_d$) for feed roller velocity response under varying stem load shocks?
- How much control delay is introduced by FIR filtering on motor current measurements before passing into the anti-jam state machine?
- What are the stability boundaries of the closed loop if the feed roller encounters slipping wet leaves?

## 6. Sources
1. Ogata, K. (2010). *Modern Control Engineering* (5th ed.), Prentice Hall.
2. Franklin, G.F., Powell, J.D., and Emami-Naeini, A. (2015). *Feedback Control of Dynamic Systems* (7th ed.), Pearson.
3. Astrom, K.J., and Murray, R.M. (2021). *Feedback Systems: An Introduction for Scientists and Engineers* (2nd ed.), Princeton University Press.
