# CSE 219 Resources

Teaching resources for **CSE 219: Signals and Linear Systems**. The repository
keeps LaTeX source files and their rendered PDFs together.

## Author

Prepared and maintained by **Ashrafur Rahman**, Lecturer, Department of Computer
Science and Engineering, BUET.

## Repository Layout

| Path | Contents |
| --- | --- |
| `slides/` | Beamer lecture decks for DFT review, FFT, sampling, Laplace transform, and z-transform topics. Shared slide styling lives in `slides/preamble.tex`. |
| `practice-set/` | Practice question and practice sheet LaTeX sources with generated PDFs. |
| `ct/` | Class test, makeup test, and solution source/PDF files. |

## Lecture Decks

The `slides/` directory is organized by lecture number and topic:

1. Recap on DFT
2. The Fast Fourier Transform
3. Advanced FFT
4. Advanced FFT and Applications
5. Sampling
6. The Laplace Transform
7. More Laplace Transform
8. The z-Transform

Each deck has a `main.tex` source file and a generated `main.pdf`. Most decks
load the shared preamble from `slides/preamble.tex`, so changes to typography,
colors, packages, or common commands should usually be made there.

## Building PDFs

A full TeX Live installation is recommended. The materials use packages such as
Beamer, Metropolis, TikZ, pgfplots, tcolorbox, exam, FiraSans, and FiraMono.
XeLaTeX is the safest default because several files are annotated for it and the
repository uses Fira fonts.

Compile a lecture deck:

```bash
cd "slides/1 - Recap on DFT"
latexmk -xelatex main.tex
```

Compile practice materials:

```bash
cd practice-set
latexmk -xelatex practice_sheet.tex
latexmk -xelatex practice_questions.tex
```

Compile class test materials:

```bash
cd ct
latexmk -xelatex main.tex
latexmk -xelatex soln.tex
latexmk -xelatex makup.tex
latexmk -xelatex makeup_soln.tex
```

If `latexmk` is unavailable, run `xelatex` on the target `.tex` file directly,
repeating the command if cross-references or tables of contents need another
pass.
