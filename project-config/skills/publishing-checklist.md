# Publishing Checklist Skill

Use this skill whenever a change is prepared for Git commit, push, or GitHub Pages publication.

## Purpose

Prevent accidental publication of local source materials, drafts, logs, or project configuration files.

## Before Commit

- Run `git status --short`.
- Confirm the intended publication scope.
- Stage only intentional paths.
- Prefer:
  - `git add site`
  - `git add .github/workflows/<workflow-file>`
- Avoid `git add .`.

## Allowed by Default

- `site/`: confirmed website output.
- `.github/workflows/`: only when publishing infrastructure must change.

## Local Unless Explicitly Approved

- `sources/`
- `generated/`
- `logs/`
- `project-config/`
- root `README.md`
- `.DS_Store`

## Before Push

- Run `git diff --cached --name-only`.
- Confirm no local-only folders are staged.
- Use a concise commit message that describes the published change.
- When the user asks to push a specific page or file update, default to only the directly requested git steps:
  - stage the specified paths
  - commit the specified paths
  - push the resulting commit
- Unless the user explicitly asks for more, do not add extra cleanup or side work during that push flow, such as:
  - permission-bit cleanup
  - log updates
  - skill updates
  - unrelated staging
  - broader repository housekeeping
- Push to `origin main` only after the commit scope is verified.

## After Push

- Check GitHub Actions for the Pages deployment.
- Confirm the site URL if the change affects visible pages.
- Update `logs/entries/YYYY-MM-DD.md` when the publication creates durable project context.
