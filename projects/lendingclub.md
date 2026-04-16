---
title: LendingClub Fairness
tags: [ml, fairness, tabular, case-study]
permalink: /projects/lendingclub
---

# LendingClub Fairness

## TL;DR

Built a loan repayment prediction workflow with fairness diagnostics to check
whether outcomes differed across ZIP-derived proxy groups. The repo includes a
model card, data notes, and a fairness report based on the original notebook
metrics.

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
- Reported logistic-regression fairness snapshot: accuracy `0.652441`, statistical parity difference `-0.019635`, disparate impact `0.966937`, equal opportunity difference `-0.013784`, average odds difference `-0.013502`, and Theil index `0.354349`.
- Reported reweighing snapshot: training mean outcome difference moved from `-0.017565` to `0.000000`; test mean outcome difference moved from `-0.019698` to `-0.002036`.
- Reported random forest precision was `0.913286`, with the project framed around high-precision ranked loan selection rather than automated lending deployment.

## Links

- [Model card](https://github.com/elsalmi/LendingClub/blob/master/MODEL_CARD.md): intended use, metric snapshot, fairness framing, and limitations.
- [Fairness report](https://github.com/elsalmi/LendingClub/blob/master/reports/FAIRNESS_REPORT.md): summary built from existing `Fairness.md` outputs.
- [Data notes](https://github.com/elsalmi/LendingClub/blob/master/docs/DATA.md): source, local layout, ZIP3 proxy warning, and privacy constraints.
- [Original fairness notebook export](https://github.com/elsalmi/LendingClub/blob/master/Fairness.md): traceable source for reported metric values.

## Risks and Tradeoffs

- ZIP-derived proxy groups are useful for auditing patterns, but they are noisy
  and require careful governance in any real-world setting.
- Accuracy and fairness can move in opposite directions if thresholding and sampling assumptions are changed.

## What I’d improve next

1. Replace mutable manual steps with idempotent scripts.
2. Regenerate the fairness report from a pinned environment instead of copying notebook outputs.
3. Add calibration and threshold-sweep plots for precision/fairness tradeoffs.

## Repository

- GitHub: [github.com/elsalmi/LendingClub](https://github.com/elsalmi/LendingClub)
