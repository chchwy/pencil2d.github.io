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
| `content-es/`, `content-zh/` | translations of pages in `content/` |
| `i18n/` | interface text per language |
| `layouts/` | page templates; `layouts/_shortcodes/` holds the `{{< toc >}}`-style helpers |
| `data/` | the manual and course tables of contents (`manual.yml`, `course.yml`) |
| `static/` | images and other files copied to the site as-is |
| `assets/` | stylesheets and the inline SVG icons |

A new post is `content/posts/<slug>.md`, published at `/<year>/<month>/<slug>.html`.

## Languages

The site is in English (at the root), Spanish (under `/es/`) and Chinese (under `/zh/`).
Configured in `hugo.toml`; the globe menu in the header switches between them.

- **Interface text** (menus, buttons, labels) is in `i18n/<lang>.toml`. A new string goes
  in every one of them, and templates use it as `{{ T "key" }}`.
- **Page content** is translated by putting a file at the same path under `content-<lang>/`.
  For example, `content-zh/doc/faq.md` replaces `content/doc/faq.md` on `/zh/doc/faq.html`.
  Pages without a translation are shown in English with the translated interface and a note
  saying so. Their canonical link points to the English page, and they are left out of that
  language's sitemap.
- Links inside content stay as they are (`/doc/faq.html`); on other languages' pages they are
  pointed at `/es/...` or `/zh/...` automatically.

To add a language: a `[languages.<lang>]` block and a `content-<lang>` mount in `hugo.toml`,
and an `i18n/<lang>.toml` with every key from `i18n/en.toml`.

Theme based on <https://github.com/lorepirri/cayman-blog>.
