# book

LaTeX drafts by Carlo Perassi.

Published Pages and PDFs:

- [Main repository](https://github.com/carlok/book/tree/main)
- [PDF home](https://carlok.github.io/book/pdfs/)
- [Book PDF](https://carlok.github.io/book/pdfs/book/book.pdf)
- [Article PDF index](https://carlok.github.io/book/pdfs/)

## Documents

- `book.tex`: first incremental book draft importing editable chapter copies in
  math-first order.
- `chapters/math/`: book chapter copies converted from mathematical,
  computational, and formal-model drafts.
- `chapters/non_math/`: book chapter copies converted from essay and
  cultural/political drafts.
- `articles/non_math/`: essay and cultural/political drafts.
- `articles/math/`: mathematical, computational, and formal-model drafts.
- `archive/book_structure_proposal.tex`: older preliminary structure proposal.
- `docs/math-extra-high-checklist.md`: review-status checklist for the
  mathematical article/chapter pairs.
- `docs/book-enhancement-suggestions.md`: future improvement notes for the
  integrated book.
- `docs/article-normalization-guidelines.md`: shared structural pattern for
  standalone article sources.
- `docs/article-normalization-checklist.md`: normalization status for article
  sources.

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

## Publishing

The GitHub Pages PDF publishing workflow is documented in
`docs/publishing.md`.
