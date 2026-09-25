# Research Methodology and Scientific Rigor

## 1. What It Is
The research methodology defines the scientific principles, evidentiary hierarchy, hypothesis testing frameworks, and verification protocols governing all biological, mechanical, sensor, and AI research within this project.

## 2. Why It Matters
Engineering agricultural automation without scientific rigor leads to costly mistakes, premature optimization, fabricated claims, and machines that look functional on paper but fail in actual farm conditions or injure livestock and operators. A disciplined methodology ensures that every technical decision is traceable to verified facts and empirical data.

## 3. Key Concepts & Evidentiary Hierarchy

### Evidentiary Hierarchy
When evaluating claims, parameters, or specifications, evidence is ranked in the following descending order of authority:
1. **Tier 1 — Controlled Empirical Data**: Measurements collected directly by the team on calibrated physical testbenches following documented protocols.
2. **Tier 2 — Primary Sericultural & Agricultural Authorities**: Official publications, technical bulletins, and manuals from the Central Silk Board (CSB), CSRTI Mysore, Indian Council of Agricultural Research (ICAR), and state sericulture directorates.
3. **Tier 3 — Peer-Reviewed Scientific Literature**: Published journal papers (e.g., ASABE, Biosystems Engineering, Journal of Sericultural Science, CIRP Annals).
4. **Tier 4 — Industrial Standards**: BIS (IS 11459, IS 15530), ISO (ISO 4254-1, ISO 13849-1), IEC electrical codes.
5. **Tier 5 — Working Hypotheses & Engineering Assumptions**: Explicitly labeled as such; subject to mandatory experimental verification.
*(Commercial marketing brochures, unverified blogs, and anecdotal opinions are strictly excluded as primary evidence).*

### Scientific Hypothesis Testing Protocol
Every proposed smart feature must follow the standard empirical loop:
1. **Observation**: State the field problem with quantifiable baseline metrics (e.g., "manual chopping yields particle size variance of $\pm 40\%$").
2. **Hypothesis**: Formulate a falsifiable, testable prediction (e.g., "regulating feed roller velocity via motor current feedback will reduce particle size variance to $<\pm 15\%$").
3. **Protocol Formulation**: Define independent, dependent, and control variables, sample size ($N \ge 30$), instrumentation calibration, and environmental conditions.
4. **Execution & Data Logging**: Record raw time-series without filtering or selective pruning.
5. **Statistical Analysis**: Compute mean, standard deviation, confidence intervals ($p < 0.05$), and error distributions.
6. **Conclusion**: Confirm, reject, or refine the hypothesis.

## 4. Engineering Relevance
- **Separation of Fact and Proposal**: In all project documentation, existing verified biological facts must be clearly segregated from proposed machine mechanisms.
- **Reproducibility**: All software scripts, CAD files, sensor logs, and wiring schematics must be committed to the repository with full provenance so that any experiment can be independently replicated.

## 5. Questions to Investigate
- What is the minimum statistical sample size of mulberry shoots required to establish a normal distribution of shear strength across different cultivars?
- What are the confounding environmental variables (relative humidity, temperature, time since harvest) that must be controlled during cutting tests?

## 6. Sources
1. Central Silk Board (CSB), *Research Methodologies in Sericultural Sciences*, Ministry of Textiles.
2. Montgomery, D.C. (2017). *Design and Analysis of Experiments* (9th ed.), Wiley.
3. Indian Council of Agricultural Research (ICAR), *Handbook of Agricultural Engineering*.
