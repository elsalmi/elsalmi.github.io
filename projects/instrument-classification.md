---
title: Instrument Classification
tags: [ml, audio, classification]
permalink: /projects/instrument-classification
---

# Instrument Classification

## TL;DR

Built an instrument recognition workflow focused on clean problem framing, model interpretation, and practical next steps for production-facing evaluation.

## Problem

Given an audio sample, identify likely instrument class while keeping model behavior understandable and measurable for review.

## Data

- Audio clips and labels from the repository’s experiment space.
- Goal is short-form classification and confusion-style performance framing.
- Planned follow-up includes clearer data split and preprocessing notes in-code and in docs.

## Method

- Audio preprocessing pipeline to generate model-ready features.
- Baseline model training and confusion-style validation.
- Emphasis on adding explicit artifact tracking before scaling deployment claims.

## Results

- Current project summary emphasizes model quality framing (accuracy + confusion patterns) and interpretability path.
- Existing artifacts are currently notebook-heavy; portfolio work focuses on distilling reusable outcomes into case-study form.

## Demo / Artifacts

- Public repo includes experiments and implementation artifacts.
- Planned minimal public demo path:
  - sample upload/uploaded clip notes
  - class output + confidence summary
  - small gallery of expected classes and failure examples

## Risks and Tradeoffs

- Limited dataset detail in the current state can obscure model boundaries.
- The portfolio page currently prioritizes clarity and reproducibility planning over finalized productionization.

## What I’d improve next

1. Add a pinned environment file and deterministic feature extraction script.
2. Include a small confusion matrix figure in a `reports/` artifact.
3. Define acceptance thresholds and error budgets by instrument class.

## Repository

- GitHub: [github.com/elsalmi/Instrument-Classificiation-](https://github.com/elsalmi/Instrument-Classificiation-)
