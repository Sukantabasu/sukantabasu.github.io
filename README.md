# sukantabasu.github.io

Personal academic website of **Sukanta Basu** (University at Albany, SUNY).
Built with [Jekyll](https://jekyllrb.com/) and the
[al-folio](https://github.com/alshedivat/al-folio) theme; deployed to GitHub Pages
by a GitHub Actions workflow.

## How the site is organized

### Navigation (each item is a page or a dropdown of pages)

`publications` (all + 6 topic pages) · `research` · `group` (members + photos) · `grants` ·
`teaching` · `software & data` (JAX-ALFA + Zenodo) · `hackathons` (overview + 9) ·
`conferences` · `outreach` · `links` · `Olympics 2020` (overview + 17 daily forecasts) ·
`cv` · `news`

Dropdown menus are defined by the `*-menu.md` pages (`dropdown: true` + a `children:` list).
The child pages themselves have `nav: false` and their own `permalink`.

### Key files

| Path | What it holds |
| --- | --- |
| `_pages/about.md` | Home page — bio, photo, links, latest news |
| `_pages/*.md` | One Markdown file per page; front-matter `nav` / `nav_order` controls the menu |
| `_news/*.md` | One file per news item; newest date shows first |
| `_bibliography/papers.bib` | Every publication; edit this to add a paper |
| `_data/cv.yml` | On-page CV summary (the PDF button points to `assets/pdf/cv.pdf`) |
| `_data/coauthors.yml` | Group members whose names get highlighted in the publication list |
| `_data/socials.yml` | ORCID / Scholar / GitHub / LinkedIn / Kaggle / email links |
| `_config.yml` | Site-wide settings |
| `CNAME` | Custom domain (`sukantabasu.com`) |
| `assets/img/prof_pic.jpg` | Profile photo — **replace with a real headshot** |
| `assets/img/olympics/` | Drop `2021-07-15.png` … `2021-08-01.png` here for the Olympics pages |
| `assets/img/group/` | Photos referenced from `/pictures/` |
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

1. **Settings → Actions → General →** Workflow permissions: *Read and write permissions*.
2. Push to `main`; wait for the **Deploy site** action to finish (Actions tab).
3. **Settings → Pages →** Source: *Deploy from a branch*, Branch: `gh-pages` / `(root)`.

### Custom domain (`sukantabasu.com`, DNS on Cloudflare)

The `CNAME` file is already in the repo. In the Cloudflare dashboard for `sukantabasu.com`,
add these DNS records (all **DNS only / grey cloud**, not proxied — GitHub Pages serves its
own TLS):

| Type | Name | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `sukantabasu.github.io` |

Then in **Settings → Pages → Custom domain**, confirm `sukantabasu.com` and enable
*Enforce HTTPS* once the certificate is issued.

## Credits

Theme: [al-folio](https://github.com/alshedivat/al-folio) (MIT). See `LICENSE`.
