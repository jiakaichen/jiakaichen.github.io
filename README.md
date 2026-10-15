# Jiakai Chen — personal academic website

Built with [Jekyll](https://jekyllrb.com) and [AcademicPages](https://github.com/academicpages/academicpages.github.io), a fork of [Minimal Mistakes](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/).

## Where things live
| What | File(s) |
|---|---|
| Name, sidebar bio, links, site URL | `_config.yml` |
| Header menu | `_data/navigation.yml` |
| Home page text | `_pages/about.md` |
| Publications / working papers / work in progress | `_publications/*.md` (`category:` = `journal`, `policy`, `working`, `wip`) |
| Teaching | `_teaching/*.md` |
| Media quotes and op-eds | `_pages/media.md` |
| PDFs (CV, papers, syllabi) | `files/` |
| Profile photo | `images/JiakaiChenUH2017small.jpg` |

Items in a section are listed newest `date:` first. Working papers, work in progress and courses carry `hide_date: true`, so their dates only control order and are never shown.

### Adding a paper
Copy any file in `_publications/`, change `title`, `category`, `permalink`, `date`, and optionally `coauthors`, `venue`, `venue_detail`, `paperurl`. Text below the front matter appears on the paper's own page (e.g. an abstract).

## Run locally
```
bundle install
bundle exec jekyll serve -l -H localhost
```
