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
- **Undergraduate associates:** the People section has an "Undergraduate Associates" block with a
  placeholder note. Replace it with a `.member-grid` of `.member` cards once you have names.
- **Colors / fonts:** change the CSS variables at the top of `styles.css` (`--accent`, `--paper`, etc.).
- **Contact email:** the footer currently shows `contact@localpoliticslab.org` as a placeholder —
  replace it with a real address, or set up email forwarding for the domain in GoDaddy.

## Deploy — Option A: GitHub Pages (free, recommended)

1. Create a GitHub repo and push the **contents of this `site/` folder** to the repo root
   (so `index.html` is at the top level). The included `CNAME` file already contains
   `localpoliticslab.org`.
2. Repo → **Settings → Pages** → set **Source: Deploy from a branch**, branch `main`, folder `/root`.
3. In **GoDaddy → Domain → DNS**, point the domain at GitHub Pages:
   - Four `A` records for `@` →
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record for `www` → `YOUR-USERNAME.github.io`
   - Remove any conflicting parked `A`/`CNAME` records GoDaddy added by default.
4. Back in GitHub Pages settings, confirm the custom domain is `localpoliticslab.org` and
   enable **Enforce HTTPS** once the certificate is issued (can take up to ~24h for DNS to propagate).

## Deploy — Option B: GoDaddy hosting

If you have a GoDaddy hosting/cPanel plan:

1. Open **cPanel → File Manager** and go to `public_html/`.
2. Upload the contents of this `site/` folder (not the folder itself) so `index.html` sits in
   `public_html/`. You can drag-and-drop or upload a zip and extract.
3. Visit `https://localpoliticslab.org`. (The `CNAME` file is only used by GitHub Pages; it is
   harmless here and can be deleted.)

## Notes

- Fonts load from Google Fonts via a `<link>`; the site falls back to system fonts if offline.
- No analytics, cookies, or trackers are included.
- Paper links point to local PDFs in `papers/` where available; papers without a local PDF show the
  citation without a download link — add the PDF and a link when ready.
