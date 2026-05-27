# CLAUDE.md

Guidance for AI assistants working in this repository.

## Repository overview

This is `ideabus.github.io` — a GitHub Pages site served from the `main` branch of the repo root. The site is currently a single static HTML page; there is no build step, framework, or generator (no Jekyll `_config.yml`, no `package.json`, no static-site generator config).

GitHub Pages serves `index.html` directly at https://ideabus.github.io/.

## Layout

```
.
├── index.html      # The entire site — a single static HTML page
├── README.md       # One-liner placeholder
├── LICENSE         # Apache License 2.0
└── .gitignore      # Python-flavored (carried over from a template; no Python code present)
```

That is the whole repository. There are no other directories, no assets, no CSS/JS files, no tests.

## Working in this repo

Because there is no build system:

- Edit `index.html` directly. Preview by opening it in a browser — no server needed for plain HTML.
- If you add assets (CSS, JS, images), reference them with relative paths from `index.html`.
- If a static-site generator is introduced later (Jekyll, Hugo, Eleventy, etc.), update this file with the build/preview commands.

There is nothing to lint, type-check, test, or compile. Do not invent commands — if asked to "run tests" or "build", state that none exist.

## Conventions

- Keep changes minimal and scoped. This repo is small enough that there's no abstraction or structure to preserve.
- The `.gitignore` is the default Python `.gitignore` from GitHub's template. Leave it unless Python code is actually added — don't rewrite it preemptively.
- Don't create planning, design, or status documents (`PLAN.md`, `NOTES.md`, etc.) unless explicitly asked. There is no documentation directory.

## Git workflow

- The default branch is `main`.
- GitHub Pages publishes from `main` automatically — pushing to `main` deploys the site.
- For Claude Code sessions on the web, develop on the branch specified by the session (e.g. `claude/<slug>`) and let the user merge to `main` when they're ready to publish.
- Do not open pull requests unless the user explicitly asks.

## When extending the site

If/when this grows beyond a single page, a reasonable next structure would be:

- `index.html` stays at the root (GitHub Pages entry point)
- `assets/` for CSS, JS, images
- `_config.yml` if Jekyll is adopted (GitHub Pages' default generator)

Don't pre-create that scaffolding before it's needed.
