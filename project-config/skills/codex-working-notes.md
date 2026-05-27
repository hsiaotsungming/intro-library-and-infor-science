# Codex Working Notes

## Required Context

Before major website work, review:

- `README.md`
- `project-config/`
- `site/`

For work that changes project structure, publishing, design direction, workflow rules, or durable project knowledge, also follow:

- `project-config/skills/project-logging.md`

For publishing work, also follow:

- `project-config/skills/publishing-checklist.md`

For page, component, visual, or unit design work, also follow:

- `project-config/skills/style-consistency.md`

For saving or organizing images for a page, also follow:

- `project-config/skills/page-assets.md`

For cropping how an image appears on a page without permanently editing the image file, also follow:

- `project-config/skills/display-image-crop.md`

## Current Project State

- The main website work is currently under `site/`.
- The active course site is bilingual, with separate English and Traditional Chinese pages.
- The current implemented module is `site/ai_and_library/`.
- Completed section pages:
  - `site/ai_and_library/section-01.html`
  - `site/ai_and_library/section-01-zh.html`
  - `site/ai_and_library/section-02.html`
  - `site/ai_and_library/section-02-zh.html`

## Important Working Preferences

- Reuse the visual system inherited from `Information Organization`, but do not copy content structure blindly.
- Keep the site textbook-like, quiet, and reading-centered.
- Prefer separate bilingual pages over mixed-language pages.
- For Traditional Chinese pages:
  - avoid `「」` unless clearly needed
  - avoid semicolons
  - on first mention, prefer `中文（English）` for major concepts
  - after first mention, usually use Chinese only
- When comparing concepts, prefer card-based comparisons over HTML tables.
- For summaries, prefer short cards or short closing paragraphs instead of abstract layered frameworks.
- Section pages should link clearly to the previous and next sections when available.

## Design Lessons Already Learned

- Table layouts are fragile in this project and should be avoided for conceptual comparison when cards can do the job.
- Horizontal comparison cards are more stable than tables for mobile and desktop.
- Summary sections should stay concise and should not add extra conceptual labels unless the user explicitly wants them.
- Each section page should feel like a complete reading unit, not just an expanded card from the module page.
- Module pages should link directly into implemented section pages.

## Expected Behavior

- Keep source materials and website output separate.
- Preserve local-only areas unless the user explicitly approves publication.
- Use professional, concise textbook-style design.
- Keep typography consistent and suitable for projection and mobile browsing.
- Store page-specific images in that page's local `assets/` folder.
- Prefer non-destructive display cropping for page images unless permanent image editing is requested.
- Prefer maintainable HTML and TypeScript.
- Use GitHub Pages deployment through the existing workflow if publishing infrastructure is added later.
- Update project notes when the work creates durable context for future conversations.

## Git Safety

- Stage only intentional paths.
- Do not use `git add .`.
- Check `git status --short` before commit.
- Confirm that `project-config/` is not staged unless explicitly requested.
- Ignore macOS metadata such as `.DS_Store` and `._*`.
