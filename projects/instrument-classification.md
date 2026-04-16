---
title: Instrument Classification
tags: [ml, audio, classification]
permalink: /projects/instrument-classification
---

# Instrument Classification

## TL;DR

Built an instrument recognition workflow over NSynth audio with two modeling
tracks: feature-based supervised learning and CNN experiments over
spectrogram-style images. The best measured baseline so far is a random forest
at `54.20%` accuracy, improved to `57.57%` with randomized search in the
supervised-learning notebook.

## Problem

Given a short isolated note, predict the instrument family while making model
behavior understandable enough for demo review: expected inputs, likely
confusions, and measurable next thresholds.

## Data

- Dataset: Google NSynth.
- Notebook-observed metadata split sizes: 289,205 training records, 12,678
  validation records, and 4,096 test records.
- The project notes document dataset source, local layout assumptions, class-set
  differences across notebooks, and why raw audio/features are not committed to
  the repo.

## Method

- Extracted audio-feature tables for scikit-learn supervised baselines.
- Trained random forest baselines and plotted normalized confusion matrices.
- Prepared spectrogram-style image folders for fast.ai CNN experiments,
  including pretrained ResNet/DenseNet variants.
- Kept the measured baseline separate from the demo plan so the project does not
  overstate model readiness.

## Results

| Area | Current status |
| --- | --- |
| Random forest accuracy | `54.20%` in `4.SupervisedLearning.ipynb` |
| Randomized-search random forest accuracy | `57.57%` in `4.SupervisedLearning.ipynb` |
| CNN confusion review | Present in notebooks, with most-confused pairs such as brass/reed, flute/reed, and vocal/string |
| Final CNN metric table | Pending regeneration from a pinned environment |

The project is not finished, but it now has a clear baseline, known gaps, and a
practical path from notebook experiment to a small demo.

## Links

- [Source repo](https://github.com/elsalmi/Instrument-Classificiation-)
- [Report](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/reports/REPORT.md)
- [Data notes](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/docs/DATA.md)
- [Reproducibility notes](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/docs/REPRODUCIBILITY.md)
- [Supervised-learning notebook](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/4.SupervisedLearning.ipynb)
- Planned demo path: upload a short WAV/MP3 note, compute the same
  spectrogram-style representation, return top-k class predictions with
  confidence, and show the known confusion risks.

## Risks and Tradeoffs

- The repo is notebook-first and does not yet include raw NSynth data, generated
  spectrogram folders, serialized feature tables, or model checkpoints.
- The supervised-learning path and CNN path use different class sets in the
  committed notebooks.
- The demo should warn users that NSynth is isolated-note data, not arbitrary
  mixed music.

## What I’d improve next

1. Add a pinned environment file and deterministic feature extraction script.
2. Include a small confusion matrix figure in `reports/`.
3. Regenerate CNN metrics and export them as a stable report table.
4. Define acceptance thresholds and error budgets by instrument class.

## Repository

- GitHub: [github.com/elsalmi/Instrument-Classificiation-](https://github.com/elsalmi/Instrument-Classificiation-)
