# Collaboration Workflow

## Roles

- The user provides source materials, course direction, content basis, and visual preferences.
- Codex handles website implementation, structure, technical maintenance, and GitHub Pages deployment.

## Local Areas

- `sources/`: original materials.
- `generated/`: AI-assisted drafts and intermediate assets.
- `logs/`: project logs and durable decisions.
- `project-config/`: working knowledge for website production.
- `site/`: publishable website files.

## Publishing Rule

- Commit and push confirmed website files from `site/`.
- Commit GitHub infrastructure files, such as `.github/workflows/`, only when required for publishing.
- Do not publish local working areas unless explicitly approved.
- Avoid `git add .`; stage paths intentionally.

## Unit Work

- Unit-level work may happen in separate conversations.
- Each unit should identify its scope before implementation.
- Avoid changing unrelated units during a unit-specific conversation.
