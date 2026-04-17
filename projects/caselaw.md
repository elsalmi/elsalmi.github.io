---
title: CaseLaw
tags: [nlp, legal-tech, retrieval]
permalink: /projects/caselaw
---

# CaseLaw

## TL;DR

Built a legal-text workflow that combines retrieval-oriented preprocessing with
both unsupervised and supervised summarization notebooks. The repo includes data
prep notebooks, model experiments, and a final project report.

## Problem

Legal text is long and noisy; teams need a way to move from question to relevant
sources quickly while preserving clarity and traceability.

## Data

- Inputs are case-text corpora prepared in notebook pipelines.
- The repo documentation references prepared datasets such as
  `cases_final_v1.parquet.gzip` and `cases_final_nc_cleaned_v1.parquet.gzip`.
- Source/legal-text licensing and redistribution constraints should be treated as
  a deployment boundary.

## Method

- Built data-prep and exploratory analysis notebooks to clean and shape legal text.
- Ran an unsupervised summarization path in `Project51_UnSupervised_Model.ipynb`.
- Trained a supervised seq2seq summarization model in
  `Project51_Supervised_Seq2Seq_Model.ipynb`, with an HTML export committed for review.

## Results

- The repo contains both supervised and unsupervised summarization artifacts that
  can be inspected directly.
- The supervised notebook includes a training-history plot where both training
  and validation loss decline across a 20-epoch run.
- Project documentation is captured in the committed code report PDF.

## Output sample

![CaseLaw seq2seq training vs validation loss curve](/images/caselaw-seq2seq-loss-curve.png)

Loss-curve output extracted from the committed supervised seq2seq notebook.

## Links

- [Source repo](https://github.com/elsalmi/CaseLaw)
- [Supervised seq2seq notebook](https://github.com/elsalmi/CaseLaw/blob/master/Project51_Supervised_Seq2Seq_Model.ipynb)
- [Supervised model HTML export](https://github.com/elsalmi/CaseLaw/blob/master/Project51_Supervised_Seq2Seq_Model.html)
- [Unsupervised notebook](https://github.com/elsalmi/CaseLaw/blob/master/Project51_UnSupervised_Model.ipynb)
- [Code and report PDF](https://github.com/elsalmi/CaseLaw/blob/master/Group51_109B_Code_Report-1.pdf)

## Risks

- Retrieval quality can drift quickly with preprocessing changes.
- Summaries can become misleading without citation and factuality checks.
- Dataset scope and legal-source rights must be validated before public-facing use.

## What changed

- Rewrote the page into a clear notebook-to-results narrative.
- Added a concrete output sample from the supervised model training run.
- Replaced vague follow-up language with direct links to existing project artifacts.

## What I’d improve next

1. Add a fixed evaluation set with citation-grounded summary checks.
2. Export headline quality metrics (for example ROUGE-style scores) to a stable report file.
3. Add an inference script with clear input/output contracts for reproducible reruns.
