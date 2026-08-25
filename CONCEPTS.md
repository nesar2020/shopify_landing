# Shopify Landing Concepts — Design Specs

Four portfolio concepts, each a complete conversion-focused landing page for a
different kind of Shopify merchant. All live in `preview/concepts/` as
standalone HTML (open in any browser, no build step); `preview/concepts/index.html`
is the gallery hub.

Each spec below is a build checklist for rebuilding the concept by hand in
Webflow (or as a Shopify section, following the pattern already in `shopify/`).

---

## Concept 01 — KARST Roasters (`01-karst-coffee.html`)

Single-lot specialty coffee, subscription commerce. Page job: **start a subscription**.
CTA everywhere: **"Start my roast plan."**

```
TOKENS
  Colors: fir #12291F · fir-deep #0C1D16 · paper #FAF7F0 · mint #D9EFDF ·
          amber #C4762A · ink #161512
  Type:   Display — Bricolage Grotesque 800/600 · Body — Instrument Sans 400/500/600 ·
          Mono — IBM Plex Mono 400/500 (tickets, data, eyebrows)
  Scale:  16px base · display clamp 2.6–4.3rem, ls -0.025em · breakpoints 1160/880/720
  Spacing: 4px unit · sections 88px · radius 6px everywhere

SECTIONS
  1. Nav — sticky, paper bg, hairline bottom border, primary CTA right
  2. Hero — 2-col grid (1.15fr/.85fr): headline + lead + 2 CTAs + proof line |
     lot ticket card (dark fir, perforation dots via absolute circles,
     dashed dividers, dl grid of origin data, tasting-note pills)
  3. Ribbon — dark marquee strip, mono uppercase claims (CSS keyframe slide,
     duplicated content; Webflow: marquee interaction or Lottie)
  4. Roast curve — 2-col: white card with SVG line chart (bean temp + RoR,
     first-crack marker) | 3 numbered "why" items
  5. How it works — dark band, 3 steps in a 1px-gap grid (gasket-style cells)
  6. Plans — 3 pricing cards, middle "hot" card elevated w/ amber flag pill,
     check bullets (CSS borders, not icons)
  7. Reviews — 3 cards, amber stars, named + tenure footers
  8. FAQ — details/summary accordion, amber "+" rotates 45°
  9. Closing — dark fir band, amber CTA, next-roast-day urgency
  10. Footer — deepest fir, small print

SIGNATURE ELEMENT
  The lot ticket: a perforated coffee-lot card (producer, altitude, varietal,
  process, cupping score, tasting pills) + the published roast curve. Pulled
  from real specialty-coffee vernacular. Webflow: ticket = div block w/
  absolutely-positioned notch circles; curve = inline SVG embed.

ASSETS NEEDED
  Google Fonts above · roast-curve SVG (in file, copy-paste) · no images
```

---

## Concept 02 — ARO Tempo 2 (`02-aro-tempo.html`)

Performance running shoe, single-product drop. Page job: **buy the shoe**.
CTA everywhere: **"Get the Tempo 2 — $140."**

```
TOKENS
  Colors: track #F2F0EB · chalk #FFFFFF · carbon #111013 · signal #FF3B1F
  Type:   Display — Anton (all-caps, ls +0.01em, line-height .88–.95) ·
          Body — Barlow 400–700 · Mono — JetBrains Mono (specs, splits)
  Scale:  16px base · hero display clamp 4–11.5rem · breakpoints 1180/880/720
  Spacing: 4px unit · sections 90px · radius 2px (track paint, not app UI) ·
          borders 2px solid carbon (hard, graphic)

SECTIONS
  1. Nav — sticky, 2px black bottom border, signal CTA
  2. Hero — giant two-row display headline (row 2 outlined text:
     -webkit-text-stroke; Webflow: duplicate heading w/ stroke via custom CSS
     embed) · grid: copy + CTAs | black trackside "spec board" (weight/stack/
     drop/plate/rated as big Anton numerals)
  3. Band — black marquee of spec claims, signal dividers
  4. Build — 2-col: midsole cross-section diagram (stacked bars: knit, plate,
     foam hatch pattern, rubber) | A/B/C annotated notes
  5. Splits (dark) — the signature: 10K split table, same runner two shoes,
     tabular-nums mono, signal deltas widening late; honesty note below
  6. Athletes — 3 quote cells in 2px black grid, giant PB numerals in signal
  7. Buy — 2-col: price + strike + launch flag, size button grid
     (aria-pressed states, one sold-out size), CTA, bullets |
     colorway card w/ swatch buttons + 30-day run test guarantee box
  8. Closing — full signal-orange band w/ faint diagonal stripes overlay,
     black CTA
  9. Footer + mobile sticky add-to-cart bar (<720px)

SIGNATURE ELEMENT
  The wear-test split table — product proof expressed in the runner's own
  data language (min/km, tabular figures, negative deltas). Webflow: styled
  table or grid w/ mono font; stripes = repeating-linear-gradient embed.

ASSETS NEEDED
  Google Fonts above · no images (diagram is pure CSS bars) ·
  custom CSS embed for text-stroke + stripe overlay
```

---

## Concept 03 — OCTAVE Slab 65 (`03-octave-slab65.html`)

Enthusiast mechanical keyboard, batch pre-order. Page job: **reserve a unit**.
CTA everywhere: **"Reserve Slab 65 — $189."**

```
TOKENS
  Colors: ground #101114 · panel #16181D · panel-2 #1C1F26 · alu #C9CDD4 ·
          text #E8E6E1 · amber #E8A33D
  Type:   Display — Sora 600/700 (ls -0.03em) · Body — IBM Plex Sans ·
          Mono — IBM Plex Mono (specs, labels)
  Scale:  16px base · h1 clamp 2.5–4.4rem · breakpoints 1120/880/720
  Spacing: 4px unit · sections 96px · radius 8px · hairlines rgba(alu,.14)
  Dark-only page — earned by the product world (desk-setup culture), not default.

SECTIONS
  1. Nav — sticky, blurred ground, amber CTA
  2. Hero — centered: live batch pill (pulsing amber dot) → headline →
     lead → CTAs → proof → THE KEYBOARD: full 65% layout built from CSS
     keycaps (3D press: translateY + box-shadow collapse), amber accent
     cluster, perspective tilt. JS: real keydown presses the matching key.
  3. Spec sheet — 8 cells in 1px-gap grid: mount/case/plate/angle/switches/
     caps/connection/firmware — numbers first
  4. Force curve — panel card w/ SVG measured force curve (62g tactile peak,
     actuation marker, ±2.1g consistency claim) | 3 tagged notes
  5. Build — 3 cards: gasket sandwich, case fill, stabilizers
  6. Reviews — 3 cards sourced from the community's own places
     (subreddit, YouTube review, verified owner)
  7. Buy band — 2-col: price, stock progress bar (135/500), finish selector
     buttons, CTA | reservation-terms checklist
  8. FAQ — pricing honesty, hot-swap, linear option, why-65%
  9. Closing + footer

SIGNATURE ELEMENT
  The interactive CSS keyboard — the product IS the hero, and it presses
  back when the visitor types. Webflow: grid of styled div "keys" + small
  custom JS embed for keydown; degrade gracefully (hover/click states) if
  JS trimmed. Force curve = inline SVG embed.

ASSETS NEEDED
  Google Fonts above · force-curve SVG (in file) · ~20-line JS embed
```

---

## Concept 04 — LERVÆRK Batch 09 (`04-lervaerk-batch09.html`)

Small-batch ceramics studio, limited numbered edition. Page job: **reserve a piece**.
CTA everywhere: **"Reserve from Batch 09."**

```
TOKENS
  Colors: gallery #FCFBF9 · ink #211E1B · celadon #5F7F76 / deep #48645D ·
          clay #C0674B (glaze chips + scarcity only) · sand #D9C9A8
  Type:   Display — Libre Caslon Display 400 (serif, museum-catalogue) ·
          Body — Karla 400/500/600 · labels: Karla 600 caps, ls +0.22em
  Scale:  16.5px base · h1 clamp 2.6–4rem · breakpoints 1080/880/720
  Spacing: sections 100px (most generous of the four) · radius 0 —
          square corners, museum labels · hairline borders only

SECTIONS
  1. Nav — sticky gallery white, wordmark in Caslon, black rectangular CTA
  2. Hero — 2-col: label → headline (italic accent) → lead → CTAs →
     scarcity note | shelf of 3 CSS vessels (border-radius silhouettes w/
     glaze gradients) standing on a single 1px "plinth" line, museum captions
  3. Strip — 4 facts between hairlines (clay origin, cone, signature, record)
  4. Catalogue — 3 catalogue cards: framed vessel figure + label block
     (№ x/24, name, dimensions, price / N-remain) — a catalogue raisonné,
     not a product grid; 48-hour-hold reservation note
  5. Process — 2-col: three glaze chips (radial-gradient circles: Hav/Sand/
     Ask) | firing timeline on a left rule (thrown → bisque 950° →
     reduction 1280° highlighted → graded & numbered)
  6. Quote band — full celadon-deep bleed, single collector quote in Caslon
  7. Practical notes — accordion (food-safe, retired glaze, fragile shipping,
     open studio)
  8. Closing — "when this firing sells out, it's history" + CTA
  9. Footer

SIGNATURE ELEMENT
  The batch record: numbered editions (№ 17/24), named glaze recipes that
  retire, kiln-position provenance in the collector quote. Scarcity that is
  true of the object, not a countdown timer. Webflow: vessels = divs with
  large asymmetric border-radius + linear-gradient backgrounds; chips =
  radial-gradient circles.

ASSETS NEEDED
  Google Fonts above · no images, no SVG — everything is CSS
```

---

## Shared discipline (all four)

- One page job, one primary CTA repeated verbatim at every decision point;
  secondary actions ghost-quiet.
- 5-second test: what / who / what-to-do above every fold.
- Proof placed next to decisions (ratings by CTAs, guarantees in buy boxes).
- One border-radius value per concept, hairline borders, no default drop-shadows.
- Focus-visible outlines, `prefers-reduced-motion` respected, ≥44px tap
  targets, mobile breakpoints, sticky mobile ATC where it earns its place.
- All copy, data, reviews and stock counts are illustrative portfolio content.
