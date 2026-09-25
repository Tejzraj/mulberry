# Project Engineering & Research Roadmap

This document outlines the phased research and engineering progression for the **Mulberry Smart Cutting Machine**. Every phase defines explicit objectives, entry/exit criteria, and deliverables.

---

## Phase Summary Table

| Phase | Title | Focus Area | Status |
|---|---|---|---|
| Phase 1 | Domain Research | Botany, Agronomy, Sericulture Biology | In Progress |
| Phase 2 | Problem Definition | Farmer Needs, Cutting Inefficiencies, Constraints | Pending |
| Phase 3 | Existing Machine Study | Benchmarking Manual & Motorized Choppers | Pending |
| Phase 4 | Mechanical Concept | Blade Geometries, Feeder Mechanisms, Kinematics | Pending |
| Phase 5 | Sensor Selection | Torque, Current, Vibration, Optical, Acoustic | Pending |
| Phase 6 | Prototype Instrumentation | Test Bench Setup, DAQ, Sensor Calibration | Pending |
| Phase 7 | Data Collection | Empirical Cutting Datasets (Normal, Jammed, Dull) | Pending |
| Phase 8 | AI/ML Development | Vision Models, Anomaly Detection, State Estimation | Pending |
| Phase 9 | Closed-Loop Control | Adaptive Feed & Blade Speed Regulation Loop | Pending |
| Phase 10 | Prototype Testing | Lab & Field Cutting Runs with Silkworm Feeds | Pending |
| Phase 11 | Optimization | Energy Efficiency, Wear Resistance, Latency | Pending |
| Phase 12 | Patent & Paper Documentation | Formal Prior-Art Analysis, Academic Publication | Pending |

---

## Phase Details

### Phase 1 — Domain Research
- **Objective**: Establish a rigorous biological and agricultural foundation covering mulberry plant physiology, sericulture practices, silkworm instar feeding behaviors, and leaf quality parameters.
- **Deliverables**: Comprehensive literature synthesis across `docs/01-domain/` and `docs/02-sericulture/`, compiled reference library in `docs/07-research/references.md`.
- **Entry Criteria**: Project kick-off; repository initialization.
- **Exit Criteria**: Verified biological guidelines (instar-wise feed dimensions, leaf moisture requirements, harvest schedules) supported by reputable scientific sources (Central Silk Board, ICAR).

### Phase 2 — Problem Definition
- **Objective**: Translate biological feeding requirements and traditional sericulture practices into quantifiable mechanical and control engineering requirements.
- **Deliverables**: Detailed problem statement in `docs/03-machine/problem-definition.md`, quantitative targets for cutting dimensions, edge quality criteria, throughput targets, and failure modes.
- **Entry Criteria**: Completion of Phase 1 domain literature review.
- **Exit Criteria**: Engineering specification document approved with measurable acceptance criteria (e.g., target throughput in kg/hr, allowable bruise percentage, target cut size tolerance).

### Phase 3 — Existing Machine Study
- **Objective**: Conduct systematic benchmarking of existing manual cutting tools, chaff cutters, leaf choppers, and automated agricultural cutters.
- **Deliverables**: Comparative technical matrix in `docs/03-machine/existing-cutting-methods.md`, failure mode analysis of conventional machines (jamming, blade degradation, uneven cutting).
- **Entry Criteria**: Approved problem definition and cutting metrics.
- **Exit Criteria**: Comprehensive prior-art and competitive landscape cataloged; clear identification of technological gaps.

### Phase 4 — Mechanical Concept
- **Objective**: Develop conceptual mechanical designs for feeding, cutting, and discharging mulberry leaves and stems.
- **Deliverables**: Conceptual CAD/mechanical sketches in `hardware/mechanical/`, trade-off analysis of cutting mechanisms (rotary drum, scissor shear, guillotine, disc blades) in `docs/03-machine/cutting-mechanisms.md`.
- **Entry Criteria**: Benchmarking insights from Phase 3.
- **Exit Criteria**: Down-selected mechanical architecture with documented design calculations (cutting forces, motor sizing, gear ratios).

### Phase 5 — Sensor Selection & Signal Feasibility
- **Objective**: Evaluate and select candidate sensors for real-time state estimation (material density, blade dullness, motor load, feed rate, cut quality).
- **Deliverables**: Evaluated sensor trade-off matrix in `docs/05-iot-and-control/sensor-research.md`, component selection in `hardware/components.md`, sensor datasheets cataloged.
- **Entry Criteria**: Mechanical architecture down-selection.
- **Exit Criteria**: Selected sensor suite with defined measurement ranges, sampling frequencies, interfaces, and electrical specs.

### Phase 6 — Prototype Instrumentation & Bench Setup
- **Objective**: Construct an instrumented experimental cutting test-bench with integrated Data Acquisition (DAQ).
- **Deliverables**: Physical test bench wiring schematics in `hardware/schematics/`, DAQ firmware in `software/firmware/`, raw signal logging verification.
- **Entry Criteria**: Sourced sensors, motors, and prototype mechanical frame.
- **Exit Criteria**: Demonstrated synchronized signal capture (current, vibration, optical frames, acoustic) during live cutting.

### Phase 7 — Empirical Data Collection
- **Objective**: Execute structured cutting experiments across varying leaf conditions (fresh, wilted, mature shoots, tender shoots) and machine states (sharp blade, worn blade, overloaded feed).
- **Deliverables**: Labeled experimental dataset cataloged in `research/datasets/`, standardized test protocols in `experiments/protocols/`, data run logs in `experiments/logs/`.
- **Entry Criteria**: Functional, calibrated DAQ bench.
- **Exit Criteria**: Minimum target volume of labeled time-series and image data across baseline operational regimes.

### Phase 8 — AI/ML Development & Edge Optimization
- **Objective**: Train and evaluate machine learning models for computer vision (leaf stage/quality sorting) and sensor-based condition monitoring (blade wear, jam prediction).
- **Deliverables**: Trained model weights/benchmarks in `software/computer-vision/`, edge deployment benchmarks (latency, memory footprint, accuracy) in `docs/04-ai-ml/edge-ai.md`.
- **Entry Criteria**: Verified labeled dataset from Phase 7.
- **Exit Criteria**: Models meeting target inference latency (< 50 ms on target edge device) and accuracy thresholds on hold-out validation sets.

### Phase 9 — Closed-Loop Control Implementation
- **Objective**: Design, implement, and simulate closed-loop control algorithms dynamically adjusting feed speed, blade RPM, or feed clearances based on sensor/AI feedback.
- **Deliverables**: Control software in `software/control-system/`, closed-loop architecture analysis in `docs/05-iot-and-control/closed-loop-control.md`.
- **Entry Criteria**: Calibrated actuators and validated predictive models/rules.
- **Exit Criteria**: Stable closed-loop response demonstrated without hunting, motor stall, or excessive mechanical oscillation during sudden load variations.

### Phase 10 — Prototype Testing & Silkworm Feeding Trials
- **Objective**: Evaluate end-to-end prototype performance in laboratory cutting trials and test cut feed on silkworm colonies.
- **Deliverables**: Comprehensive test report in `experiments/results/`, cut quality metric evaluations (edge damage, sizing uniformity, moisture retention).
- **Entry Criteria**: Integrated closed-loop hardware/software cutting prototype.
- **Exit Criteria**: Quantitative verification of cut quality, safety interlock performance, and biological acceptability of prepared feed.

### Phase 11 — Engineering Optimization
- **Objective**: Refine mechanical, electrical, and algorithmic subsystems based on trial data to enhance energy efficiency, reliability, and ergonomics.
- **Deliverables**: Revised BOM (`hardware/bill-of-materials.md`), design for manufacturing (DFM) documentation, optimized control firmware.
- **Entry Criteria**: Field trial analysis from Phase 10.
- **Exit Criteria**: Final prototype sign-off demonstrating target throughput, reliability, and ease of maintenance.

### Phase 12 — Patent & Paper Documentation
- **Objective**: Compile rigorous scientific documentation, conduct formal patent prior-art novelty analysis, and draft research publications.
- **Deliverables**: Complete prior-art mapping in `docs/06-patent/prior-art.md`, innovation assessment in `docs/06-patent/innovation-concept.md`, submitted peer-reviewed manuscript or technical project report.
- **Entry Criteria**: Validated experimental data and prototype validation from Phases 10–11.
- **Exit Criteria**: Completed project technical documentation, comprehensive research thesis/manuscript, formal patentability assessment.
