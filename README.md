# cs-notes

Personal learning notes from Carnegie Mellon University's
[AI Engineering Fundamentals graduate certificate](https://www.cmu.edu/online/ai-engineering-fundamentals),
starting with course **24-887 — Machine Learning & AI for Engineers**.

The notes are the *source of truth*; the published website is rendered from them
with [Quarto](https://quarto.org) and deployed to GitHub Pages by CI — so the
notes and the rendered pages stay decoupled.

**Live site:** https://panjunbiao.github.io/cs-notes

## Repository layout

```
.
├── _quarto.yml                 # Quarto website config
├── index.qmd                   # landing page
├── notes/                      # prose notes (.qmd, real LaTeX math)
│   └── logistic-regression/    # one folder per topic module
│       ├── index.qmd                    # module landing page (published)
│       ├── two-class-linear.qmd         # cleaned/corrected note (published)
│       └── _two-class-linear.source.md  # verbatim original source (committed, NOT published)
├── notebooks/                  # Jupyter notebooks (.ipynb), published via Quarto
├── assets/img/                 # figures / diagrams
├── _source/                    # private raw scans/originals (git-ignored, local only)
├── .github/workflows/publish.yml   # render + deploy to GitHub Pages
└── _site/                      # rendered output (git-ignored, built by CI)
```

## Writing notes

Add a `.qmd` (prose) or `.ipynb` (notebook) file, then register it in the
`website.sidebar` / `navbar` section of `_quarto.yml`. Push to `main` and CI
renders and deploys automatically.

**Source vs. published.** Each polished note may keep a companion verbatim
transcription of the original derivation as `_<name>.source.md`. The leading `_`
tells Quarto to skip it during rendering, so it is **versioned in git but never
published** — a faithful record (mistakes preserved) that the cleaned `.qmd` is
based on.

## Local preview (optional)

Install [Quarto](https://quarto.org/docs/get-started/) (and Jupyter if you use
notebooks), then:

```bash
quarto preview      # live-reloading local preview
quarto render       # one-off full build into _site/
```

## Publishing / deployment

Deployment is fully automated via GitHub Actions
(`.github/workflows/publish.yml`) on every push to `main`. This requires a
**one-time** setting in the repo: **Settings → Pages → Build and deployment →
Source: GitHub Actions**.

## Acknowledgment

Course material and problem framing are from CMU's **24-887 — Machine Learning &
Artificial Intelligence for Engineers** (instructor: Dr. Levent Burak Kara), part
of the [AI Engineering Fundamentals](https://www.cmu.edu/online/ai-engineering-fundamentals)
graduate certificate. These are my own study notes; any errors are mine.
