---
layout: default
title: Home
---

# Mohamed ElSalmi

I build applied machine-learning work that can be checked, reused, and defended on the merits.

Most of these projects started as notebooks. I rewrote them so the data, method, results, and tradeoffs are all in one place. I care more about evidence than adjectives.

The three main case studies now point back to the source docs and rebuild paths too: Qiskit has reproducibility notes, LendingClub has a generated fairness report, and Instrument Classification has a pinned legacy environment plus a report rebuild script.

<nav class="home-links" aria-label="Page sections">
  <a href="#projects">Projects</a>
  <a href="#focus">Focus</a>
  <a href="#contact">Contact</a>
</nav>

<style>
.home-links {
  display: flex;
  flex-wrap: wrap;
  gap: 10px 16px;
  margin: 16px 0 24px;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 16px;
  margin: 16px 0 24px;
}

.project-card {
  display: block;
  border: 1px solid var(--mm-line, #e8e8e8);
  border-radius: 6px;
  color: var(--mm-ink, #222);
  background: var(--mm-paper-soft, #fcf8f4);
  overflow: hidden;
  text-decoration: none;
  transition: border-color 160ms ease, box-shadow 160ms ease, transform 160ms ease;
}

.project-card:hover {
  border-color: var(--mm-accent-dark, #8b2d3f);
  box-shadow: 0 8px 20px rgba(11, 16, 32, 0.12);
  transform: translateY(-2px);
}

.project-card img {
  aspect-ratio: 16 / 10;
  background: #f5f5f5;
  display: block;
  object-fit: cover;
  width: 100%;
}

.project-card__body {
  display: block;
  padding: 12px;
}

.project-card__title {
  display: block;
  font-weight: 700;
  margin-bottom: 4px;
}

.project-card__meta {
  color: var(--mm-ink-muted, #555);
  display: block;
  font-size: 0.92em;
  line-height: 1.4;
}
</style>

<a id="projects"></a>
## Featured Work

These are the projects that best represent the work here.

<div class="project-grid" role="list">
  <a class="project-card" href="/projects/musigan" role="listitem">
    <img src="/images/MusiGAN.JPG" alt="MusiGAN project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">MusiGAN</span>
      <span class="project-card__meta">Symbolic music generation with sample outputs and provenance notes.</span>
    </span>
  </a>
  <a class="project-card" href="/projects/lendingclub" role="listitem">
    <img src="/images/LC-Logo-Official-min-1024x418.png" alt="LendingClub Fairness project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">LendingClub Fairness</span>
      <span class="project-card__meta">Loan-risk modeling with a model card, fairness report, and rebuild script.</span>
    </span>
  </a>
  <a class="project-card" href="/projects/instrument-classification" role="listitem">
    <img src="/images/instrument_classification.png" alt="Instrument Classification project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">Instrument Classification</span>
      <span class="project-card__meta">NSynth classification with a pinned environment and report rebuild path.</span>
    </span>
  </a>
  <a class="project-card" href="/projects/qiskit" role="listitem">
    <img src="/images/qiskit.jpg" alt="Qiskit Hub project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">Qiskit Hub</span>
      <span class="project-card__meta">Qiskit tutorials with reproducibility notes and deterministic simulator output.</span>
    </span>
  </a>
</div>

| Project | What it shows | Status |
| --- | --- | --- |
| [MusiGAN](/projects/musigan) | Symbolic music generation with sample outputs and provenance notes | Featured |
| [LendingClub Fairness](/projects/lendingclub) | Loan-risk modeling with a model card, fairness report, and rebuild script | Featured |
| [Instrument Classification](/projects/instrument-classification) | Audio classification with a pinned environment and report rebuild path | Featured |
| [Qiskit Hub](/projects/qiskit) | Quantum tutorials with reproducibility notes and deterministic simulator output | Featured |
| [CaseLaw](/projects/caselaw) | Legal retrieval and summarization reference with supervised and unsupervised notebooks | Reference |

Browse the full project list and filters at [Projects](/projects/).

The featured technical case studies link back to repo docs, report snapshots, and rebuild scripts so the evidence is traceable instead of implied.

<a id="focus"></a>
## Focus

What I care about is simple:

- Start with the question and the constraint that matters.
- Keep the evaluation visible, even when the answer is messy.
- Leave behind something another person can actually use.

If a project needs a long explanation to sound important, it probably needs another pass.

<a id="contact"></a>
## Contact

- LinkedIn: [mohamed-elsalmi](https://www.linkedin.com/in/mohamed-elsalmi/)
- GitHub: [github.com/elsalmi](https://github.com/elsalmi)
