# Software Architecture & Repositories

This directory houses the embedded firmware, computer vision pipelines, supervisory control algorithms, and edge telemetry code for the smart mulberry cutting machine.

## Structure
- [`firmware/`](firmware/README.md) — Low-level real-time firmware running on the microcontroller (ESP32-S3 / STM32): sensor sampling, stepper pulse generation, BLDC PWM control, and hardware safety state machines.
- [`computer-vision/`](computer-vision/README.md) — Image acquisition, dataset preprocessing, model training scripts, and edge inference pipelines for leaf detection, quality grading, and defect identification.
- [`control-system/`](control-system/README.md) — Supervisory closed-loop control routines, dynamic feed rate regulation, anti-jam state machines, and system telemetry.

## Software Standards
- **Firmware**: Written in modern C++ (C++17) or C within FreeRTOS; zero dynamic memory allocations in real-time control loops; strict MISRA C guidelines for safety-critical execution.
- **Computer Vision**: Python 3.10+ / C++ using OpenCV, ONNX Runtime, and PyTorch for model training.
- **Inter-Process Communication**: UART / CAN-bus / ZeroMQ message passing between low-level MCU and high-level SBC.
