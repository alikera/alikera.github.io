# Ali Keramati's Website

My personal website, built with the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme (v1.2) and hosted on GitHub Pages: [alikera.github.io](https://alikera.github.io).

## Where things live

| What | File |
|---|---|
| Bio, photo and address on the home page | `_pages/about.md`, `assets/img/prof_pic.jpg` |
| News on the home page (newest five) and the full list at `/news/` | one file per item in `_news/` |
| Publications (add `selected = {true}` to feature a paper on the home page) | `_bibliography/papers.bib`, thumbnails in `assets/img/publication_preview/` |
| Project cards and pages | `_projects/*.md`, images in `assets/img/projects/` |
| CV page | `_data/cv.yml` (RenderCV format); the PDF icon downloads `files/cv-alikeramati.pdf` |
| Teaching, education and transcripts | `_pages/teaching.md`, `_pages/education.md`, PDFs in `files/` |
| Email, Google Scholar, ORCID, GitHub, LinkedIn icons | `_data/socials.yml` |
| Co-author homepages and venue links in the publication list | `_data/coauthors.yml`, `_data/venues.yml` |
| Repositories page | `_data/repositories.yml` |
| Site title, description and theme options | `_config.yml` |
| Accent colour (UC Irvine blue) | `_sass/_custom.scss`, loaded by `assets/css/main.scss` |

## Publishing

Pushing to `master` runs `.github/workflows/deploy.yml`, which builds the site and pushes it to the `gh-pages` branch. GitHub Pages serves that branch (*Settings → Pages → Deploy from a branch → `gh-pages`*). Don't edit `gh-pages` by hand.

## Previewing locally

With Docker: `docker compose up`, then open http://localhost:8080.
With Ruby 3.3: `bundle install && bundle exec jekyll serve`, then open http://localhost:4000.

The previous AcademicPages version of this site is kept on the `academicpages-backup` branch.
