# Israel Trek 2027 · MIT Sloan MBA

Website for the MIT Sloan MBA Israel Trek, March 21–28, 2027: Tel Aviv-Yafo, Jerusalem, and the Dead Sea.

**Live site:** https://adiy10.github.io/israel-trek-2027/

A single static page (HTML and CSS, no JavaScript, no build step), hosted for free on GitHub Pages.

## Publishing with GitHub Pages

One-time setup, about a minute:

1. In this repository, open **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Pick branch **main** and folder **/ (root)**, then click **Save**.
4. After a minute or two, the site is live at https://adiy10.github.io/israel-trek-2027/.

From then on, every change pushed to `main` goes live automatically.

## Editing the site

The easiest way is right on GitHub: open `index.html`, click the pencil icon, make the change, and click **Commit changes**.

Common updates in `index.html`:

- **Deposit link is live:** in "Next steps", step 3, replace `<span class="badge">Coming soon</span>` with a button such as
  `<a class="btn btn-primary" href="YOUR-DEPOSIT-LINK" target="_blank" rel="noopener">Pay the deposit</a>`.
  Then update the "coming weeks" wording in the hero note, the Cost section, and step 3.
- **Prices:** the `tiers` list in "Cost", the "From $999" fact in the hero, and the `og:description` meta tag.
- **Dates or regions:** the hero facts, plus the `description` and `og:description` meta tags.

To preview changes on your computer before pushing:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Files

```
index.html            All page content
css/styles.css        All styles (design tokens at the top)
assets/img/           Optimized WebP photos and the iTrek logo
assets/og-image.jpg   Link-preview image for WhatsApp, Slack, and iMessage
favicon-32.png        Browser tab icon
apple-touch-icon.png  Home-screen icon
.nojekyll             Tells GitHub Pages to serve the files as-is
```

## Design

One scrolling page: hero with key facts → what we'll do → itinerary → cost → safety → next steps → questions.

| Token | Value | Use |
|---|---|---|
| `--brand` | `#00B4F4` | iTrek cyan for buttons, dots, and tags (too light for text on white) |
| `--brand-ink` | `#00699E` | Cyan for text and icons on light backgrounds |
| `--ink` | `#0B1B2B` | Headings, button text, safety panel |
| `--text` / `--muted` | `#334155` / `#5B6472` | Body and secondary text |
| `--bg-alt` / `--brand-tint` | `#F4F8FB` / `#E5F7FE` | Alternating sections, highlighted price tier |

- **Type:** Poppins for headings, Inter for body text (Google Fonts).
- **Accessibility:** WCAG AA color contrast, skip link, semantic landmarks, visible focus styles, reduced-motion support, and alt text.
- **Performance:** responsive images with fixed dimensions and lazy loading, about 900 KB of assets in total.

## Notes

- **Search engines:** the page includes `<meta name="robots" content="noindex">` because it links to the trek's WhatsApp group.
  Delete that line if you want the site to show up in search results.
- **Link previews:** the `og:url` and `og:image` tags use the full GitHub Pages address. Update them if the address changes.
- **Custom domain (optional):** Settings → Pages → Custom domain.
