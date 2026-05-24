# abhishekbanerjee.github.io

Personal portfolio site, live at [abhishekbanerjee.github.io](https://abhishekbanerjee.github.io).

## Stack

- **[Jekyll](https://jekyllrb.com/)** — static site generator. Compiles Markdown + Liquid templates into plain HTML that GitHub Pages serves directly. No server, no database, no runtime.
- **[Tailwind CSS](https://tailwindcss.com/)** — utility-first CSS, loaded via CDN. Styling lives on the elements as class names; no separate `.css` files.

## Running locally

```bash
bundle install                              # first time only
bundle exec jekyll serve --livereload       # → http://localhost:4000
```

Changes to Markdown files and `_includes/` rebuild automatically.

## Structure

```
_layouts/
  default.html                # HTML shell used by every page (head, header, footer, scripts)

_includes/
  header.html                 # Sticky nav bar
  footer.html                 # Footer
  publications-content.html   # Publication list (raw HTML, included into index.html)

_config.yml                   # Site-wide config: name, email, social handles
index.html                    # Main page — all sections (About, Experience, Education,
                              #   Publications, Projects, Contact) live here
about.md                      # Bio, written in Markdown, injected into index.html
hero-content.md               # (unused on page; kept for reference)

assets/
  abhishek.jpg                # Profile photo
```

## Editing content

| What | Where |
|---|---|
| Bio | `about.md` |
| Experience / Education / Projects / Publications | `index.html` (each is a `<section>`) |
| Site name, email, social links | `_config.yml` |
| Nav, header tagline | `_includes/header.html` |

## A note on the contact email

The email address in the Contact section is **not** in the HTML source. It's assembled from two string fragments at render time by a small JavaScript snippet in `_layouts/default.html`, so bots scraping raw HTML can't harvest it. The `+website` tag on the address lets you filter inbound mail in Gmail with **To: contains `+website`**.

## Credits

This site was designed and built in collaboration with [Claude](https://claude.ai) (Anthropic).
