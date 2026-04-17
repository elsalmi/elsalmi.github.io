---
title: Qiskit Hub
tags: [quantum, experimentation]
permalink: /projects/qiskit
---

# Qiskit Hub

## TL;DR

Built a practical quantum-computing tutorial track in Qiskit, from basic circuits
to algorithm demos. The repo shows runnable notebooks, reference material, and
deterministic simulator outputs for sanity checks.

## Problem

How do we demonstrate practical understanding of quantum programming concepts
while keeping the work understandable to non-specialists?

## Data

- Primary inputs are tutorial circuits and simulator outputs, not a tabular ML dataset.
- Work is organized around notebook-based experiments in `Tutorials/`.
- Runtime scope is mainly simulator-backed execution for repeatable learning runs.

## Method

- Implemented topic-by-topic notebooks (Hello World, circuit building,
  teleportation, and Bernstein-Vazirani).
- Executed circuits with Qiskit backends (`statevector_simulator` and `qasm_simulator`).
- Kept outputs inspectable with plots and measurement dictionaries in notebook cells.

## Results

- Completed and published four core tutorial notebooks in the repo.
- In the Bernstein-Vazirani notebook, a single-shot simulator run reports one
  measured key (`{'101010010101': 1}`) and the plotted output shows probability
  `1.000` for that observed state.
- Added reference materials (`Quantum Gates Cheat Sheet.pdf` and project papers)
  to support quick review.

## Output sample

![Bernstein-Vazirani single-shot simulator output at probability 1.000](/images/qiskit-bv-output-sample.png)

Output extracted from the committed
`Tutorials/4. Bernstein-Vazirani Algorithm.ipynb` notebook.

## Links

- [Source repo](https://github.com/elsalmi/qiskit)
- [Reproducibility notes](https://github.com/elsalmi/qiskit/blob/master/docs/REPRODUCIBILITY.md)
- [Hello World tutorial](https://github.com/elsalmi/qiskit/blob/master/Tutorials/1.%20Hello%20World.ipynb)
- [Quantum Teleportation tutorial](https://github.com/elsalmi/qiskit/blob/master/Tutorials/3.%20Quantum%20Teleportation%20Algoirthim.ipynb)
- [Bernstein-Vazirani tutorial](https://github.com/elsalmi/qiskit/blob/master/Tutorials/4.%20Bernstein-Vazirani%20Algorithm.ipynb)
- [Quantum gates cheat sheet](https://github.com/elsalmi/qiskit/blob/master/Tutorials/Quantum%20Gates%20Cheat%20Sheet.pdf)

## Updated evidence

- Added [reproducibility notes](https://github.com/elsalmi/qiskit/blob/master/docs/REPRODUCIBILITY.md) with notebook order and environment expectations.
- Kept the deterministic Bernstein-Vazirani output as the clearest checked result in the tutorial path.
- Reframed the repo around the four tutorials and archived the scratch notebook outside the core flow.

## Risks

- Quantum libraries evolve quickly, so notebooks can break as APIs change.
- Simulator success does not guarantee equivalent behavior on real hardware noise profiles.
- This is an educational and experimentation repo, not a production quantum system.

## What I’d improve next

1. Add a pinned environment file and notebook compatibility notes by Qiskit version.
2. Add one multi-shot run summary table (counts distribution and interpretation).
3. Add a short hardware-vs-simulator note for readers new to quantum runtime constraints.
