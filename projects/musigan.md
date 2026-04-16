---
title: MusiGAN
tags: [ml, music-generation, reproducibility]
permalink: /projects/musigan
---

# MusiGAN

## TL;DR

Compared LSTM, GRU, and GAN approaches for symbolic MIDI generation, then
upgraded the repo with evidence docs that separate creative results from
reproducibility and licensing caveats. The current artifact set includes a
stronger README, reproducibility notes, data-provenance warnings, an evaluation
rubric, and a sample-report template.

## Problem

How should we generate short symbolic music sequences while preserving variation
and musical structure?

The original project explored multiple model families, but the portfolio version
needed a clearer story around what was measured, what was only qualitatively
preferred, and what is safe to show publicly.

## Data

- Source format: MIDI symbolic note data, not raw audio.
- Observed committed corpus: 307 Pokemon MIDI files, 92 piano MIDI files, and a
  serialized note stream at `Data/notes`.
- Important caveat: these files may include copyrighted compositions or
  derivative transcriptions, so the repo now explicitly treats them as legacy
  local research inputs rather than a clean open benchmark.

## Method

- Parsed MIDI files into note/chord/rest tokens with `music21`.
- Encoded token windows for sequence modeling.
- Compared CuDNNLSTM, CuDNNGRU, and GAN generator/discriminator experiments.
- Converted generated token sequences back into MIDI.
- Added a listening rubric and proposed symbolic metrics for the next sample
  review pass.

## Results

| Evidence | Current status |
| --- | --- |
| LSTM/GRU/GAN code | Present in notebooks and `Models/gan_final.py` |
| Generated MIDI artifacts | Present in legacy `Output midi/` folders |
| Qualitative finding | GAN outputs were preferred in the original project notes; LSTM/GRU outputs were more repetitive |
| Formal evaluation table | Pending sample scoring with the new rubric |
| Data provenance | Documented as a risk before any public demo |

This is strongest as a creative ML case study: it shows model-family comparison,
artifact discipline, and sober handling of provenance rather than pretending a
legacy notebook is a production-grade music system.

## Demo / Artifacts

- [Source repo](https://github.com/elsalmi/MusiGAN)
- [Evidence README](https://github.com/elsalmi/MusiGAN/blob/master/README.md)
- [Reproducibility notes](https://github.com/elsalmi/MusiGAN/blob/master/docs/REPRODUCIBILITY.md)
- [Data provenance warning](https://github.com/elsalmi/MusiGAN/blob/master/docs/DATA_PROVENANCE.md)
- [Evaluation rubric](https://github.com/elsalmi/MusiGAN/blob/master/docs/README_EVAL.md)
- [Sample report](https://github.com/elsalmi/MusiGAN/blob/master/reports/SAMPLE_REPORT.md)
- [Artifact ignore policy](https://github.com/elsalmi/MusiGAN/blob/master/.gitignore)

## Risks and Tradeoffs

- Legacy TensorFlow/Keras/CuDNN APIs need pinning before reliable reruns.
- Training-data provenance needs cleanup before a public interactive demo.
- Existing generated samples are not automatically safe to redistribute.
- Evaluation remains qualitative until sample scores and symbolic metrics are
  exported to the report.

## What I’d improve next

1. Move questionable legacy data/checkpoints out of git into controlled artifact
   storage.
2. Add a pinned legacy environment and repo-relative generation script.
3. Score one LSTM, one GRU, and one GAN sample with the listening rubric.
4. Add symbolic metrics such as repetition rate, note-density, interval
   distribution, and unique n-gram rate.

## Repository

- GitHub: [github.com/elsalmi/MusiGAN](https://github.com/elsalmi/MusiGAN)
