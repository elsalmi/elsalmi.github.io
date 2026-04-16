# Online Portfolio

This repo hosts the upgraded `elsalmi.github.io` technical portfolio site, published with GitHub Pages.

## Portfolio strategy

This portfolio-first upgrade focuses on senior-facing clarity and credibility:

- Structured project architecture and reusable templates.
- Concise project narratives with problem, method, artifacts, and risk framing.
- Automated site checks via CI.

## Current release

### v1.1 (homepage hotfix + project index polish)

- Restored homepage project thumbnails with Jekyll-safe HTML image cards.
- Removed the music-profile link from visible contact content and site metadata.
- Tightened homepage positioning and project index status language.
- Added LendingClub model-card and fairness-report links to the portfolio case study.
- Added Instrument Classification baseline report, data notes, and reproducibility
  links to the portfolio case study.

### v1 (GitHub-driven portfolio upgrade)

- Added structured homepage sections for Home, Projects, About/Resume, and Contact.
- Added portfolio information architecture in `projects/index.md`.
- Added reusable project template at `projects/_template.md`.
- Added six case-study pages:
  - `projects/musigan.md`
  - `projects/lendingclub.md`
  - `projects/instrument-classification.md`
  - `projects/qiskit.md`
  - `projects/caselaw.md`
  - `projects/copbot.md`
- Added `docs/PORTFOLIO.md` with best-work index and maturity tags.
- Added GitHub Actions CI for markdown lint, link checks, and Jekyll build.
- Updated site positioning and metadata in `_config.yml`.

## Build and QA

- Local checks:
  - `bundle install`
  - `bundle exec jekyll serve`
  - `bundle exec jekyll build`
- CI checks:
  - markdown lint
  - dead-link scan
  - Jekyll build

## Next phase

After this foundation, the same structure will be reused for remaining repositories.
