<!-- .github/copilot-instructions.md - Guidance for AI coding agents -->
# Copilot instructions for this repository

Purpose: Quickly orient AI agents to be productive in this GitHub Pages static site repository.

- Big picture:
  - This is a simple static website (GitHub Pages). Main entry is `index.html` at repository root.
  - Site-wide configuration (if used) is `_config.yml`. There are no build scripts by default.
  - Static assets live in `css/`, `js/`, `images/`, and `files/`.

- Key files and where to start:
  - `index.html` — primary landing page and canonical place for layout edits.
  - `_config.yml` — site settings (only relevant if Jekyll/GitHub Pages processing is used).
  - `about.html` — example content page to mirror patterns for new pages.
  - `css/` — CSS sources and minified variants (project uses Tailwind via CDN and `output.css` for built styles).
  - `js/` — JS bundles and minified copies.

- Local dev / preview
  - No build system required. For a quick preview serve the folder over HTTP:

    python -m http.server 8000

  - If you want a Node-based static server (optional):

    npx http-server . -p 8080

  - If contributors use Jekyll (not required here), use `bundle exec jekyll serve` — only when Ruby & Bundler are present.

- Project conventions and important patterns
  - Keep asset structure stable: modify files in `css/`, `js/`, `images/`, and mirror changes to any minified siblings.
  - Prefer editing non-minified sources (e.g., `css/output.css`) and update/minify outputs only when necessary.
  - HTML files are served as-is; avoid introducing server-side code or build steps without discussion.

- Integration points and deployment
  - This site is intended for GitHub Pages. Deploy by merging to the branch configured in repository settings (commonly `main`).
  - No external CI or package manifest detected — avoid adding heavy build tooling unless adding a clear reason and docs.

- Debugging tips specific to this repo
  - Check browser DevTools console for missing asset 404s — most issues are incorrect relative paths.
  - When changing `_config.yml`, verify URLs and `baseurl` values; preview with local HTTP server.

- What to avoid / constraints
  - Do not modify minified files in-place unless also updating the corresponding source files.
  - Avoid adding package.json, webpack, or similar tooling without syncing with maintainers.

- Examples (edit flow)
  - Update page markup: edit `index.html`, test locally via `python -m http.server`, commit small atomic change, open a PR.

If anything in this file is unclear or you want more detail about a specific workflow (local tooling, tests, or adding a build step), tell me what to expand.
