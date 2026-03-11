# Genezio Docs

HTML-only documentation site for Genezio, built from Markdown files.

## Quick Start

```bash
npm install
npm run build
```

Build output:

- `dist/index.html`
- `dist/docs/**`
- `dist/assets/site.css`

## How It Works

- `build.js` is the static site generator.
- Docs content is authored in `content/**/*.md`.
- The generator converts Markdown to HTML and applies a shared layout (top nav + left menu + content shell).
- Sidebar/menu entries are content-driven:
  - only pages with non-empty Markdown are included
  - empty pages are automatically excluded from the menu and output

## Content Structure

- `content/index.md` -> site home page
- `content/docs/index.md` -> docs index
- `content/docs/getting-started.md` -> standalone docs page
- `content/docs/<section>/<page>.md` -> section pages

Examples:

- `content/docs/introduction/what-is-genezio.md`
- `content/docs/core-concepts/brands.md`
- `content/docs/genezio-agents/prompter-agent.md`

## Scripts

- `npm run build` - generate the static site into `dist/`
- `npm run clean` - remove `dist/`

## Tech Notes

- No frontend framework.
- No runtime JS required for docs rendering.
- Styling lives in `src/site.css`.
- Output is designed to be readable for both humans and LLM pipelines (clean headings, semantic HTML, explicit sections).
