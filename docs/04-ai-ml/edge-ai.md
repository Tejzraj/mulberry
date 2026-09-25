# Edge AI Hardware and Deployment

## 1. What It Is
Edge AI refers to the local execution of machine learning and computer vision inference algorithms on dedicated embedded microprocessors, microcontrollers, or neural processing units (NPUs) situated physically within the cutting machine, without dependency on external cloud servers.

## 2. Why It Matters
Rural sericultural farms in major silk-producing states often experience intermittent or absent internet connectivity, high ambient electrical noise, and high ambient temperatures. An intelligent cutting system must execute all sensory processing, inference, and control decisions locally with deterministic, millisecond-level responsiveness.

## 3. Key Concepts & Edge Hardware Platforms

### Candidate Edge Computing Platforms

| Platform | Compute Architecture | AI Acceleration | Typical Power | Approx. Cost ($ USD) | Operating System / Environment | Suitable Role |
|---|---|---|---|---|---|---|
| **ESP32-S3** | Dual Xtensa LX7 (240 MHz) | Vector instructions for 8-bit quantization | 0.5 – 1.0 W | $4 – $7 | FreeRTOS / Bare-metal C++ | Sensor DAQ, motor control, TinyML vibration inference |
| **Raspberry Pi 5 (4GB/8GB)** | Quad Cortex-A76 (2.4 GHz) | None (CPU only; ~20 GFLOPs) | 5 – 12 W | $60 – $80 | Linux (Debian/Ubuntu) | Supervisory control, classical CV, lightweight CNNs |
| **Raspberry Pi 5 + Hailo-8L NPU** | RPi 5 + M.2 Hailo-8L | 13 TOPS (INT8 NPU) | 7 – 15 W | $110 – $140 | Linux + HailoRT | Full real-time YOLO object detection & segmentation (> 30 FPS) |
| **NVIDIA Jetson Orin Nano** | 6-core ARM Cortex-A78AE + Ampere GPU | 20–40 TOPS (Sparse INT8) | 7 – 15 W | $200 – $300 | JetPack Linux / TensorRT | High-end research prototype testbench |
| **Kendryte K210 / MaixDuino** | Dual RISC-V 64-bit (400 MHz) | KPU (0.8 TOPS INT8) | 1 – 2 W | $15 – $25 | FreeRTOS / MicroPython | Low-cost entry-level leaf presence & color verification |

### Optimization & Runtime Stacks
- **Quantization**: Conversion of 32-bit floating point weights ($FP32$) to 8-bit signed integers ($INT8$), yielding a $4\times$ reduction in model size and $2\times$ to $4\times$ speedup on edge CPUs.
- **Inference Runtimes**: ONNX Runtime, TensorFlow Lite (TFLite), OpenVINO, and TensorRT.
- **Thermal Management**: Industrial environments require passive heatsinking or IP65 sealed enclosures with external cooling fins to dissipate 10–15 W without sucking moist, dusty air into the circuit board compartment.

## 4. Engineering Relevance
- **Thermal & Environmental Enclosures**: The computing enclosure must resist vibrating machine frames ($> 2g$ peak shocks) and thermal soak in 40°C rural sheds.
- **Reliability & Watchdog Timers**: Embedded Linux SBCs risk filesystem corruption if powered off abruptly. The power subsystem must include hardware power-loss protection (supercapacitors or micro-UPS) and hardware watchdog timers to reboot in the event of software lockups.

## 5. Questions to Investigate
- What is the actual thermal equilibrium temperature of an enclosed Raspberry Pi 5 operating inside an IP65 box at 35°C ambient temperature during continuous cutting?
- Can an ESP32-S3 handle real-time TinyML vibration FFTs while simultaneously generating clean 20 kHz stepper pulse trains without jitter?
- What is the total cold-boot time of candidate platforms from power switch activation to ready-to-cut state?

## 6. Sources
1. Raspberry Pi Foundation, *Raspberry Pi 5 and AI Kit Documentation* (2024).
2. Hailo Technologies, *Hailo-8L M.2 AI Acceleration Module Product Brief*.
3. Espressif Systems, *ESP32-S3 Technical Reference Manual*.
