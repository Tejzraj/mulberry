# Hardware Components Selection & Specifications

## 1. What It Is
This document details the preliminary evaluation, technical specifications, and selection rationale for off-the-shelf and custom hardware components constituting the physical testbench and prototype cutter.

## 2. Why It Matters
Selecting inappropriate components (e.g., undersized stepper motors that lose steps under friction, or non-isolated current sensors susceptible to electrical spikes) results in hardware failures, erratic control performance, and escalated prototype development costs.

## 3. Key Concepts & Component Breakdown

### 1. Actuation & Motors
- **Primary Cutting Drum Motor**:
  - *Candidate*: 750W – 1100W Brushless DC (BLDC) motor (48V DC, rated 3000 RPM, paired with 5:1 planetary reduction or timing belt reduction to achieve 600 RPM at 15–20 N·m torque).
  - *Alternative*: 1.0 HP Single-phase AC Induction motor with VFD (variable frequency drive).
- **Feed Mechanism Motor**:
  - *Candidate*: NEMA 23 or NEMA 34 High-Torque Stepper Motor (3.0–4.5 N·m holding torque), microstepped at 1600 steps/rev, paired with a 5:1 planetary gearbox for high stiffness feed roller drive.

### 2. Instrumentation & Sensors
- **Motor Current Sensing**: ACS712 / ACS724 (Hall effect, 30A/50A) or low-side 10 mΩ precision shunt with INA240 bidirectional current sense amplifier.
- **Vibration Sensing**: ADXL345 (3-axis digital I2C/SPI MEMS) or IEPE industrial piezoelectric accelerometer for high-frequency dynamic analysis.
- **Angular Velocity (RPM)**: Hall effect sensor module paired with neodymium magnets on the cutter drum hub, providing interrupt-driven pulse counting.
- **Vision Capture**: Raspberry Pi Global Shutter Camera (1.58 MP, Sony IMX296 sensor) or industrial USB3 machine vision camera.

### 3. Compute & Control Hardware
- **Low-Level Microcontroller**: STM32F4 / ESP32-S3 (FreeRTOS, 1 kHz control loop, hardware PWM, high-speed ADC, CAN/RS485).
- **High-Level Edge SBC**: Raspberry Pi 5 (4GB / 8GB) with active cooler; optional Hailo-8L M.2 NPU accelerator for real-time vision inference.

### 4. Power Supply Subsystem
- **Mains Input**: 220–240 V AC, 50 Hz, single phase.
- **DC Power Rails**:
  - 48V DC / 25A (1200W) switched-mode power supply (SMPS) for BLDC cutter motor.
  - 24V DC / 10A (240W) for stepper drivers, solenoids, and cooling fans.
  - 5V DC / 5A regulated buck converter for Raspberry Pi SBC and logic sensors.

## 4. Engineering Relevance
- All electrical components must be housed within a ventilated, dust-proof NEMA 4X / IP65 enclosure with positive internal pressure or sealed heat pipe exchangers.
- Emergency stop lines must cut coil power to safety contactors in hardware, isolating all high-voltage motor drivers independently of MCU software state.

## 5. Questions to Investigate
- Does the 48V BLDC motor generate excessive EMI that interferes with high-gain current sense amplifiers or I2C sensor buses?
- What is the peak thermal dissipation of the combined power supplies inside the sealed chassis?

## 6. Sources
1. Manufacturer Datasheets: Allegro ACS724, Texas Instruments INA240, Espressif ESP32-S3, Sony IMX296.
2. Hughes, A., and Drury, B. (2019). *Electric Motors and Drives*, Newnes.
3. Bureau of Indian Standards (BIS), *IS 15530:2005 Chaff Cutter Safety*.
