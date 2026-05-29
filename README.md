# book

LaTeX drafts by Carlo Perassi.

## Documents

- `seven_strategic_challenges_europe.tex`: an article outlining seven strategic pressures facing contemporary Europe.
- `western_death.tex`: an essay on demographic change, integration, and liberal-democratic self-preservation.
- `limit_complex.tex`: a complex-analysis note on the limit of `(z^n - a^n) / (z - a)` across integer, rational, real, and complex exponents.
- `two_transient_spherical_signal_models.tex`: a mathematical note comparing two rational models for a transient spherical signal.

## Build

Build all PDFs with `latexmk`:

```bash
mkdir -p /tmp/book-build
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=/tmp/book-build \
  seven_strategic_challenges_europe.tex western_death.tex \
  limit_complex.tex two_transient_spherical_signal_models.tex
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

The current documents use only standard LaTeX packages plus common packages such as
`amsmath`, `amssymb`, `amsthm`, `bm`, `csquotes`, `geometry`, `lmodern`, and `mathrsfs`.
