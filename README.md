# AVA — Shopify Landing Page Demos

Conversion-focused product landing pages built with **Claude Code** as an
interview demo for a Shopify landing-page role at AVA Beauty.

## AVA Chi Maskine page (brand-matched)

`preview/chi-maskine.html` is a standalone landing page for the **Premium Chi
Maskine**, rebuilt to match AVA Beauty's real design system (white + cream bands,
black CTAs, red price anchoring, teal accent, serif headings, Danish copy, the
FAQ-under-hero layout, comparison table, and local trust: MobilePay/Dankort,
100-dages retur, E-mærket).

Deployable theme files for this page:

| Path | What it is |
|---|---|
| `shopify/layout/landing.liquid` | Minimal layout — **no theme header/footer** (clean ad landing page) |
| `shopify/sections/ava-chi-landing.liquid` | The whole page as a self-contained section (inline CSS/JS + SVG art) |
| `shopify/templates/page.chi-maskine.liquid` | Page template that mounts the section using the landing layout |

### Deploy the Chi Maskine page to Shopify

```bash
npm install -g @shopify/cli @shopify/theme
shopify theme pull --store frp4rj-hd.myshopify.com            # or your store
cp shopify/layout/landing.liquid                <theme>/layout/
cp shopify/sections/ava-chi-landing.liquid      <theme>/sections/
cp shopify/templates/page.chi-maskine.liquid    <theme>/templates/
shopify theme dev --store frp4rj-hd.myshopify.com            # live preview
shopify theme push                                           # deploy
```

Then in **Shopify admin → Online Store → Pages**, create a page (e.g. handle
`chi-maskine`) and set its **Theme template** to `chi-maskine`. It renders at
`/pages/chi-maskine` with no store header/footer — ideal for paid traffic.

---

## SØVN Night page (original demo)

A conversion-focused product landing page for a fictional Nordic wellness brand
(**SØVN Night**, a magnesium sleep drink).

It ships in two forms so it can be shown live *and* deployed into a real store:

| Path | What it is | How to view |
|---|---|---|
| `preview/index.html` | Standalone, self-contained landing page | Open in any browser — no build step |
| `shopify/sections/sovn-landing.liquid` | A real Shopify **section** (Online Store 2.0) with Theme-Editor settings | Deploy to a store, see below |
| `shopify/templates/page.sovn-night.json` | Page template that mounts the section | Assign to a page in Shopify admin |

## Design approach

- **"Moonlit Nordic" identity** — cool "paper" base punctuated by full-bleed
  *midnight* sections, one luminous aurora-teal accent used only against the
  dark, editorial serif (Spectral) over a clean grotesque (Hanken Grotesk).
  Deliberately *not* the generic cream/terracotta wellness template.
- **Conversion architecture:** hook → problem agitation → mechanism (dosed
  actives) → benefits → ingredient transparency → ritual → social proof →
  comparison vs. pills/melatonin → pack offer with honest scarcity → 60-night
  guarantee → FAQ, plus a mobile sticky add-to-cart.
- Fully responsive, light/dark theme-aware, respects `prefers-reduced-motion`,
  keyboard-focusable. No external assets except Google Fonts (product visual is
  inline SVG).

## Preview locally

```bash
# just open the file
open preview/index.html          # macOS
xdg-open preview/index.html      # Linux
# or serve it
python3 -m http.server -d preview 8080   # then visit http://localhost:8080
```

## Deploy to Shopify

The Liquid section is a drop-in for any Online Store 2.0 theme.

```bash
# 1. Install the free Shopify CLI
npm install -g @shopify/cli @shopify/theme

# 2. From your theme directory, pull your live theme (or use a dev theme)
shopify theme pull --store your-store.myshopify.com

# 3. Copy the demo files into the theme
cp shopify/sections/sovn-landing.liquid        <theme>/sections/
cp shopify/templates/page.sovn-night.json      <theme>/templates/

# 4. Preview against your store with hot reload
shopify theme dev --store your-store.myshopify.com

# 5. Push when happy
shopify theme push
```

Then in **Shopify admin → Online Store → Pages**, create a page and set its
**Theme template** to `sovn-night`. To make the buy box add to cart for real,
open the page in the **Theme Editor** and set the section's **Product** setting
to a real product — its variants automatically become the pricing packs.

## Notes

- All copy, reviews, ratings, and press mentions are illustrative demo content.
- Health claims are illustrative and not evaluated by any health authority.
