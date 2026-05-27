# Site And Bilingual Pattern

Date: 2026-05-27

## Decision

Use a textbook-style static website pattern inherited from the Information Organization project, but adapt it to this course with separate English and Traditional Chinese pages, card-based concept comparison, and explicit section-to-section navigation.

## Details

- Keep English and Traditional Chinese as separate pages rather than mixed on one page.
- Use the Information Organization section rhythm as the default page pattern:
  - hero
  - jump navigation
  - readable content sections
  - previous and next pager
- Prefer card layouts over HTML tables for conceptual comparison and summary content.
- For Traditional Chinese pages:
  - avoid `「」` unless clearly needed
  - avoid semicolons
  - on first mention of major concepts, prefer `中文（English）`
  - after first mention, usually continue with Chinese only
- Link implemented sections directly from the module page.
- Link adjacent sections directly once both pages exist.

## Rationale

This pattern is easier to maintain across sessions, works better for mobile and projection, supports separate refinement of English and Traditional Chinese writing, and reduces layout risk compared with table-heavy designs.
