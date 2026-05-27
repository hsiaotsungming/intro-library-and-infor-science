# GitHub Pages Setup

## Repository

`https://github.com/hsiaotsungming/information-organization-101.git`

## Published Site

`https://hsiaotsungming.github.io/information-organization-101/`

## Deployment

- Deployment method: GitHub Actions.
- Workflow file: `.github/workflows/deploy-pages.yml`
- Published site root: `site/`
- Branch: `main`

## GitHub Settings

Repository settings should use:

- `Settings` -> `Pages` -> `Source` -> `GitHub Actions`

## Notes

- The workflow uploads `site/` as the GitHub Pages artifact.
- The workflow runs on pushes to `main`.
- The workflow can also be triggered manually from GitHub Actions.
