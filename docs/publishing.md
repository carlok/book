# Publishing PDFs

This repository publishes generated PDFs through GitHub Actions and GitHub
Pages.

## Current state

The workflow is defined in `.github/workflows/publish-pdfs.yml`.

It runs automatically when `main` changes in one of these paths:

- `book.tex`
- `chapters/**`
- `articles/**`
- `.github/workflows/publish-pdfs.yml`

It can also be run manually:

```bash
gh workflow run publish-pdfs.yml --ref main --repo carlok/book
```

## What the workflow builds

The workflow builds:

- `book.tex` as the integrated book PDF;
- every raw article source under `articles/math/`;
- every raw article source under `articles/non_math/`.

Most files are built with `latexmk -pdf`. The source
`articles/non_math/study_sheets_on_scientific_atheism.tex` is built with
`latexmk -xelatex`, because it declares XeLaTeX and uses `fontspec`.

The Pages artifact is assembled under:

```text
pdfs/
  index.html
  book/book.pdf
  articles/math/*.pdf
  articles/non_math/*.pdf
```

## Production publishing

The production trigger is:

```yaml
on:
  workflow_dispatch:
  push:
    branches:
      - main
    paths:
      - book.tex
      - chapters/**
      - articles/**
      - .github/workflows/publish-pdfs.yml
```

Manual runs remain available for forced rebuilds.

## Visibility note

This repository is public, and the GitHub Pages output is public. Do not publish
PDFs through this workflow unless the generated book and article PDFs are
acceptable for public Pages visibility.
