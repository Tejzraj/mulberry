# Hardware Components Selection & Specifications (Prototype-1)

> **Project**: Design and Development of a Compact Electric Plant Cutting, Gathering and Binding Machine for Future Mulberry Application  
> **Target Prototype**: Prototype-1 Mini Model (Electric 24V Architecture)

---

## 1. Overview & Strategy

The Prototype-1 component selection balances affordability, modularity, and rapid prototyping. A 24V DC battery-electric bus is selected over internal combustion (IC) engines to simplify speed control, reduce mechanical vibration, eliminate local emissions, and facilitate sensor/MCU telemetry.

---

## 2. Component Specifications Breakdown

### 2.1 Actuation & Power Transmission
- **Cutter Motor**:
  - *Type*: High-torque 24V DC brushed or brushless motor.
  - *Power Rating*: ~500W nominal.
  - *Speed & Transmission*: Operating at ~3000 RPM base speed, reduced via a 2-stage pulley/belt or chain drive down to 600–900 RPM at the cutter shaft to deliver high cutting torque and resist plant jams.
  - *Shaft & Bearings*: Ground 20 mm shaft supported by two UCP 204 pillow-block bearings.
- **Traction Motor**:
  - *Type*: 24V geared DC motor with integrated spur or planetary gearbox.
  - *Power Rating*: ~250W.
  - *Output Speed*: 30–60 RPM at axle, delivering 0.2–0.5 m/s travel speed through 250–350 mm drive wheels.
- **Binding System Actuator**:
  - *Type*: 12V/24V high-torque low-RPM worm gear motor (or mini linear actuator), ~30–50W.
  - *Function*: Drives the rotating twine ring around the compressed bundle and operates the mechanical twine cutter.

### 2.2 Energy Storage & Power Management
- **Battery Pack**:
  - *Chemistry*: Lithium Iron Phosphate (LiFePO4).
  - *Rating*: 24V (nominal), ~30 Ah capacity (~720 Wh nominal energy).
  - *Advantages*: Lighter than lead-acid, high thermal stability, > 2000 deep cycle life, negligible voltage sag under load.
  - *Protection*: Internal 40A continuous Battery Management System (BMS) with over-charge, over-discharge, short-circuit, and cell-balancing protection.
- **Power Distribution**:
  - Main 40A/50A DC fuse mounted immediately at the battery positive terminal.
  - Latching red mushroom Emergency Stop switch isolating the main power bus.
  - High-efficiency 24V-to-5V step-down buck converter (3A) supplying the ESP32 microcontroller and logic sensors.

### 2.3 Microcontroller & Embedded Control
- **Microcontroller**: ESP32 DevKit V1 (38-pin, dual-core Tensilica Xtensa 32-bit LX6, 240 MHz).
- **Core Responsibilities**:
  - PWM generation for traction and cutter motor drivers.
  - Real-time interrupt counting for cutter RPM and wheel odometry.
  - Fast ADC sampling for current overload protection.
  - Finite State Machine (FSM) control for the binding sequence.
  - Telemetry streaming over Wi-Fi / Bluetooth (BLE) to mobile/laptop dashboard.

### 2.4 Sensor Suite
1. **Cutter RPM Sensor**: A3144 Hall-effect digital latch module positioned adjacent to a rotating magnetic collar on the cutter shaft.
2. **Current Overload Sensor**: ACS712 (30A) or ACS724 Hall-effect current sensor inline with the cutter motor supply to detect stem jams and trigger automatic shutdown.
3. **Battery Voltage Monitor**: High-precision resistor divider (e.g., 100kΩ / 10kΩ) connected to ESP32 ADC pin with RC low-pass filter.
4. **Wheel Encoder**: Photoelectric or magnetic hall encoder on the wheel axle for speed calculation (0.2–0.5 m/s) and distance tracking.
5. **Limit Switches**: Heavy-duty micro-switches to detect binding ring home position, bundle compression threshold, and release gate closure.

---

## 3. Power Architecture Schematic Block Diagram

```
[ 24V, 30Ah LiFePO4 Battery ]
             |
    [ 40A Main Fuse ]
             |
    [ Emergency Stop ]
             |
             +-----------------------+-----------------------+
             |                       |                       |
             v                       v                       v
    [ Cutter Driver ]       [ Traction Driver ]     [ DC-DC 5V Buck ]
             |                       |                       |
             v                       v                       v
     Cutter Motor (500W)     Traction Motor (250W)      [ ESP32 MCU ]
             |                       |                       |
    [ Hall RPM + ACS712 ]     [ Wheel Encoder ]    [ Limit Switches & Logs ]
```
