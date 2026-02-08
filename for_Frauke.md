# Getting Started with Our Slide Repository

Hi Frauke! This document walks you through everything you need to collaborate on our AAPOR short course slides. The slides are written in LaTeX (Beamer) and live in a GitHub repository. We use Overleaf to edit and compile them, with GitHub keeping everything in sync.

**Good news:** Everything here runs in your web browser -- no software to install on your PC. You just need a GitHub account and an Overleaf account.

## Overview of the Setup

```
You (Overleaf) <---> GitHub <---> Steph (Overleaf or local)
```

Both of us can edit the slides. GitHub is the central hub that keeps our versions in sync.

---

## Step 1: Create a GitHub Account (if you don't have one)

1. Go to [github.com](https://github.com)
2. Click **Sign up**
3. Follow the prompts (free account is fine)
4. Let Steph know your username so she can add you as a collaborator on the repository

---

## Step 2: Accept the Repository Invitation

Once Steph adds you as a collaborator:

1. Check your email for an invitation from GitHub
2. Click **Accept invitation**
3. You should now see the repository at its GitHub URL (Steph will send you the link)

---

## Step 3: Link Overleaf to GitHub

This lets you edit the LaTeX slides in Overleaf's nice visual editor, with changes syncing back to GitHub.

1. Go to [overleaf.com](https://www.overleaf.com) and log in (or create a free account)
2. Click **New Project** (green button, top left)
3. Select **Import from GitHub**
4. If this is your first time, Overleaf will ask you to connect your GitHub account -- follow the prompts to authorize it
5. You should see the repository in the list -- click **Import**
6. Overleaf will create a project with all the files from the repository

---

## Step 4: Editing Slides

The main file to edit is:

```
slides/main.tex
```

This is a standard LaTeX Beamer file. If you've used LaTeX before, it will look familiar. The slides use the **Metropolis** theme, which gives them a clean, modern look.

### How to add or edit a slide

Each slide looks like this in the source:

```latex
\begin{frame}{Your Slide Title Here}

    Your content here.

    \begin{itemize}
        \item First point
        \item Second point
    \end{itemize}

\end{frame}
```

Section dividers look like this:

```latex
\section{Section Name}
```

### Compiling

In Overleaf, just click the green **Recompile** button (or it may auto-compile). The PDF preview appears on the right side of the screen.

### References

We use a bibliography file (`slides/references.bib`). To cite a paper on a slide:

```latex
\cite{kern2023}           % produces: Kern et al. (2023)
\citep{kern2023}          % produces: (Kern et al., 2023)
```

---

## Step 5: Syncing Changes with GitHub

This is the most important part for collaboration. After you make edits in Overleaf:

1. Click the **Menu** button (top left in Overleaf)
2. Look for the **GitHub** section in the menu
3. Click **Push Overleaf changes to GitHub**
4. Add a brief description of what you changed (e.g., "Added slides on labeler diversity")
5. Click **Submit**

Before you start editing each time:

1. Open the **Menu**
2. Click **Pull GitHub changes to Overleaf**
3. This grabs any changes Steph has made since you last worked on the slides

### The Golden Rule

**Always pull before you start editing, and push when you're done.** This prevents us from accidentally overwriting each other's work.

---

## Step 6: Adding Figures

To add an image to the slides:

1. In Overleaf, upload the image file to the `slides/figures/` folder (drag and drop works)
2. In the LaTeX source, add:

```latex
\begin{frame}{Your Slide Title}
    \centering
    \includegraphics[width=0.8\textwidth]{figures/your-image-name.pdf}
\end{frame}
```

PDF and PNG formats work best.

---

## Quick Reference Card

| Task | How |
|------|-----|
| Open slides for editing | Open Overleaf project, navigate to `slides/main.tex` |
| See the compiled PDF | Click green **Recompile** button in Overleaf |
| Get Steph's latest changes | Menu > GitHub > Pull |
| Share your changes | Menu > GitHub > Push (add a brief description) |
| Add a figure | Upload to `slides/figures/`, use `\includegraphics` |
| Add a reference | Add entry to `slides/references.bib`, use `\cite{key}` |

---

## File Structure

```
training_data_course/
  slides/
    main.tex            <-- the slide deck (this is what we edit)
    references.bib      <-- bibliography
    figures/             <-- images and diagrams
  from CMU course Oct 2025/
    slides.pdf           <-- our earlier 90-min version for reference
    notes after CMU course.txt
  CLAUDE.md              <-- project notes (for Steph's AI assistant)
  for Frauke.md          <-- this document
  relevant papers/       <-- ours and other papers we want to draw upon
```

---

## Troubleshooting

**Overleaf won't compile:**
- Check the log file (click the log icon next to Recompile) for error messages
- Common issue: a missing `}` or `\end{frame}`
- If stuck, message Steph

**GitHub sync conflict:**
- This happens if we both edited the same lines
- Overleaf will show a conflict message
- Usually easiest to resolve by copying your changes, pulling the latest version, and re-applying your edits
- Or just message Steph and we'll sort it out together

**Can't find the repository in Overleaf:**
- Make sure you accepted the GitHub invitation (Step 2)
- Try disconnecting and reconnecting GitHub in Overleaf settings

---

## Questions?

Just message Steph! None of this is hard once you've done it once.
