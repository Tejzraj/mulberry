# Experiments Master Registry and Protocols

## 1. What It Is
The experiments master registry establishes the standardized experimental protocol template, trial logging guidelines, data archival procedures, and active directory of planned and completed experiments across the project lifecycle.

## 2. Why It Matters
Reproducibility is the bedrock of scientific engineering. Unstructured testing leads to lost data, uncalibrated readings, unrepeatable results, and misdirected engineering effort. Standardized protocols ensure that every test run generates valid, peer-reviewable evidence.

## 3. Key Concepts & Standard Experiment Protocol Template

Every experiment documented in `experiments/protocols/` must adhere to the following mandatory structure:

```markdown
# Experiment Protocol: [EXP-ID] — [Descriptive Title]

## 1. Objective & Hypothesis
- **Objective**: Specific, measurable goal of the trial.
- **Hypothesis**: Formal falsifiable statement (e.g., "Increasing blade shear clearance from 0.08 mm to 0.25 mm will increase cut leaf moisture loss rate by > 20% over 2 hours").

## 2. Experimental Apparatus & Setup
- Mechanical fixtures, motor drive models, sensor part numbers, serial numbers.
- Calibration dates, zero-tare procedures, sampling frequencies.

## 3. Variables
- **Independent Variables**: Parameter deliberately manipulated (e.g., blade speed, feed rate, stem diameter).
- **Dependent Variables**: Measured outputs (e.g., peak motor current, edge roughness, mass flow rate).
- **Controlled Variables**: Kept constant (e.g., room temperature, leaf variety, post-harvest age).

## 4. Materials & Sampling
- Mulberry cultivar (e.g., V-1), harvest time, harvest method, sample size ($N \ge 30$).

## 5. Step-by-Step Procedure
- Chronological execution steps with safety precautions.

## 6. Safety Hazards & Mitigation
- High-speed rotating parts, sharp blade handling, electrical isolation.

## 7. Data Logging & File Artifacts
- Location of raw CSV, audio, or video logs in `experiments/logs/`.

## 8. Analysis & Acceptance Criteria
- Statistical tests (t-test, ANOVA), significance threshold ($p < 0.05$).
```

---

## 4. Master Registry of Planned Experiments

| Experiment ID | Title | Target Domain | Phase | Status |
|---|---|---|---|---|
| **EXP-BIO-01** | Post-Harvest Leaf Desiccation vs. Cut Edge Geometry | Sericulture Biology | Phase 1 | Planned |
| **EXP-MECH-01** | Mulberry Stem Shear Resistance Characterization | Mechanical Cutting | Phase 2 | Planned |
| **EXP-MECH-02** | Blade Clearance vs. Specific Cutting Energy Benchmarking | Mechanical Cutting | Phase 3 | Planned |
| **EXP-SENS-01** | Dynamic Motor Current Signatures Under Varying Feed Loads | IoT & Sensing | Phase 5 | Planned |
| **EXP-SENS-02** | Vibration Spectrum Analysis Across Sharp and Dulling Blades | IoT & Sensing | Phase 6 | Planned |
| **EXP-AI-01** | Edge Computer Vision Leaf vs. Stem Segmentation Benchmark | AI & Vision | Phase 8 | Planned |
| **EXP-CTRL-01** | Closed-Loop Anti-Jam Feed Reversal Latency Validation | Control Systems | Phase 9 | Planned |

## 5. Questions to Investigate
- What standard moisture balance or oven-drying methodology (e.g., AOAC 930.15) should be used as the gold standard for measuring leaf moisture loss?
- Where can controlled biological rearing validation trials be hosted (e.g., university sericulture department or CSRTI research station)?

## 6. Sources
1. Montgomery, D.C. (2017). *Design and Analysis of Experiments*, Wiley.
2. Central Silk Board (CSB), *Standard Rearing and Testing Protocols*.
3. ASABE Standards, *S358.2: Moisture Measurement — Forages*.
