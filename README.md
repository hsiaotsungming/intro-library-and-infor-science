# Intro to Information and Library Science

Working directory for building a bilingual course website about library and information science.

This project currently focuses on a static course site under `site/`, using a design direction inherited from the `Information Organization` project and adapted for this course's own content and writing preferences.

## Start Here

When a new AI or collaborator takes over, read these in order:

1. `project-config/skills/codex-working-notes.md`
2. `project-config/skills/style-consistency.md`
3. `project-config/skills/publishing-checklist.md`
4. `site/`

## Current Structure

- `site/`: publishable website files
- `project-config/`: durable working rules, style notes, workflow notes, and project skills

## Current Site Status

The current implemented module is:

- `site/ai_and_library/`

Implemented pages include:

- `site/index.html`
- `site/zh/index.html`
- `site/ai_and_library/index.html`
- `site/ai_and_library/zh.html`
- `site/ai_and_library/section-01.html`
- `site/ai_and_library/section-01-zh.html`
- `site/ai_and_library/section-02.html`
- `site/ai_and_library/section-02-zh.html`

## Important Project Preferences

- The site is bilingual, but English and Traditional Chinese should be on separate pages.
- The visual style should stay textbook-like rather than promotional.
- For Traditional Chinese pages:
  - avoid `「」` unless needed
  - avoid semicolons
  - on first mention of major concepts, prefer `中文（English）`
  - after first mention, usually continue with Chinese only
- For concept comparison, prefer card layouts instead of HTML tables.
- Keep section pages linked to nearby sections when those sections exist.

## Design Direction

- Reuse the stable page rhythm from `Information Organization`:
  - large hero
  - section navigation
  - readable section blocks
  - previous/next page links
- Do not copy content structure mechanically from that project. Adapt layout to the actual teaching material.

## Git Notes

- Do not use `git add .`
- Stage intentional paths only
- Keep macOS metadata files out of commits
- `.gitignore` already excludes `.DS_Store` and `._*`

## Handoff Note

If you are the next AI working on this project, do not start by redesigning the whole site. Read the working notes first, inspect the current `site/ai_and_library/` pages, and continue the established pattern unless the user asks for a change in direction.
