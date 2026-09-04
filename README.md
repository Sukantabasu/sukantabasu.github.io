# sukantabasu.github.io

Personal academic website of **Sukanta Basu** (University at Albany, SUNY).
Built with [Jekyll](https://jekyllrb.com/) and the
[al-folio](https://github.com/alshedivat/al-folio) theme; deployed to GitHub Pages
by a GitHub Actions workflow.

## How the site is organized

| Path | What it holds |
| --- | --- |
| `_pages/about.md` | Home page — bio, photo, links, latest news |
| `_pages/research.md` | Research themes and competition results |
| `_pages/publications.md` | Publications page (auto-generated from the bibliography) |
| `_pages/group.md` | Current members and former advisees |
| `_pages/grants.md` | Sponsored-research table |
| `_pages/teaching.md` | Courses taught |
| `_pages/software.md` | JAX-ALFA and other open-source code |
| `_pages/cv.md` + `_data/cv.yml` | CV page (PDF button points to `assets/pdf/cv.pdf`) |
| `_news/*.md` | One file per news item; newest date shows first |
| `_bibliography/papers.bib` | Every publication; edit this to add a paper |
| `_data/coauthors.yml` | Group members whose names get highlighted in the publication list |
| `_data/socials.yml` | ORCID / Scholar / GitHub / LinkedIn / email links |
| `_config.yml` | Site-wide settings |
| `assets/img/prof_pic.jpg` | Profile photo (replace with a real headshot) |
| `assets/pdf/cv.pdf` | The CV PDF |
| `cv-latex/` | LaTeX source for the CV — **not published**, kept here for convenience |

## Common edits

- **Add a publication:** append a BibTeX entry to `_bibliography/papers.bib`. Use
  `abbr = {Wind}` (or `ABL`, `Optics`, `LES`, `ML`, `Mesoscale`, `Dynamics`) for the
  topic badge, `selected = {true}` to feature it on the home page, and
  `award = {true}` / `award_name = {...}` for a highlight.
- **Add a news item:** create `_news/YYYY-MM-DD-slug.md` (copy an existing one).
- **Update the CV:** edit `_data/cv.yml` for the on-page summary, and replace
  `assets/pdf/cv.pdf` with the new PDF.
- **Add / remove a group member:** edit `_pages/group.md`, and add them to
  `_data/coauthors.yml` so their name is highlighted in the publication list.

## Local preview (optional)

The theme now uses a gem-based runtime with many plugins, so local builds need a full
Ruby + Node + ImageMagick toolchain. Most edits (Markdown, YAML, BibTeX) don't need a
local preview — just push and let CI build. If you do want one:

```bash
bundle install
npm ci
JEKYLL_ENV=production bundle exec jekyll serve
```

## Deployment

`.github/workflows/deploy.yml` builds the site on every push to `main` and publishes
the result to the `gh-pages` branch.

One-time GitHub setup:

1. **Settings → Pages →** Source: *Deploy from a branch*, Branch: `gh-pages` / `(root)`.
2. **Settings → Actions → General →** Workflow permissions: *Read and write permissions*.

To attach a custom domain later: add a `CNAME` file at the repo root containing the
domain, point DNS at GitHub Pages, and set the domain under Settings → Pages.

## Credits

Theme: [al-folio](https://github.com/alshedivat/al-folio) (MIT). See `LICENSE`.
