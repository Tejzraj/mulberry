# Experiments and Empirical Testing

This directory manages the experimental life cycle for physical mechanical testing, sensor characterization, computer vision benchmarks, and biological silkworm feed quality evaluations.

## Directory Structure
- [`protocols/`](protocols/README.md) — Rigorous step-by-step test protocols defining hypotheses, apparatus, variables, procedures, and safety measures.
- [`results/`](results/README.md) — Synthesized experimental reports, statistical analyses, comparison charts, and peer-reviewed conclusions.
- [`logs/`](logs/README.md) — Raw measurement data files (CSV time-series, audio recordings, sensor dumps) organized by experiment ID.

## Core Rules
1. Never conduct a trial without an approved protocol in `protocols/`.
2. Never alter or selectively delete raw data in `logs/`.
3. Every experiment must report confidence intervals and standard deviations.
