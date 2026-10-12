# Repository Guidelines

## Project Structure & Module Organization

This repository contains a buildless GitHub Pages website for CardioTech. `index.html` holds conference content, `styles.css` defines base layouts, `poster-theme.css` follows the supplied poster, and `app.js` handles programme tabs, navigation, and theme preferences. `assets/fonts/` contains self-hosted Jost fonts and their license. `assets/logos/sources.json` and `assets/people/sources.json` record logo and portrait provenance. Keep institution logos in the closing partner section only. There is no test directory.

The site uses `CardioTech_banner.png` and `cardiotech_logo.png` directly from the root. Preserve these originals and the reference document `CardioTech.pdf`. Keep conference facts tied to the official source links recorded in `README.md`.

## Build, Test, and Development Commands

No package installation or build is required. The Next.js-related entries in `.gitignore` do not establish an installed framework.

Useful checks from the repository root:

- `git status --short`: review changed and untracked files.
- `python3 -m http.server 4173`: serve the site locally.
- `node --check app.js`: check JavaScript syntax.
- `git diff --check`: detect whitespace errors in tracked changes.
- `git diff --stat`: review the scope of tracked changes.

When adding tooling, document exact installation, development, build, and test commands in `README.md`.

## Coding Style & Naming Conventions

Use two-space indentation in HTML, CSS, and JavaScript. Follow surrounding formatting; no formatter or linter is installed. Use semantic HTML, CSS custom properties for theme colors, and lowercase, hyphen-separated asset names. Preserve existing filenames unless updating all references.

## Testing Guidelines

No automated runner or coverage requirement is configured. Check desktop and mobile layouts, asset loading, light/dark themes, the mobile menu, and speaker disclosures. Verify programme tabs with arrow, Home, and End keys. Check source links and distinguish Faro 2026 dates from Madrid 2027 dates.

## Commit & Pull Request Guidelines

History contains only `Initial commit`, so no recurring commit convention exists. Use concise, imperative subjects such as `Add conference landing page`. Keep commits focused.

Pull requests should explain the change, list validation performed, and link related issues when available. Include screenshots for visual changes and identify any new dependencies or configuration requirements.

## Security & Configuration

Never commit secrets or credentials. Keep local environment files and generated output excluded by `.gitignore`; document required configuration using placeholder values.
