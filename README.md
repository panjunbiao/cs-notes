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
├── notebooks/                  # Jupyter notebooks (.ipynb), published via Quarto
├── assets/img/                 # figures / diagrams
├── _source/                    # raw scans & originals (NOT published)
├── .github/workflows/publish.yml   # render + deploy to GitHub Pages
└── _site/                      # rendered output (git-ignored, built by CI)
```

## Writing notes

Add a `.qmd` (prose) or `.ipynb` (notebook) file, then register it in the
`website.sidebar` / `navbar` section of `_quarto.yml`. Push to `main` and CI
renders and deploys automatically.

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
