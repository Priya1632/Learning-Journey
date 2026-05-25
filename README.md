# From SAS to R, and into HEOR/RWE

A working biostatistician's applied learning journal. Built with [Quarto](https://quarto.org).

**Live site:** https://github.com/Priya1632/Learning-Journey

## What this is

A public, evolving record of my transition from clinical SAS programming into R fluency and HEOR/RWE methodology. Every entry follows a consistent template — concept, applied code, resources, my own summary, and gotchas — so it works as both a personal reference and a follow-along guide for anyone walking a similar path.

Two tracks:

- **SAS → R.** R fundamentals, tidyverse, pharmaverse, and side-by-side translations of SAS patterns.
- **HEOR & RWE.** Statistical models, causal inference and study design, the R toolchain, and a running library of resources reviewed.

## Repo structure

```
.
├── _quarto.yml              # site config
├── index.qmd                # homepage
├── about.qmd
├── sas-to-r/
│   ├── r-fundamentals/
│   ├── dplyr-tidyverse/
│   ├── pharmaverse/
│   └── sas-vs-r-patterns/
├── heor-rwe/
│   ├── stat-models/
│   ├── methods-concepts/
│   ├── tools/
│   └── resources-reviewed/
├── reference/
│   └── r-cheatsheet.qmd
├── _entry-template.qmd      # template for new entries
├── drafts/                  # gitignored — half-finished entries
└── .github/workflows/
    └── publish.yml          # auto-deploys to GitHub Pages on push to main
```

## Local preview

```bash
quarto preview
```

Renders to `_site/` and opens a live-reloading preview in the browser. (You'll need [Quarto installed](https://quarto.org/docs/get-started/) — and R if you start using executable code chunks.)

## Adding a new entry

1. Copy `_entry-template.qmd` into the right section folder.
2. Rename it descriptively (kebab-case): `propensity-score-matching-with-matchit.qmd`.
3. Fill in the template's sections. If it's not ready, drop it in `drafts/` instead.
4. Add it to the relevant section index and to `_quarto.yml` sidebar if you want it in nav.
5. Commit and push — GitHub Actions renders and publishes automatically.

## Contributing / corrections

Spot something wrong? Open an issue or a PR. Each page also has an "Edit this page" link that drops you straight into the source on GitHub.

## License

Content (text, summaries) — CC BY 4.0. Code snippets — MIT.
