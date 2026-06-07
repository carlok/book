# Publishing PDFs

This repository publishes generated PDFs through GitHub Actions and GitHub
Pages.

## Current state

The workflow is defined in `.github/workflows/publish-pdfs.yml`.

It is currently manual-only:

```bash
gh workflow run publish-pdfs.yml --ref codex/book-first-look --repo carlok/book
```

This is deliberate while the workflow is being tested on
`codex/book-first-look`. It prevents accidental publication from every push.

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

After the branch is tested and merged to `main`, the workflow can be made
automatic by adding push triggers for:

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

Until that change is made, publishing requires a human to run the workflow
manually.

## Visibility note

GitHub Pages may expose the generated PDFs publicly, depending on the
repository and account settings. Do not publish PDFs through this workflow
unless the generated book and article PDFs are acceptable for Pages visibility.
