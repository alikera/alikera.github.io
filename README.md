# Ali Keramati's Website

My personal website, built with the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme (v1.2) and hosted on GitHub Pages: [alikera.github.io](https://alikera.github.io).

## Where things live

| What | File |
|---|---|
| Bio, photo and address on the home page | `_pages/about.md`, `assets/img/prof_pic.jpg` |
| Publications (selected ones also show on the home page) | `_bibliography/papers.bib` — add `selected = {true}` to feature a paper |
| Education, CV and transcript pages | `_pages/education.md`, `_pages/cv.md`, `_pages/transcript.md` |
| PDFs (CV, transcripts, degrees) | `files/` |
| Email, Google Scholar, GitHub, LinkedIn icons | `_data/socials.yml` |
| Site title, description, theme options | `_config.yml` |
| News items on the home page | add files to `_news/` and set `announcements.enabled: true` in `_pages/about.md` |

## Publishing

Pushing to `master` runs `.github/workflows/deploy.yml`, which builds the site and pushes it to the `gh-pages` branch. GitHub Pages serves that branch (*Settings → Pages → Deploy from a branch → `gh-pages`*). Don't edit `gh-pages` by hand.

## Previewing locally

With Docker: `docker compose up`, then open http://localhost:8080.
With Ruby 3.3: `bundle install && bundle exec jekyll serve`, then open http://localhost:4000.

The previous AcademicPages version of this site is kept on the `academicpages-backup` branch.
