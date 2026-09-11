# Local Politics and Policy Lab — website

Static site for **localpoliticslab.org**. No build step: just HTML, CSS, and assets.
Open `index.html` in a browser to preview locally.

```
site/
├── index.html      # the entire single-page site
├── styles.css      # all styling
├── assets/
│   ├── natalia-bueno.jpg
│   └── favicon.svg
├── papers/         # PDFs linked from the Research section
├── CNAME           # custom domain for GitHub Pages (localpoliticslab.org)
└── README.md
```

## Editing

Everything is plain HTML — edit `index.html` directly.

- **Add a paper:** copy the PDF into `papers/`, then add an `<li>` inside the relevant
  `<ul class="paper-list">` (Research) and/or `<ul class="pub-list">` (Publications), following an
  existing item as a template.
- **Add a person:** duplicate the `.member` block in the People section. Use a real photo
  (`<img class="photo" ...>`) or keep the initials monogram (`<div class="avatar-mono">CB</div>`).
- **Undergraduate research fellows:** the People section has an "Undergraduate Research Fellows"
  block: a `.fellow-grid` of `<figure class="fellow">` cards (square photo + name). Add a fellow by
  duplicating a card; put a ~600px square JPG in `assets/` (originals live in `photos/`).
- **Colors / fonts:** change the CSS variables at the top of `styles.css` (`--accent`, `--paper`, etc.).
- **Contact email:** the footer "Get in touch" link is `clara.bicalho@emory.edu`.
- Fonts load from Google Fonts via a `<link>`; the site falls back to system fonts if offline.
- No analytics, cookies, or trackers are included.
- Paper links point to local PDFs in `papers/` where available; papers without a local PDF show the
  citation without a download link — add the PDF and a link when ready.
