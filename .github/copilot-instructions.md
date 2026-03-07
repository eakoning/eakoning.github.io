# Copilot Instructions

This is a Jekyll-based GitHub Pages site.

## Build & Serve

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve --livereload

# Build for production
bundle exec jekyll build
```

The site is served at `http://localhost:4000` by default. Output is generated into `_site/` (gitignored).

## Architecture

- `_config.yml` — site-wide settings (title, baseurl, theme, plugins, collections)
- `_layouts/` — base HTML templates; pages/posts declare `layout:` in front matter
- `_includes/` — reusable HTML partials, injected via `{% include filename.html %}`
- `_posts/` — blog posts named `YYYY-MM-DD-title.md`, always require `layout`, `title`, and `date` front matter
- `_data/` — YAML/JSON/CSV data files accessible via `site.data.<filename>`
- `assets/` — static files (CSS, JS, images)
- `_sass/` — Sass partials imported by the main stylesheet

Pages at the root (e.g., `about.md`, `index.html`) are rendered using their declared layout.

## Key Conventions

- All content files use YAML front matter delimited by `---`
- Liquid templating (`{{ }}`, `{% %}`) is used inside layouts, includes, and content files
- `baseurl` in `_config.yml` must be set to the repository name when hosting on GitHub Pages as a project site (e.g., `/repo-name`); leave empty for a user/org site (`username.github.io`)
- GitHub Pages only supports a [subset of Jekyll plugins](https://pages.github.com/versions/); use the `github-pages` gem to match the hosted environment exactly
- The `_site/` directory is build output and should not be committed

## GitHub Pages Deployment

The site deploys automatically on push to the configured branch (usually `main` or `gh-pages`). No manual deploy step is needed.
