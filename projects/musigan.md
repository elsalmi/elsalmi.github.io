---
title: MusiGAN
tags: [ml, music-generation, reproducibility]
permalink: /projects/musigan
---

# MusiGAN

## TL;DR

Compared LSTM, GRU, and GAN approaches for symbolic music generation and framed the project around quality tradeoffs, reproducibility, and artifact-first reporting.

## Problem

How should we generate short symbolic music sequences while preserving variation and musical structure?  
The original project explored multiple model families but lacked a portfolio-ready narrative around reproducibility and evaluation artifacts.

## Data

- Source: public MIDI-oriented experiments documented in the repository.
- Constraint: legacy TensorFlow stack and older environment assumptions require explicit pinning before reliable reruns.
- Note: dataset provenance and licensing were not fully operationalized in the original version.

## Method

- Implemented sequence pipelines for symbolic input representation.
- Trained and compared LSTM, GRU, and GAN models.
- Structured the portfolio story around what changed in quality and compute behavior across models.

## Results

- GAN path was reported as faster to convergence and often produced better listening quality than recurrent baselines in the legacy project notes.
- Current portfolio artifact focuses on clearly separating:
  - model family
  - sample quality observations
  - reproducibility status

## Demo / Artifacts

- Repository code and notebooks are linked in the project GitHub page.
- Planned next artifact pack:
  - generated sample set
  - short reproducibility note
  - model checkpoints or reference scripts

## Risks and Tradeoffs

- The project is currently best presented as a comparative proof-of-concept due to dependency age.
- Evaluation is still mostly qualitative unless dedicated symbolic metrics are added in the next iteration.

## What I’d improve next

1. Pin a modern reproducible environment container.
2. Add one-page sample generation output report with before/after comparison.
3. Add benchmark-style metrics and a minimal demo interface.

## Repository

- GitHub: [github.com/elsalmi/MusiGAN](https://github.com/elsalmi/MusiGAN)
