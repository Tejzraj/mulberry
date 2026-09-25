# Master Research Questions Registry

## 1. What It Is
The master research questions registry compiles and categorizes all fundamental, unanswered scientific, engineering, and agronomic questions identified across the project domains.

## 2. Why It Matters
A complex interdisciplinary project risks getting sidetracked by secondary features before resolving core feasibility uncertainties. This registry serves as the scientific backlog directing empirical experiments, CAD modeling, and literature reviews.

## 3. Key Concepts & Domain Questions

### Domain A: Botany, Agronomy, and Sericulture Biology
1. *RQ-BIO-1*: What is the precise quantitative shear resistance (MPa) of fresh mulberry stems across diameters from 2 mm to 15 mm for major cultivars (V-1, S-36, G-4)?
2. *RQ-BIO-2*: How does post-harvest moisture decay rate compare between cleanly sheared leaf edges vs. crushed/torn edges over a 4-hour feeding window under chawki room conditions (28°C, 85% RH)?
3. *RQ-BIO-3*: What is the maximum acceptable leaf piece size and perimeter roughness tolerated by 1st and 2nd instar *Bombyx mori* without causing feeding inhibition?
4. *RQ-BIO-4*: Does feeding precision-cut leaves produce statistically significant increases in cocoon weight, shell percentage, or effective rate of rearing (ERR) compared to traditional manual chopping?

### Domain B: Mechanical Cutting Dynamics
1. *RQ-MECH-1*: What blade bevel angle (20°, 25°, 30°) and shear clearance (0.05 mm vs. 0.15 mm) minimizes specific cutting energy ($J/cm^2$) while maintaining edge durability when shearing both soft leaves and 12 mm woody stems?
2. *RQ-MECH-2*: Which mechanical kinematics—rotary drum shear vs. counter-rotating disc shear vs. reciprocating guillotine—provides the optimal balance of continuous feed throughput, cut sizing uniformity, and anti-clogging resilience?
3. *RQ-MECH-3*: What feed roller surface profile (fluted elastomer vs. knurled stainless steel) provides slip-free intake of wet, slippery mulberry leaves without crushing delicate laminae?

### Domain C: Sensing and IoT Instrumentation
1. *RQ-SENS-1*: Can motor current sensing reliably differentiate between an impending woody stem jam and a dense bundle of soft leaves before motor stall occurs?
2. *RQ-SENS-2*: What is the dominant acoustic and vibration frequency signature associated with tool sharpness loss, and can it be detected above the ambient mechanical noise of bearings, motors, and farm surroundings?
3. *RQ-SENS-3*: What is the temporal latency from physical stem contact at the ledger plate to measurable current spike detection in the microcontroller ADC?

### Domain D: AI, Computer Vision, and Control Systems
1. *RQ-AI-1*: Can a lightweight edge computer vision model (e.g., YOLO-nano or MobileNet) accurately segment individual leaves and estimate biological maturity grade under variable ambient farm lighting in real time (> 20 FPS)?
2. *RQ-AI-2*: Does edge disease detection provide actionable utility at the cutting stage, or are diseased leaves more reliably culled during field harvesting?
3. *RQ-CTRL-1*: What closed-loop control topology (e.g., dual PID loops for cutter drum and feed rollers) ensures instantaneous recovery and automatic throat clearing during transient cutting shocks without tripping circuit protection?

### Domain E: Economics and Field Practicality
1. *RQ-ECON-1*: What is the total bill-of-materials (BOM) cost ceiling for the machine to achieve a commercial payback period of less than two rearing seasons (< 1 year) for a typical 100-DFL sericulturist?
2. *RQ-ECON-2*: Can the machine operate continuously on single-phase rural power supplies subject to $\pm 20\%$ voltage fluctuations and frequent power outages?

## 4. Engineering Relevance
- Research questions are mapped directly to project phases in `ROADMAP.md`.
- No prototype design choice is frozen until its corresponding research question is answered with empirical data.

## 5. Questions to Investigate
- Which of the above research questions represents the highest technical risk to project feasibility and must be investigated first? *(Identified as RQ-BIO-1 and RQ-MECH-1: mechanical shear parameters of fresh mulberry biomass).*

## 6. Sources
1. Central Silk Board (CSB), *Research Gaps in Sericultural Mechanization*, Ministry of Textiles.
2. Kepner, R.A., et al. (2005). *Principles of Farm Machinery*, CBS Publishers.
3. FAO Agricultural Services Bulletin 107, *Mulberry Sericulture*.
