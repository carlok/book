# Book Enhancement Suggestions

These notes collect future improvements for the integrated book without moving
them into the book body.

## Structure

- Decide whether the math section should settle into a stable order such as
  foundations, geometry, dynamics, morphology, games, and aesthetics.
- Add short part introductions once the chapter set stabilizes.
- Consider grouping macro-political essays under a dedicated part title if the
  non-math section grows.

## Chapter Uniformity

- Give every chapter the same basic frame: abstract, introduction, main body,
  conclusion, and bibliography only where it is actually used.
- Keep article sources intact, but let chapter copies become the edited book
  versions.
- Standardize theorem, definition, remark, and proof environments across the
  math chapters.

## Bibliography Strategy

- Decide whether bibliographies should remain per chapter or move to one final
  book bibliography.
- If moving to a final bibliography, convert chapter-local citations gradually
  so each source is cited where it is used.
- Avoid keeping unused bibliographies in chapter copies.

## Review Passes

- Continue marking extra-high review status in
  `docs/math-extra-high-checklist.md`.
- For technical chapters, add a short "what would need proof" note when the
  text is exploratory rather than theorem-complete.
- Run periodic standalone article builds after broad source-date or package
  changes, not only book builds.

## Publication

- Keep the `/pdfs/` index as the canonical public entry point for readers.
- Add a short generated build timestamp to the PDF index only if it becomes
  useful for verifying Pages deployments.
- Consider changed-only article builds later if the full batch becomes slow.
