# nudibranchwebsite

Source html for **[nudibranch.poplel.xyz](https://nudibranch.poplel.xyz)**

Styled with [98.css](https://jdan.github.io/98.css/) for that swagalicious retro look

## Structure

Plain HTML and CSS — no framework, no build step. Every page is a directory with an
`index.html`, so URLs are clean (`/privacy-policy`, not `/privacy.html`).

```
index.html            → /
guide/index.html      → /guide
faq/index.html        → /faq
docs/index.html       → /docs
contact/index.html    → /contact
privacy-policy/       → /privacy-policy
404.html              → not-found page
style.css             → shared styles (root-absolute: /style.css)
```

Assets and links are referenced root-absolutely (`/style.css`, `/logo.png`, `/guide`),
so the site must be served from the domain root.

## The sidebar

The nav is duplicated verbatim in every page, between the
`<!-- ==== SIDEBAR ==== -->` comments. Change one, change them all. The only per-page
differences are:

- `class="active"` on the current page's link
- the docs tree uses `<details open>` on docs pages, closed elsewhere

## Adding a docs page

Docs are drafted in `Documents/NudibranchDocs` and not published yet. To add one:

1. Create `docs/<slug>/index.html` from an existing page (slug matches the markdown
   filename, e.g. `docs/api-reference`).
2. In the sidebar tree on *every* page, replace that entry's
   `<span class="pending">Title</span>` with `<a href="/docs/<slug>">Title</a>`.
3. Drop the "Coming soon" note from the matching card on `docs/index.html`.

Local preview:

```
python3 -m http.server 8000
```
