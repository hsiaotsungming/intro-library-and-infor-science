# Project Logging Skill

Use this skill when a work session changes project structure, website behavior, publishing setup, design direction, workflow rules, or durable project knowledge.

## Purpose

Keep the long-term project understandable across separate conversations and future collaborators.

## When to Log

Create or update a log entry when:

- A new folder, workflow, or project area is created.
- GitHub Pages, deployment, or repository settings change.
- Website structure, style, or technical direction changes.
- A source set is added or reorganized.
- A decision affects future unit work.
- A published website change is committed or pushed.

## Where to Log

- Daily work notes: `logs/entries/YYYY-MM-DD.md`
- Durable decisions: `logs/decisions/YYYY-MM-DD-short-title.md`
- Production rules and reusable instructions: `project-config/`

## Entry Format

Use concise sections:

```md
# YYYY-MM-DD

## Summary

- What changed.
- What was published, if anything.
- What remains local.

## Notes

- Constraints, warnings, or follow-up context.
```

## Decision Format

Use this structure for durable decisions:

```md
# Decision Title

Date: YYYY-MM-DD

## Decision

State the decision clearly.

## Rationale

Explain why it matters for future work.

## Implications

List what future contributors should do because of this decision.
```

## Safety

- Do not publish `logs/` unless explicitly approved.
- Keep logs brief and recoverable.
- Do not paste full copyrighted source material into logs.
- Reference source files by path instead of duplicating them.
- When reading or writing Chinese Markdown logs in Windows PowerShell 5.1, explicitly use UTF-8, for example `Get-Content -Raw path\to\file.md -Encoding UTF8`, because UTF-8 files without BOM may otherwise be decoded as the system ANSI code page and appear garbled.
