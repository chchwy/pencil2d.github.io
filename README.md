# Pencil2D Official Website

Go to the website: <https://www.pencil2d.org>

Built with [Hugo](https://gohugo.io/) (extended edition) and deployed to GitHub Pages by
`.github/workflows/hugo.yml` on every push to `master`.

## Preview locally

Install Hugo extended (`winget install Hugo.Hugo.Extended`, `brew install hugo`, or a
release from GitHub), then run from the repository root:

    hugo server

and open <http://localhost:1313>. The page reloads as you edit.

## Where things are

| path | what |
|---|---|
| `content/` | every page, in Markdown; `content/posts/` holds the news posts |
| `layouts/` | page templates; `layouts/_shortcodes/` holds the `{{< toc >}}`-style helpers |
| `data/` | the manual and course tables of contents (`manual.yml`, `course.yml`) |
| `static/` | images and other files copied to the site as-is |
| `assets/` | stylesheets and the inline SVG icons |

A new post is `content/posts/<slug>.md`, published at `/<year>/<month>/<slug>.html`.

Theme based on <https://github.com/lorepirri/cayman-blog>.
