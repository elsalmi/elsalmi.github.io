---
title: LendingClub Fairness
tags: [ml, fairness, tabular, case-study]
permalink: /projects/lendingclub
---

# LendingClub Fairness

## TL;DR

Built a loan repayment prediction workflow and layered fairness diagnostics to check whether outcomes differed across protected-proxy groups.

## Problem

Credit risk models are often high-performing but can carry unequal error profiles across demographic proxies.  
This project aimed to surface those tradeoffs rather than hide them behind single-metric accuracy reporting.

## Data

- Funded-loan records from public LendingClub-style columns (historical, U.S. lending data shape).
- Outcome focus: whether loans were fully paid vs. charged off.
- Sensitive attribute path: proxy constructed from ZIP-level features and Census-linked context in the original project.

## Method

- Train baseline models for repayment prediction.
- Evaluate with standard performance metrics and fairness metrics.
- Compare pre/post mitigation behavior with reweighing-style adjustments.

## Results

- Fairness checks included statistical parity difference, disparate impact, average odds difference, and equal opportunity difference.
- The existing fairness notes reported meaningful movement toward parity after reweighing, with tradeoffs that are explicitly documented for decision-making.

## Demo / Artifacts

- GitHub repository includes walkthroughs and fairness reporting structure.
- The case-study page tracks next-step outputs to move toward:
  - reproducible train/seeded inference script
  - exported `FAIRNESS_REPORT.md`
  - clear metric snapshots per model type

## Risks and Tradeoffs

- ZIP-proxy framing is useful for portfolio communication but requires strict framing and governance if discussed in operational settings.
- Accuracy and fairness can move in opposite directions if thresholding and sampling assumptions are changed.

## What I’d improve next

1. Replace mutable manual steps with idempotent scripts.
2. Add a compact model card with explicit limitations and intended-use boundaries.
3. Provide artifact screenshots from generated reports for quick trust verification.

## Repository

- GitHub: [github.com/elsalmi/LendingClub](https://github.com/elsalmi/LendingClub)
