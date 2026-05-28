# book

LaTeX drafts by Carlo Perassi.

## Documents

- `seven_strategic_challenges_europe.tex`: an article outlining seven strategic pressures facing contemporary Europe.
- `western_death.tex`: an essay on demographic change, integration, and liberal-democratic self-preservation.

## Build

Build both PDFs with `latexmk`:

```bash
mkdir -p /tmp/book-build
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/tmp/book-build \
  seven_strategic_challenges_europe.tex western_death.tex
```

The command writes PDFs and auxiliary LaTeX files to `/tmp/book-build`, keeping the repository clean.

To build a single document, pass only that `.tex` file:

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/tmp/book-build \
  seven_strategic_challenges_europe.tex
```

## Requirements

- A LaTeX distribution with `pdflatex`.
- `latexmk` for repeat builds and dependency tracking.

The current documents use only standard LaTeX packages plus `geometry` and `csquotes`.
