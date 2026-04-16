---
title: MusiGAN
tags: [ml, music-generation, reproducibility]
permalink: /projects/musigan
---

# MusiGAN

## TL;DR

Built a symbolic music generation project that compares LSTM, GRU, and GAN
approaches over MIDI note sequences. The project parses MIDI into musical tokens,
trains sequence models, and converts generated tokens back into playable MIDI.

## Problem

How should we generate short symbolic music sequences while preserving variation
and musical structure?

The project explores which model family produces the most usable musical
sketches, while keeping the limits clear: the outputs are creative drafts, not a
finished music product.

## Data

- Source format: MIDI symbolic note data, not raw audio.
- Observed committed corpus: 307 Pokemon MIDI files, 92 piano MIDI files, and a
  serialized note stream at `Data/notes`.
- Some source MIDI files are game/theme transcriptions, so I do not present the
  corpus as a cleared public benchmark.

## Method

- Parsed MIDI files into note/chord/rest tokens with `music21`.
- Encoded token windows for sequence modeling.
- Compared CuDNNLSTM, CuDNNGRU, and GAN generator/discriminator experiments.
- Converted generated token sequences back into MIDI.
- Added listening criteria and symbolic metrics for future sample scoring.

## Results

| Area | Current status |
| --- | --- |
| LSTM/GRU/GAN code | Present in notebooks and `Models/gan_final.py` |
| Generated MIDI | Existing examples are saved in `Output midi/` folders |
| Model comparison | GAN outputs were the most promising direction in the original experiments |
| Evaluation | Listening scores and symbolic metrics are the next cleanup step |
| Data rights | Source MIDI licensing needs review before any public demo |

The main lesson from this project is practical: model architecture matters, but
symbolic music generation also depends heavily on preprocessing, rhythm
representation, and how the samples are judged by ear.

## Links

- [Source repo](https://github.com/elsalmi/MusiGAN)
- [README](https://github.com/elsalmi/MusiGAN/blob/master/README.md)
- [Reproducibility notes](https://github.com/elsalmi/MusiGAN/blob/master/docs/REPRODUCIBILITY.md)
- [Data notes](https://github.com/elsalmi/MusiGAN/blob/master/docs/DATA_PROVENANCE.md)
- [Evaluation notes](https://github.com/elsalmi/MusiGAN/blob/master/docs/README_EVAL.md)
- [Sample report](https://github.com/elsalmi/MusiGAN/blob/master/reports/SAMPLE_REPORT.md)

## Risks and Tradeoffs

- Legacy TensorFlow/Keras/CuDNN APIs need pinning before reliable reruns.
- Training MIDI needs source review before a public interactive demo.
- Existing generated samples are not automatically safe to redistribute.
- Evaluation is still listening-based until sample scores and symbolic metrics
  are added.

## What I’d improve next

1. Move legacy data and checkpoints out of git into controlled storage.
2. Add a pinned legacy environment and repo-relative generation script.
3. Score one LSTM, one GRU, and one GAN sample with listening notes.
4. Add symbolic metrics such as repetition rate, note-density, interval
   distribution, and unique n-gram rate.

## Repository

- GitHub: [github.com/elsalmi/MusiGAN](https://github.com/elsalmi/MusiGAN)
