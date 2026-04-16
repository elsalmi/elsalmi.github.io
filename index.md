---
layout: default
title: Home
---

# Mohamed ElSalmi

I build production-minded machine learning and data science systems with measurable outcomes, reproducible workflows, and responsible AI practices.

<nav class="home-links" aria-label="Page sections">
  <a href="#projects">Projects</a>
  <a href="#about-resume">About / Resume</a>
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
  border: 1px solid #e8e8e8;
  border-radius: 6px;
  color: #222;
  overflow: hidden;
  text-decoration: none;
  transition: border-color 160ms ease, transform 160ms ease;
}

.project-card:hover {
  border-color: #0085A1;
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
  color: #555;
  display: block;
  font-size: 0.92em;
  line-height: 1.4;
}
</style>

<a id="projects"></a>
## Featured Work

These are the projects I want people to look at first.

<div class="project-grid" role="list">
  <a class="project-card" href="/projects/musigan" role="listitem">
    <img src="/images/MusiGAN.JPG" alt="MusiGAN project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">MusiGAN</span>
      <span class="project-card__meta">Generates MIDI sketches by comparing LSTM, GRU, and GAN models.</span>
    </span>
  </a>
  <a class="project-card" href="/projects/lendingclub" role="listitem">
    <img src="/images/LC-Logo-Official-min-1024x418.png" alt="LendingClub Fairness project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">LendingClub Fairness</span>
      <span class="project-card__meta">Predicts loan outcomes and audits fairness across proxy groups.</span>
    </span>
  </a>
  <a class="project-card" href="/projects/instrument-classification" role="listitem">
    <img src="/images/instrument_classification.png" alt="Instrument Classification project thumbnail">
      <span class="project-card__body">
      <span class="project-card__title">Instrument Classification</span>
      <span class="project-card__meta">Classifies NSynth notes with random forest baselines and CNN experiments.</span>
    </span>
  </a>
</div>

| Project | Focus | Status |
| --- | --- | --- |
| [MusiGAN](/projects/musigan) | Symbolic music generation with LSTM/GRU/GAN tradeoffs | Active showcase |
| [LendingClub Fairness](/projects/lendingclub) | Credit prediction with fairness diagnostics and mitigation | Active showcase |
| [Instrument Classification](/projects/instrument-classification) | Audio instrument recognition with measured model evaluation | Active showcase |
| [Qiskit Hub](https://github.com/elsalmi/qiskit) | Quantum computing learning projects | Curated link |
| [CaseLaw](https://github.com/elsalmi/CaseLaw) | Legal case retrieval and summarization pipeline | Reference |

Browse the full project list and filters at [Projects](/projects/).

<a id="about-resume"></a>
## About / Resume

I’m a data science engineer focused on:

- Designing reliable ML systems for real users.
- Turning notebooks into reproducible workflows.
- Reporting results with measurable impact and responsible AI checks.
- Shipping practical work such as demos, metrics, and documentation.

<a id="contact"></a>
## Contact

- LinkedIn: [mohamed-elsalmi](https://www.linkedin.com/in/mohamed-elsalmi/)
- GitHub: [github.com/elsalmi](https://github.com/elsalmi)
