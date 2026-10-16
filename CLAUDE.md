# Jiakai Chen — personal academic website

Jekyll site built on AcademicPages (a fork of Minimal Mistakes), hosted on GitHub Pages.
Converted from a hand-written single-page HTML site.

## Build and deploy
- GitHub Pages source is set to **GitHub Actions** (Settings → Pages). The workflow is
  `.github/workflows/jekyll.yml` and runs on pushes to `main` or `master`.
- The old "Deploy from a branch" builder can't compile this theme's Sass (`math.div`), so
  don't switch back.
- Local preview: `bundle install` then `bundle exec jekyll serve -l -H localhost`.

## Where content lives
- `_config.yml`: site title, sidebar (`author:` block: name, bio, location, employer),
  `publication_category` (Research page sections, in display order).
- `_data/navigation.yml`: top menu (Research, Teaching, Media, CV → `/files/cv.pdf`).
- `_pages/about.md`: home page. `_pages/media.md`: quotes and op-eds.
  `_pages/publications.html`: Research page (title "Research").
- `_publications/*.md`: one file per paper. `category:` is `journal`, `policy`, `working`
  or `wip`. Within a section, newest `date:` comes first.
  - `excerpt:` = text under the title in the list (co-authors, status).
  - `venue:` = journal, shown as "*Journal*, year". Working papers have no venue.
  - `paperurl:` = "Download Paper" link. `citation:` is kept but NOT shown in the list.
  - `hide_date: true` on working/wip papers and courses: their dates are placeholders
    used only for ordering and must never be displayed.
  - Text below the front matter (e.g. an abstract) makes the title link to the paper's own
    page; with no body text, the title is plain text and `sitemap: false` is set.
- `_teaching/*.md`: one file per course, syllabus link in the body.
- `files/`: PDFs (CV, papers, syllabi). `images/JiakaiChenUH2017small.jpg`: sidebar photo.

## Customizations to the stock theme (keep these when updating the theme)
- `_sass/_custom.scss` (imported last in `assets/css/main.scss` as `"custom"`): sidebar gap,
  heading weights/font, Research-page text sizes (`$paper-title-size`, `$paper-text-size`,
  applied via the `archive__item--paper` class set in `archive-single.html`), wrapping of long sidebar lines (icons exempt from the indent).
- `_sass/layout/_sidebar.scss`: avatar `border-radius: 0` (rectangular photo, not a circle).
- `_includes/archive-single.html`: no "Published in"/"Published:" labels for publications;
  `hide_date` respected for teaching; titles unlinked when a paper has no body text;
  citation line suppressed for publications; publication venue shown after the excerpt.
- `_layouts/single.html`: same "Published" removal on individual paper pages.
- `_layouts/archive.html`: `hide_title: true` in a page's front matter hides its
  big heading (set on the Research and Teaching pages; the title is still used in the browser tab).

## Preferences
- Keep the theme's default look unless asked; make style changes in `_sass/_custom.scss`.
- Google Analytics is off (the old Universal Analytics ID is dead; GA4 would need a new ID).
