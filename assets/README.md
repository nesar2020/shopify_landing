# Image assets for the Chi Maskine landing page

Drop product / lifestyle / review photos here, then tell Claude to wire them in.

Claude will:
1. Embed them (data-URIs) in the standalone preview (`preview/chi-maskine.html`).
2. Upload them to Shopify **Files** via the Admin API and reference the CDN URLs
   in the Liquid section (`shopify/sections/ava-chi-landing.liquid`), then
   redeploy to the store.

## Suggested filenames (match photos to page slots)

| Filename | Slot |
|---|---|
| `hero-main.(jpg/png/webp)` | Main hero product photo |
| `hero-1` … `hero-5` | Hero thumbnails (angles / in-use / detail / remote / video still) |
| `benefit-sleep` | "Når kroppen ikke vil falde til ro" |
| `benefit-back` | "Til stiv ryg, hofter og ben" |
| `benefit-legs` | "Lettere ben efter lange dage" |
| `review-1` … `review-6` | UGC review photos (optional) |
| `cross-1` … `cross-4` | Cross-sell product photos (optional) |

Not sure how to name them? Just drop everything in this folder — Claude will
look at each image and place it in the right slot. Any slot without a photo
keeps its current SVG illustration.
