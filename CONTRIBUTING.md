# Contributing Guidelines

Welcome to the **Mulberry Smart Cutting Machine** research and engineering repository. This repository adheres to high standards of scientific honesty, reproducible engineering, and clean Git hygiene.

---

## Core Engineering Principles

1. **Evidence Before Claims**: Never claim a feature is working, optimized, or patentable without reproducible experimental evidence.
2. **Fact vs. Hypothesis**: Always distinguish between established biological/engineering facts (which require reliable citations) and proposed hypotheses (which require experimental validation).
3. **No Fabricated Data or Sources**: Never fabricate URLs, DOI citations, author names, or performance statistics. If a source is unconfirmed, flag it explicitly as `Source required`.
4. **No Premature Optimization or Design Lock-in**: Maintain flexibility in mechanical and algorithmic architectures until comparative trade-off studies are executed.
5. **Safety First**: Cutting machines and high-speed rotary components present physical hazards. All hardware designs must incorporate hardware interlocks and fail-safe stop routines.

---

## Daily Research & Engineering Workflow

Contributors working on this repository follow a standardized daily rhythm:

1. **Inspect Git Status**: Review branch state and recent commits before starting.
2. **Review Previous Daily Report**: Read the latest report in `daily-reports/` to maintain continuity.
3. **Advance Current Milestone**: Implement changes aligned with the active phase in `ROADMAP.md`.
4. **Update Documentation & References**: Any new factual claim must be accompanied by an entry in `docs/07-research/references.md`.
5. **Record Unresolved Questions**: Log design trade-offs and uncertainties immediately.
6. **Log Daily Progress**: Author a new report in `daily-reports/YYYY-MM-DD.md`.
7. **Update Status**: Keep `PROJECT_STATUS.md` synchronized with actual progress.
8. **Verify & Push**: Perform pre-commit checks (`git diff --check`, linting) and push to the remote repository.

---

## Git Commit Conventions

We follow Conventional Commits formatting:

```
<type>(<scope>): <short description>
```

### Allowed Types
- `docs`: Documentation updates, domain notes, research syntheses.
- `feat`: New hardware schematic, firmware implementation, or algorithmic feature.
- `fix`: Bug fix in software or correction of documented parameters.
- `test`: Addition of experimental protocols, test bench results, or benchmark runs.
- `refactor`: Structural reorganization of code or documentation without semantic changes.
- `chore`: Maintenance of build scripts, `.gitignore`, or repository configuration.

### Commit Message Rules
- Use imperative, present tense ("add sensor analysis", not "added sensor analysis").
- Avoid generic commit messages like "updates", "changes", "wip", or "final".
- Keep commit scopes granular and focused.

---

## Scientific Citation Standard

When introducing agronomic, biological, or mechanical figures (e.g., leaf moisture content, silkworm feed dimensions, cutting energy), prioritize authoritative sources:
1. Central Silk Board (CSB), Ministry of Textiles, Govt. of India.
2. Indian Council of Agricultural Research (ICAR) & State Agricultural Universities.
3. Peer-reviewed journals (e.g., *Journal of Sericultural Science*, *Biosystems Engineering*, *ASABE Transactions*).
4. Official patent offices (IPO, USPTO, WIPO) for prior art.

Record every citation in `docs/07-research/references.md`.
