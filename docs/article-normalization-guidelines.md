# Article Normalization Guidelines

Standalone article sources should share a predictable structure while preserving
the local machinery each article genuinely needs.

## Standard Structure

Use this order unless an article has a deliberate custom title page:

```tex
\documentclass[11pt,a4paper]{article}

% Encoding and typography
% Common packages
% Article-specific packages, theorem environments, and macros

\title{...}
\author{Carlo Perassi}
\date{fixed date}

\begin{document}
\maketitle

\begin{abstract}
...
\end{abstract}

\section{Introduction}
...

% Body sections

\section{Conclusion}
...

% Bibliography only if cited or otherwise used

\end{document}
```

## Local Exceptions

- Keep engine-specific setup such as `fontspec` for XeLaTeX articles.
- Keep visual systems such as custom title pages, `tcolorbox`, TikZ, and
  article-specific color palettes when they are part of the article's design.
- Keep local theorem environments, labels, citations, macros, and mathematical
  notation with the article that needs them.
- Do not add keywords blocks after abstracts.
- Use fixed dates, not `\today` or dynamic year expressions.

## Review Rule

Mark an article normalized only after its source has the standard metadata
order, abstract/introduction/conclusion framing, and a successful standalone
compile with its required engine.
