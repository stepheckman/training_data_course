# Human-Centered Data Collection for Machine Learning: Lessons from Survey Research

**AAPOR Conference Short Course**
May 12, 2025 | Los Angeles, CA

**Instructors:** Stephanie Eckman (University of Maryland) and Frauke Kreuter (University of Munich / University of Maryland)

## What is this?

A 4-hour short course for survey methodologists on human-centered training data collection for ML. The course draws parallels between survey methodology and ML data pipelines, covering measurement quality, labeler representation, sampling strategies, and ethics.

This is an expanded version of a 90-minute course given at CMU in October 2025.

## Repo structure

```
slides/
  main.tex              <- Main Beamer slide deck
  references.bib        <- BibTeX references
  figures/              <- Images and diagrams
from CMU course Oct 2025/
  slides.pdf            <- Prior 90-min version (for reference)
  notes after CMU course.txt  <- Teaching notes on what to improve
relevant papers/        <- Key source papers (PDFs)
```

## How to compile

The slides are LaTeX Beamer using the **Metropolis** theme. Compile via **Overleaf** (synced through GitHub) or locally with:

```bash
cd slides
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Requires a standard TeX Live or similar distribution with the `metropolis` beamer theme installed.

## Course outline

1. **Introduction** -- Why data quality matters (Data-Centric AI, Sambasivan et al.)
2. **Survey data collection basics** -- Total Survey Error framework
3. **Training data collection** -- Data sources, labeling tasks, labeler experiences
4. **Measurement: Are the labels correct?** -- Cognitive models, design effects, pre-labeling bias, order effects
5. **Representation: Who labels?** -- Labeler diversity, nonresponse frameworks, human vs. LLM labelers
6. **Sampling: Which instances to label?** -- Random, uncertainty, diversity, active learning
7. **Ethics** -- Wages, harmful content exposure, global labor dynamics
8. **Practical advice** -- Tools, paradata, concrete recommendations

## Contributing

- Edit `slides/main.tex` for slide content
- Add references to `slides/references.bib` (author-year style via `natbib`)
- Place figures in `slides/figures/`
- See `CLAUDE.md` for detailed content and style guidelines
