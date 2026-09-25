# Microcontroller Firmware

This directory contains the real-time embedded firmware executed on the system's low-level microcontroller (ESP32-S3 / STM32F4).

## Responsibilities
- 1 kHz sensor sampling loop (motor current, Hall RPM, chassis vibration, emergency interlocks).
- Precision microsecond pulse generation for feed stepper motor.
- Closed-loop PID speed and torque regulation for BLDC cutter motor.
- Instantaneous anti-jam sequence execution (< 20 ms response upon stall detection).
- Hardware watchdog and fail-safe shutdown routines.

## Development Stack
- Framework: ESP-IDF / PlatformIO (C/C++).
- Real-Time OS: FreeRTOS.
- Hardware Abstraction Layer (HAL) architecture isolating board pinouts from core control logic.
