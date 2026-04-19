---
title: Instrument Classification
tags: [ml, audio, classification]
permalink: /projects/instrument-classification
---

# Instrument Classification

## TL;DR

Built an instrument recognition project over NSynth audio with two modeling
tracks: feature-based supervised learning and CNN experiments over
spectrogram-style images. The best measured baseline so far is a random forest
at `54.20%` accuracy, improved to `57.57%` with randomized search in the
supervised-learning notebook.

## Problem

Given a short isolated note, predict the instrument family and make model
behavior understandable enough for review: expected inputs, likely confusions,
and practical quality targets.

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
concrete route from notebook experiment to a small demo.

## Output sample

![Random-forest confusion matrix after randomized search](/images/instrument-rf-confusion-matrix-tuned.png)

This confusion matrix is pulled from the randomized-search run in
`4.SupervisedLearning.ipynb`. The strongest diagonal classes include `string`
(`0.88`) and `vocal` (`0.61`), while `bass` is still frequently confused with
`mallet` (`0.24` in that row).

## Links

- [Source repo](https://github.com/elsalmi/Instrument-Classificiation-)
- [Report](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/reports/REPORT.md)
- [Data notes](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/docs/DATA.md)
- [Reproducibility notes](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/docs/REPRODUCIBILITY.md)
- [Pinned environment](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/environment.yml)
- [Supervised-learning notebook](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/4.SupervisedLearning.ipynb)
- [Rebuild script](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/scripts/rebuild_report.py)

## Recent updates

- Added the [pinned environment](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/environment.yml) and [rebuild script](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/scripts/rebuild_report.py) so the baseline is easier to rerun.
- Kept the [report snapshot](https://github.com/elsalmi/Instrument-Classificiation-/blob/master/reports/REPORT.md) and reproducibility notes aligned with the 11-class baseline.
- Left the 11-class vs 8-class warning explicit so the CNN path does not get over-interpreted.

## Risks

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
5. Build a lightweight demo that accepts a short WAV/MP3 note and returns top-k predictions with confidence.
