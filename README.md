# Mulberry Smart Cutting Machine

An AI + IoT enabled adaptive cutting and processing system for sericultural mulberry feed preparation.

> **Academic Context**: Interdisciplinary Minor Project (RVCE)
> **Current Status**: Concept / Research Phase
> **Repository**: [https://github.com/Tejzraj/mulberry.git](https://github.com/Tejzraj/mulberry.git)

---

## Overview

The **Mulberry Smart Cutting Machine** is an engineering and scientific research project exploring an AI + IoT enabled smart cutting system for mulberry (*Morus* spp.) material used in sericulture. Silkworm (*Bombyx mori*) rearing demands strict age-specific leaf and shoot sizes, uniform cut edges without tissue bruising, and uncontaminated biomass.

This project explores how real-time sensing, edge computer vision, and closed-loop electromechanical adaptation can automate and improve mulberry feed preparation, replacing manual chopping and non-adaptive motorized choppers.

---

## Problem

In traditional sericulture practice, mulberry leaf and shoot cutting presents several operational challenges:

1. **Labor Intensity & Inconsistency**: Manual chopping with sickle or chopping boards is slow, fatigue-prone, and yields inconsistent particle sizes across batches.
2. **Tissue Bruising & Moisture Loss**: Dull or improper cutting mechanisms tear leaf margins, crushing cell walls, accelerating moisture loss and oxidation, which diminishes palatability for young silkworms.
3. **Age-Specific Feed Inflexibility**: Silkworms pass through 5 instar stages, each requiring distinct leaf piece sizes (from finely chopped young leaves for 1st instars to whole leaves or shoot cuts for 5th instars). Existing mechanical choppers do not dynamically adapt cutting parameters based on feed stage or material characteristics.
4. **Varying Plant Morphology**: Mulberry stems, shoots, and leaves differ widely in lignification, moisture content, and shear resistance, leading to motor stalling, jamming, or blade dulling.
5. **Contamination Risks**: Diseased, pest-infested, or dusty leaves can compromise silkworm colony biosecurity if not sorted prior to feeding.

*Note: All potential improvements and mechanisms discussed in this repository are subjects of investigation; no quantitative performance gains are claimed prior to experimental validation.*

---

## Proposed Concept

The proposed smart cutting architecture integrates sensory feedback with edge intelligence:

```
+-----------------------------------------------------------+
|                     Mulberry Material                     |
|           (Leaves, Shoots, Varying Moisture/Age)          |
+-----------------------------------------------------------+
                              |
                              v
+-----------------------------------------------------------+
|                     Sensing / Vision                      |
|       (Optical Camera, Torque/Current, Vibration)         |
+-----------------------------------------------------------+
                              |
                              v
+-----------------------------------------------------------+
|                      Data Processing                      |
|     (Signal Filtering, Preprocessing, Feature Extract)    |
+-----------------------------------------------------------+
                              |
                              +--------------------+
                              |                    | (Telemetry Stream)
                              v                    v
+-----------------------------------+   +-----------------------------------+
|        AI / Decision Layer        |   |      Cyber-Physical Digital Twin  |
| (Instar Sizing, Density, Rules)   |   | (Multi-Physics Kinematics & ODEs, |
+-----------------+-----------------+   |  Real-Time Shadow, Blade Wear RUL,|
                  |                     |  Synthetic Fault Generation)      |
                  v                     +-----------------+-----------------+
+-----------------------------------+                     |
|            Controller             |<--------------------+ (Model-Based
|    (Embedded MCU / SBC, PID)      |                        State Estimates)
+-----------------+-----------------+
                  |
                  v
+-----------------------------------------------------------+
|                     Motor / Actuator                      |
|       (Feed Rollers, Variable Speed Cutter, Adjuster)     |
+-----------------------------------------------------------+
                              |
                              v
+-----------------------------------------------------------+
|                     Cutting Mechanism                     |
|            (Shear Blades / Rotary Cutter Drum)            |
+-----------------------------------------------------------+
                              |
                              v
+-----------------------------------------------------------+
|                         Feedback                          |
|         (Acoustic, Vibration, Current, Optical QA)        |
+-----------------------------------------------------------+
```

---

## Research Areas

- **Mulberry Cultivation & Physiology**: Variety traits, moisture retention, shear resistance, lignification across harvest regimes.
- **Sericulture Science**: *Bombyx mori* larval growth, instar nutrition requirements, feeding bed microclimate.
- **Silkworm Feeding Standards**: Age-dependent leaf size regimes, consumption efficiency, waste minimization.
- **Cutting Mechanics & Tool Wear**: Rotary vs. reciprocating shear cutters, blade material, edge retention, specific cutting energy.
- **Computer Vision (CV)**: Real-time detection of leaf quality, foreign debris, pest signs, and material geometry.
- **Sensory Instrumentation**: Current/torque monitoring, accelerometry for vibration analysis, acoustic emission for cutting sound analysis.
- **Edge AI & Embedded Computing**: Low-latency inference on resource-constrained compute platforms (e.g., Raspberry Pi, ESP32, edge micro-NPUs).
- **Closed-Loop Control Systems**: Dynamic feed rate regulation, adaptive blade speed, anti-jamming routines.
- **Cyber-Physical Digital Twin**: Kinematic/motor multi-physics simulation, virtual commissioning, live IoT telemetry shadow, and synthetic fault dataset generation.
- **Mechanical Automation & Ergonomics**: Compact feeder designs, operator safety interlocks, ease of cleaning/sanitization.
- **Patent & Prior-Art Landscape**: Thorough search of global patents and agricultural machinery literature.

---

## Project Status

**Current Phase**: Phase 1 — Domain Research & Problem Definition
See details in [`PROJECT_STATUS.md`](PROJECT_STATUS.md).

---

## Repository Structure

```
mulberry/
|-- README.md                     # Project overview and high-level architecture
|-- PROJECT_STATUS.md             # Current state, active focus, and milestones
|-- ROADMAP.md                    # Multi-phase engineering and research roadmap
|-- CONTRIBUTING.md               # Guidelines for research rigor and code practices
|-- docs/
|   |-- 01-domain/                # Mulberry botanical, cultivation, and harvest data
|   |-- 02-sericulture/           # Sericulture practices, silkworm biology, instar feeding
|   |-- 03-machine/               # Mechanical cutting dynamics, existing machines, safety
|   |-- 04-ai-ml/                 # Computer vision, edge models, data pipeline
|   |-- 05-iot-and-control/       # Sensor research, signal processing, closed-loop control, digital twin
|   |-- 06-patent/                # Prior-art search, innovation concepts, patent study
|   `-- 07-research/              # Methodology, core research questions, references
|-- daily-reports/                # Chronological daily engineering logs
|-- research/                     # Repositories for papers, patent PDFs, datasets
|-- hardware/                     # BOM, mechanical drawings, circuit schematics
|-- software/                     # Firmware, computer vision code, control algorithms, digital twin
|-- experiments/                  # Protocols, measurement logs, raw experimental data
`-- assets/                       # Diagrams, photos, benchmark videos
```

---

## Development Philosophy

1. **Evidence Before Claims**: No mechanical or algorithmic capability is declared functional without rigorous empirical data.
2. **Experiment Before Optimization**: Premature tuning without baseline measurements is avoided.
3. **Source Important Scientific Claims**: All biological and technical claims must cite recognized authorities (Central Silk Board, ICAR, peer-reviewed journals).
4. **Separate Facts from Hypotheses**: Proposed features and concepts are explicitly labeled as *Proposed / To be researched* until validated.
5. **Document Every Major Decision**: Rationale, trade-offs, and alternative approaches are recorded in research notes and daily logs.

---

## Roadmap

A structured 12-phase development trajectory is detailed in [`ROADMAP.md`](ROADMAP.md).
