# Training Data Collection Course

## Project Overview

This repo contains LaTeX Beamer slides for a **4-hour short course** on human-centered training data collection for ML, drawing on lessons from survey methodology.

- **Title:** Human-Centered Data Collection for Machine Learning: Lessons from Survey Research
- **Venue:** AAPOR Conference, May 12, 2025, Los Angeles, CA
- **Instructors:** Stephanie Eckman (University of Maryland) and Frauke Kreuter (University of Munich / University of Maryland)
- **Audience:** Survey methodologists (people with survey background learning about ML/AI training data)
- **Duration:** 4 hours (expanded from a 90-minute version given at CMU in Oct 2025)
- **Format:** Lecture + discussion (no hands-on exercises, but include discussion break slides)

## Prior Version

The `from CMU course Oct 2025/` directory contains:
- `slides.pdf` -- the 90-minute CMU version (62 slides, PowerPoint-origin PDF)
- `notes after CMU course.txt` -- teaching notes on what to improve

### Key lessons from CMU version (apply these to new slides):
- Relocate pre-labeling content so it is better motivated before it appears
- Too many slides for 90 min; now we have 4 hours so we can go deeper
- Evaluation studies section is where representation is most important -- expand this
- Show results from survey literature to motivate what we expect in labeling
- Concrete takeaways are of most interest to practitioners
- Structure around: overview of design elements, hypotheses about effects, show studies where effects appear (per FK's suggestion)

## Technical Setup

### LaTeX / Beamer
- **Theme:** Metropolis (`\usetheme{metropolis}`)
- **Compilation:** Via Overleaf (synced through GitHub)
- **Bibliography:** BibTeX with `natbib` (author-year style)
  - Use `\bibliographystyle{plainnat}` or similar author-year style
  - Bib file: `references.bib`
- Slides should compile cleanly with standard Overleaf LaTeX distribution

### File Structure
```
training_data_course/
  CLAUDE.md
  slides/
    main.tex          -- main beamer file
    references.bib    -- bibliography
    figures/           -- image files (PDFs, PNGs)
  from CMU course Oct 2025/
    slides.pdf
    notes after CMU course.txt
```

### Figures
- Key figures will come from PDF papers (Kern et al, Beck et al, Eckman et al) placed in `slides/figures/`
- Use `\includegraphics` with filenames that clearly describe the figure
- For simple diagrams (e.g., the Total Survey Error framework, nonresponse bias DAG), recreate in TikZ when feasible
- For complex figures from papers (charts, screenshots), clip from PDFs using `\includegraphics[page=X, trim=... clip]`

## Course Content Structure

The CMU version had this outline (expand each section significantly for 4 hours):

1. **Introduction**
   - Who we are
   - Why data work matters (Data Centric AI, Sambasivan et al, Sculley et al)
   - Current events motivating data quality

2. **Survey Data Collection Basics**
   - What surveys look like
   - Total Survey Error framework (Measurement + Representation)
   - Error sources: invalidity, measurement error, processing error, coverage, sampling, nonresponse, adjustment

3. **Training Data Collection**
   - Data sources: survey/federal data, web scraping, human-in-the-loop
   - Examples of labeling tasks (RLHF interfaces, image classification, NER)
   - Labeler stories (human side)

4. **Measurement: Are the Labels Correct?**
   - Cognitive model of survey response (Comprehension -> Recall -> Judgement -> Response)
   - Construct-to-measurement path
   - Research design effects on labels (Kern et al 2023 -- hate speech/offensive language experiment)
   - Pre-labeling / automation bias (Beck et al 2025)
   - Order effects in labeling (Beck et al 2024)
   - Guidelines from survey design (attitude questions, response scales)

5. **Representation: Who Labels?**
   - Who labels (experts, researchers, crowdworkers, LLMs)
   - Nonresponse bias framework applied to labeling
   - Labeler diversity and its impact on labels and models
   - Labeler characteristics impact labels (Otterbacher et al) and models (Al Kuwalty et al)
   - Can models replace human labelers? (model collapse, same biases)

6. **Sampling: Which Instances to Label?**
   - Simple random sampling
   - Uncertainty sampling, diversity sampling, active learning
   - How many labels needed

7. **Ethics**
   - Wages and benefits for data workers
   - Exposure to harmful content
   - Global labor dynamics (wealthy countries commissioning, lower-income countries labeling)
   - Human subjects / IRB considerations

8. **Label Collection Tools & Concrete Advice**
   - Open-source vs commercial tools
   - Paradata collection gaps
   - Practical recommendations

9. **Discussion**

## Communication

- Refer to Stephanie as "Boss"

## Slide Design Philosophy

Follow the **Rhetoric of Decks** philosophy (see `.claude/commands/compiledeck.md` and invoke with `/compiledeck`).

Key principles for this deck:
- **Audience type:** External (conference teaching) -- sparse, performative, one idea per slide
- **Tone:** Professional/Academic -- consistent house style
- **Theme:** Metropolis beamer theme (overrides the default theme in compiledeck; use Metropolis colors/structure but apply Rhetoric of Decks principles)
- **Titles are assertions, not labels** -- if someone reads only titles in sequence, they should follow the argument
- **One idea per slide** -- strictly enforced
- **Beauty is function** -- every element earns its presence
- **White space is confidence** -- don't fill slides
- **Charts:** one message per chart, direct labels, no legends requiring eye movement
- **Minimum font:** 24pt body (18pt floor)

### Content-Specific Style Notes
- Academic but accessible tone; audience knows surveys well but may be new to ML
- Use concrete examples and real studies throughout
- Include full citations on slides (author, year, DOI/URL) -- this audience values that
- Slide numbers on every slide
- Section divider slides for major topic transitions
- Discussion prompt slides between major sections
- No emojis

## References (from CMU version, seed the .bib file)

Key papers to include:
- Sambasivan et al, 2021 (doi:10.1145/3411764.3445518) -- "Everyone wants to do the model work"
- Sculley et al, NIPS 2015 -- Hidden Technical Debt in ML Systems
- Andrew Ng, 2021 -- Data Centric AI
- Kern et al, 2023 (https://aclanthology.org/2023.findings-emnlp.992/) -- annotation design effects on hate speech
- Beck et al, 2025 (https://arxiv.org/abs/2509.08514) -- pre-labeling / automation bias
- Beck et al, 2024 (https://aclanthology.org/2024.uncertainlp-1.8.pdf) -- order effects in labeling
- Otterbacher et al -- DESCANT: Detecting Stereotypes in Human Computational Tasks
- Al Kuwalty et al -- Identifying and Measuring Annotator Bias Based on Demographics
- Monarch, 2021 -- Human-in-the-Loop Machine Learning (book)
- Sudman & Bradburn, 1982 -- question design
- Krosnick & Presser, 2010 -- question and questionnaire design
- Ouyang et al, 2022 (https://arxiv.org/abs/2203.02155) -- InstructGPT / RLHF interface
- Shumailov et al, 2023 (https://arxiv.org/abs/2305.17493) -- model autophagy / collapse
- NLPerspectives 2024 (https://aclanthology.org/2024.nlperspectives-1.1/) -- bird classification example
