# Latini Group website

Source for <https://nautasimola.github.io>, a small custom Jekyll site.
Pushing to `master` builds the site with GitHub Actions and publishes it to the
`gh-pages` branch.

## Editing content

| What | Where |
| --- | --- |
| Site name, address, socials, menu | `_config.yml` |
| Home page text and research topics | `_pages/home.md` |
| People | `_people/*.md` (`importance`: 1 group leader, 2 postdoc, 3 PhD. `category: toshow` to display. `redirect` is the profile link) |
| Research topics | `_projects/*.md`: `category: work` to display, `importance` sets order |
| News | `_news/*.md`: `title`, `date`, optional `image`, then a short text |
| Publications | `_bibliography/papers.bib`: add `selected={true}` to feature a paper on the home page, `abbr={...}` for the venue tag, `html={...}` for the link. Add new years to `years:` in `_pages/publications.md` |
| Teaching, Join us, CV | `_pages/teaching.md`, `_pages/join.md`, `_data/cv.yml` |
| Colours and styles | `assets/css/main.scss` (palette at the top) |

Images go in `assets/img/`.

## Running locally

Needs Ruby 3 (e.g. `brew install ruby`).

```bash
export PATH="/opt/homebrew/opt/ruby/bin:$PATH" LANG=en_US.UTF-8
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>.
