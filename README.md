# chentaijie98.github.io

Academic homepage of Taijie Chen, built with Jekyll and served by GitHub Pages at
<https://chentaijie98.github.io>.

## How content is organised

Almost everything you will want to edit lives in `_data/`. The pages are thin templates that
loop over these files, so adding a paper or a news item never requires touching HTML layout.

| File | Contents |
| --- | --- |
| `_data/publications.yml` | Every paper, preprint, and manuscript under review |
| `_data/news.yml` | The homepage news feed, newest first |
| `_data/resume.yml` | Education, experience, projects, patents, awards, service, presentations |
| `_data/research.yml` | The four research themes, which also group the publication list |
| `_data/navigation.yml` | Top navigation bar |

### Adding a publication

Append an entry to `_data/publications.yml`. The only required fields are `title`, `authors`,
`venue`, and `group`; everything else is optional:

```yaml
- title: "Paper title"
  authors: "<strong>Chen, T.</strong>, Co-author, A."   # bold your own name
  venue: "Journal or conference name"
  venue_detail: "volume(issue), pages"
  venue_short: "IEEE TITS"        # shown on the placeholder tile when there is no figure
  year: 2026
  group: decision                  # decision | foundation | mobility | simulation
  kind: journal                    # journal | conference
  status: "Under review"           # omit for published work
  ranks: ["SCI-Q1 Top", "IF 8.5"]
  tags: ["Ride-Hailing"]
  image: /images/research/figure.png
  selected: true                   # also show it on the homepage
  links:
    - { label: "Paper", icon: "fas fa-file-lines", url: "https://doi.org/..." }
    - { label: "Code", icon: "fab fa-github", url: "https://github.com/..." }
```

Figures go in `images/research/`. Keep them under roughly 1000 px wide so pages stay light;
entries without an `image` render a typographic placeholder tile instead, which is fine.

### Updating the CV

Replace `files/CV-Taijie-Chen.pdf` (and `files/CV-English.pdf`, kept for older inbound links),
then mirror the changes in `_data/resume.yml`.

## Structure

```
_data/          content (see table above)
_pages/         one file per page; all use layout: clean
_layouts/       clean.html is the site shell, article.html wraps markdown pages
_includes/      site-nav, site-footer, pub-entry (renders one publication)
assets/css/     site.css is the whole design system
images/         profile photo, icons, and paper figures
```

`assets/css/site.css` holds every colour, font, and component style as CSS custom properties,
including the dark theme. Change `--primary` and `--accent` at the top of the file to re-skin
the site.

## Local development

GitHub Pages builds the site on push, so local setup is optional. If you want a preview:

```bash
bundle install
bundle exec jekyll serve
```

This needs Ruby 3.x; the system Ruby shipped with macOS is too old for the `github-pages` gem.

## Credits

Originally scaffolded from [academicpages](https://github.com/academicpages/academicpages.github.io),
a fork of the [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) Jekyll theme.
The current design is custom.
