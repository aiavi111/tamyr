# TAMYR — Design System

## Overview

TAMYR is an original real-estate & construction brand system, built from scratch for this project. There is no existing company called TAMYR — the name was supplied by the user; everything else (palette, type, components, copy, UI kit) is an original design authored here.

**Why "original" and not a recreation:** the only material provided was a single screenshot (`uploads/Spaciaz – Real Estate & Construction Group WordPress Theme (1).jpeg`) of a commercial WordPress theme called *Spaciaz*, sold by a third-party author on ThemeForest. The image itself carries a watermark from a site that redistributes pirated/"nulled" premium themes. Rather than reverse-engineer a paid product from an unlicensed screenshot, this system borrows only the general, non-proprietary *mood* the user pointed at — a dark charcoal ground, an acid-lime accent, big confident stat numbers, an editorial grotesque headline face — and rebuilds it as its own brand, with its own exact colors, type, spacing, components and copy. No layout, copy, icon, or image from that screenshot was copied.

## Sources

- `uploads/Spaciaz – Real Estate & Construction Group WordPress Theme (1).jpeg` — mood reference only (see above). Not used as a pixel or content source.
- No codebase, Figma file, brand guidelines, logo, photography, or icon set was supplied for TAMYR. Every asset below (tokens, components, UI kit, copy) is original, sized to a generic real-estate & construction group.
- If a real TAMYR codebase, Figma file, brand guide, logo, or photo library exists, attach it and this system should be re-derived from that source of truth instead.

## Content fundamentals

**Voice:** confident and matter-of-fact. TAMYR talks about itself in first person plural ("we build", "our projects") and addresses the reader as "you" ("your project", "get in touch"). No hype adjectives ("world-class", "revolutionary", "cutting-edge") — claims are backed by a number or a fact instead.

- Headline: "Built for how the city grows" — short, concrete, no adjective doing the work.
- Supporting line: "TAMYR plans, finances, and builds real estate projects across the region, from first site survey to final handover."
- Stat labels write the number as a numeral with a live "+", the noun underneath: "48+", "completed projects". Never spelled out ("forty-eight").
- CTAs are short imperatives: "View our projects", "Talk to our team", "See services" — verb first, no "Learn more about how...".
- Section eyebrows (small label above a headline) are ALL CAPS, 2–4 words: "WHO WE ARE", "OUR SERVICES".

**Casing:** sentence case for headlines and body ("Built for how the city grows"), Title Case only for short nav/menu labels ("Projects", "Our Team"), ALL CAPS with wide tracking reserved for eyebrows and micro-labels only.

**Numbers:** always numerals, always concrete ("52+ projects in development", "18M+ sq ft", "40 years"). Percentages and currency follow the same rule.

**Emoji:** none. This is a corporate B2B/B2C construction and property brand — icons carry visual emphasis, not emoji.

## Visual foundations

**Color:** two grounds, one accent. Sections alternate between a warm off-black (`--ink-950`) and a warm cream (`--bg-page`) — never both in the same section. A single acid-lime (`--lime-500`) is the only saturated accent, reserved for primary CTAs, the odd badge, and stat highlights, so it stays sharp instead of decorative. Semantic colors lean into the industry rather than generic web red/green/blue: a brick terracotta for danger, a safety amber for warning, a blueprint slate-blue for info, a deeper moss green for success — see `guidelines/colors-semantic.card.html`.

**Type:** one display face (Familjen Grotesk, a rounded-corner grotesque) for headlines and numerals, one text face (Karla, humanist and legible) for everything you read in paragraphs. Headlines run tight (`--leading-tight`, `--tracking-tight`); body text runs relaxed (`--leading-relaxed`) for long-form paragraphs. See "Fonts" caveat below.

**Spacing:** a 4px base scale (`--space-1`…`--space-32`). Sections are generous — `--section-pad-y` clamps roughly 56–112px depending on viewport. Content is capped at `--content-max` (1320px) and centered.

**Backgrounds:** flat color fills only — no gradients, no repeating textures or patterns, no hand-drawn illustration. The one exception is a full-bleed photographic band used for the stats section (a dark, contained photo with a soft bottom-up dark gradient — a "protection gradient" — so number labels stay legible over the image). Elsewhere, photography sits inside large rounded panels next to text, never as a background behind copy.

**Animation:** restrained, no bounce or spring. Content fades and rises slightly on scroll-in (`--duration-base` 220ms, `--ease-out`). Nothing loops or auto-plays.

**Hover states:** primary (lime) buttons darken to `--lime-600`; dark/outline buttons lighten their fill slightly; text links switch from `--link` to `--link-hover` and gain an underline. The circular icon-arrow button (used for CTAs and cards) rotates 45° on hover — the one signature motion flourish in the system.

**Press states:** buttons and cards scale to 0.97 with no color change beyond the existing hover state — a quick, physical tap, not a color shift.

**Borders:** hairline (1px), low-contrast, and used sparingly — around inputs and as list dividers only. `--border-hairline` on cream, a translucent white (`--border-hairline-inverse`) on ink. Cards never carry a border; they're told apart by fill color, not a stroke.

**Shadow:** minimal by design. Cards are flat. Shadow (`--shadow-sm/md/lg`) is reserved for things that actually float above the page — dialogs, dropdowns, tooltips.

**Transparency & blur:** used narrowly — a translucent frosted nav bar on scroll (`backdrop-filter: blur(...)`), and a translucent dark wash over any photo that needs a text caption on top of it. Never used decoratively (no glassmorphic cards).

**Imagery color vibe:** (no real photography was supplied — every photo slot in the UI kit is a labeled placeholder). The intended grade is warm-neutral architectural photography — dusk/golden-hour city and building shots, lightly warm, not cold-blue, not black & white, not heavily grained.

**Corner radii:** generous and consistent — 24px on large cards and photo panels (`--radius-lg`), 14px on inputs and small cards (`--radius-md`), full pill (`--radius-pill`) on every button, tag, badge, and the nav itself.

**Cards:** borderless, flat-filled, 24px-rounded. A card's role is shown by its fill — ink-950 (dark/neutral), lime-500 (accent/highlighted), cream-300 (light), or a photo — never by adding a shadow or a colored left border.

**Layout rules:** centered content column at `--content-max`; nav is fixed to the top and gains a frosted background once the page scrolls; sections are full-width color bands so the alternating dark/cream rhythm reads even on a quick scroll.

## Iconography

No icon font, sprite, or SVG set was supplied with the source screenshot. TAMYR uses **[Lucide](https://lucide.dev)** icons (loaded live from `unpkg.com/lucide`, MIT-licensed), substituted for its plain, consistent 1.5px stroke and rounded joins — a close match to the rounded-grotesque display type. This is a flagged substitution: if TAMYR has its own icon set, swap it in and update `components/**` icon usage.

- Icons render inline via `<i data-lucide="name">` + `lucide.createIcons()`, so they inherit `color` (`stroke="currentColor"`) and can be recolored per button/state.
- No emoji, no unicode-symbol icons.
- The one custom "icon" in the system is the circular arrow button (a plain circle + a Lucide `arrow-up-right`) used throughout as the CTA/card motif — see `components/core/IconButton.jsx`.
- No logo mark exists for TAMYR. Every place a mark would go instead renders the wordmark "TAMYR" in the display face — see `components/navigation/NavBar.jsx` and `thumbnail.html`. If a real logo exists, drop it in `assets/logo.svg` and it will be picked up automatically by templates/cards that look for it.

## Intentional additions (components beyond the standard set)

No source defined a component inventory (brand-guidelines-only run), so the standard primitive set (Button, IconButton, Input, Select, Checkbox, Radio, Switch, Card, Badge, Tag, Tabs, Dialog, Toast, Tooltip) was authored, plus these marketing-site-specific additions:

- **NavBar** — every product needs its own top nav; sized to TAMYR's pill-button, frosted-on-scroll header.
- **StatCard** — the big-number-plus-label unit that drives the stats band; distinct enough from a generic Card to warrant its own component.
- **FeatureCard** — the three-tone (dark / accent / photo) card used for "what we do"-style triads.
- **TestimonialCard** / **PersonCard** — quote-plus-attribution and headshot-plus-role units used across About and social-proof sections.

## Fonts — substitution flag

No font files shipped with the source material. **Familjen Grotesk** (display) and **Karla** (body) were chosen as an open, Google-Fonts-hosted pairing in the spirit of the reference mood (a rounded, confident grotesque headline over a plain humanist body). They're loaded live via `tokens/fonts.css` (`@import` from Google Fonts) rather than self-hosted binaries, since no font files exist to embed. **If TAMYR has real brand fonts, upload the `.woff2` files and this should be switched to local `@font-face` rules** — ask and we'll wire it up.

## Index

- `styles.css` — root stylesheet, `@import`s everything below.
- `tokens/` — `colors.css`, `typography.css`, `spacing.css`, `effects.css`, `fonts.css`.
- `guidelines/` — 17 foundation specimen cards (Design System tab groups: Colors, Type, Spacing, Effects, Brand).
- `components/` — 19 React UI primitives, one `@dsCard` per directory:
  - `core/` — Button, IconButton, Badge, Tag, Card
  - `forms/` — Input, Select, Checkbox, Radio, Switch
  - `feedback/` — Dialog, Toast, Tooltip
  - `navigation/` — NavBar, Tabs
  - `marketing/` — StatCard, FeatureCard, TestimonialCard, PersonCard (see "Intentional additions" above)

  Each component: `<Name>.jsx`, `<Name>.d.ts`, `<Name>.prompt.md`.
- `ui_kits/marketing-site/` — click-through TAMYR marketing site: Home, Projects (filterable grid), Project detail, About (leadership grid), Contact (working form state). `README.md` inside documents the routing.
- `assets/image-slot.js` — the placeholder-photo component used throughout (no real photography was supplied).
- `thumbnail.html` — homepage tile for this design system.
- `SKILL.md` — Claude-Code-compatible skill wrapper for this system.
