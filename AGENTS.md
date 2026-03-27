# Repository Guidelines

## Project Structure & Module Organization
This repository is a Hugo-based personal website. Source content lives in `content/`, with section index pages in `content/*/_index.md` and individual entries such as `content/works/microlux.md`. Site configuration is in `hugo.toml` and Go module metadata is in `go.mod`. Theme overrides and custom templates live in `layouts/`, especially `layouts/_default/` and `layouts/partials/`. Static assets such as images belong in `static/` and are referenced with root-relative paths like `/images/banner.jpg`. Treat `public/` as generated build output; do not edit it by hand.

## Build, Test, and Development Commands
Use Hugo Extended locally.

- `hugo server -D`: start a local preview at `http://localhost:1313` and include draft content.
- `hugo --gc --minify`: build the production site into `public/`.
- `hugo`: run a quick local build without extra cleanup or minification.

GitHub Actions deploys the site from `.github/workflows/hugo.yaml` on pushes to `main`.

## Coding Style & Naming Conventions
Prefer Markdown content with concise front matter keys such as `title`, `date`, `draft`, `summary`, and `cascade`. Use lowercase, hyphen-free section names that match the current structure (`about`, `blog`, `works`). New content files should use descriptive lowercase names, for example `content/works/new-project.md`.

For templates, preserve Hugo’s Go template style and the existing two-space HTML indentation seen in `layouts/_default/baseof.html`. Keep partials focused and place reusable snippets in `layouts/partials/`.

## Testing Guidelines
There is no automated test suite in this repository. Validate changes by running `hugo server -D` for visual review and `hugo --gc --minify` to catch template or content build errors before opening a PR. Check changed pages, image paths, and MathJax-rendered equations when relevant.

## Commit & Pull Request Guidelines
Recent history uses short, imperative commit messages such as `update content`, `add mathjax support`, and `add support for banner caption`. Follow that pattern: one clear action per commit, written in lowercase when practical.

Pull requests should include a short summary, affected paths, linked issues if any, and screenshots for layout or content changes that alter rendered pages. Note any Hugo version assumptions or deployment impact when touching `hugo.toml` or `.github/workflows/hugo.yaml`.
