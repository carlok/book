# book

LaTeX drafts by Carlo Perassi.

## Documents

- `book.tex`: first integrated book draft importing the standalone articles in
  non-math and math groups.
- `articles/non_math/`: essay and cultural/political drafts.
- `articles/math/`: mathematical, computational, and formal-model drafts.
- `proposals/book_structure_proposal.tex`: preliminary structure proposal.

## Build

Build the integrated book draft with `pdflatex`:

```bash
mkdir -p /tmp/book-build
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=/tmp/book-build book.tex
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=/tmp/book-build book.tex
```

The repeated run stabilizes the table of contents and PDF outlines. The command
writes `/tmp/book-build/book.pdf` and auxiliary LaTeX files outside the
repository.

Build standalone article PDFs with `latexmk`:

```bash
mkdir -p /tmp/book-build
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/tmp/book-build \
  articles/non_math/seven_strategic_challenges_europe.tex \
  articles/non_math/western_death.tex \
  articles/math/limit_complex.tex \
  articles/math/two_transient_spherical_signal_models.tex
```

The command writes PDFs and auxiliary LaTeX files to `/tmp/book-build`, keeping the repository clean.

To build a single document, pass only that `.tex` file:

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/tmp/book-build \
  articles/non_math/seven_strategic_challenges_europe.tex
```

## Requirements

- A LaTeX distribution with `pdflatex`.
- `latexmk` for repeat builds and dependency tracking.

The current documents use only standard LaTeX packages plus common packages such as
`amsmath`, `amssymb`, `amsthm`, `bm`, `booktabs`, `csquotes`, `geometry`,
`hyperref`, `lmodern`, `mathrsfs`, `stmaryrd`, `tcolorbox`, `tikz`, and
`titlesec`.
