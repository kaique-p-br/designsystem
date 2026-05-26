# Performaweb — Design System

A living reference for designing and building Performaweb surfaces: decks, marketing pages, app UI, and one-off prototypes.

## What is Performaweb?

Performaweb is a web-focused brand whose wordmark is two words separated by a space — **performa** in white and **web** in amber — anchored by a duotone **play-arrow** mark (two stacked triangles, amber + deep-orange center). Because "performa" is white, the wordmark sits on a dark background _or_ on the brand blue `#0077C8`; both work equally well. On light surfaces use the short-form logo (`logo-curta.png`) or the arrow mark alone. The mark reads as _motion_, _forward_, and _play/publish_. The brand leans friendly, confident, and bright: a blue + amber combo that is energetic without being loud.

> Brand assets and color/typography guidance in this system were provided directly by the client. No codebase or Figma file was attached — recreations of product screens are therefore deferred until those sources are available. See **Caveats** at the bottom.

## Sources

- **Logos** — `uploads/Logo.png` (full wordmark), `uploads/logo curta.png` (arrow mark with small ghost copy), `uploads/Asset Seta.png` (isolated arrow).
- **Fonts** — `uploads/Poppins-Regular.ttf`, `uploads/Poppins-Bold.ttf`.
- **Color & usage rules** — supplied in the brief (see _Visual Foundations → Colors_).
- **Codebase** — _not provided_.
- **Figma** — _not provided_.

---

## Index

Root files
- `README.md` — this document.
- `colors_and_type.css` — CSS variables + element defaults. Import this into any HTML surface.
- `SKILL.md` — skill manifest for reuse in Claude Code.

Folders
- `assets/` — logos and the arrow motif (`logo-performaweb.png`, `logo-curta.png`, `asset-seta.png`).
- `fonts/` — Poppins (Regular, Bold) TTFs.
- `preview/` — cards rendered in the Design System tab (Type, Colors, Spacing, Components, Brand).
- `ui_kits/` — product-specific UI kits. _Pending codebase/Figma — see Caveats._
- `slides/` — deck templates. _None supplied; not built._

---

## Content Fundamentals

The brief was written in **Brazilian Portuguese**, so the brand's primary voice is pt-BR. A few things we can infer from the brief's own phrasing ("Utilizar em todos os cartões", "Estou enviando os assets"):

- **Tone** — direct, instructional, warm. Short declarative sentences. No hedging.
- **Pronouns** — institutional "nós / a gente" when talking about the product; "você" when addressing the reader (never "tu", never "o usuário").
- **Casing** — Sentence case for UI labels and titles. The wordmark itself is **lowercase** ("performaweb") — treat that as a rule: never write _Performaweb_ in product chrome when the logo is adjacent; reserve capitalization for body prose.
- **No emoji** in brand surfaces. The duotone arrow is the brand's emotion — use it instead of an emoji when a surface needs energy.
- **Numerals** — digits, not spelled out (e.g. "3 passos", not "três passos").
- **Vibe** — optimistic, forward-moving, "apertar play". Avoid jargon and corporate stiffness. Avoid exclamation marks except at genuine celebration moments.

### Do / Don't examples (copy)

| Do                                               | Don't                                     |
| ------------------------------------------------ | ----------------------------------------- |
| "Sua presença online, com performance."          | "A melhor solução do mercado!!!"          |
| "Comece agora"                                   | "Clique aqui para iniciar o processo"     |
| "performaweb" (logo-adjacent)                    | "PerformaWeb" or "PERFORMAWEB"            |
| "3 passos rápidos"                               | "Três passos super fáceis e descomplicados" |

---

## Visual Foundations

### Colors

Client-supplied tokens, plus a small set of neutrals + states derived to round out the system.

| Token           | Hex       | Role                                            |
| --------------- | --------- | ----------------------------------------------- |
| `--pw-blue`     | `#0077C8` | Primary accent, buttons, links                  |
| `--pw-blue-ink` | `#005E9E` | Blue hover / pressed                            |
| `--pw-blue-soft`| `#E6F2FA` | Tinted surfaces, chips                          |
| `--pw-amber`    | `#F8AD07` | **Titles**, wordmark "web", arrow mark outline  |
| `--pw-amber-ink`| `#D89105` | Amber hover / pressed                           |
| `--pw-amber-deep`|`#F08C00` | Inner triangle of the arrow mark                |
| `--pw-ink`      | `#1A1A1A` | "performa" wordmark, strongest text             |
| `--pw-body`     | `#706F6F` | Body copy                                       |
| `--pw-muted`    | `#A8A8A8` | Captions, placeholders, disabled                |
| `--pw-hairline` | `#E6E6E6` | Borders, dividers                               |
| `--pw-surface-alt`|`#F5F7FA`| Page tint behind white cards                    |
| `--pw-card`     | `#FFFFFF` | Card fill                                       |

**Rule of thumb:** titles are **amber**, body is **grey #706F6F**, calls to action are **blue**. This produces the signature three-tone page: amber headline, grey paragraph, blue button.

### Typography

Single family: **Poppins** (Regular 400 + Bold 700). No italic; no display serif.

- **Display / H1** — Poppins Bold, tight tracking (`-0.01em`), amber.
- **H2/H3** — Poppins Bold, amber.
- **Body** — Poppins Regular, 16/24, grey `#706F6F`.
- **Eyebrow** — Poppins Bold, 12px, UPPERCASE, blue, `+0.04em` tracking.
- **Link** — Poppins Bold, blue, underline on hover only.

### Backgrounds

- Primary surface is **white cards on a pale neutral `#F5F7FA` canvas**. The white card is the hero shape of the system.
- Full-bleed images are allowed behind hero sections; keep them muted so the amber arrow mark reads cleanly.
- **Avoid** busy gradients, photographic collage, and hand-drawn illustration — the brand is geometric (two triangles).
- **The arrow mark is the only decorative motif** the system leans on. A single translucent arrow at 6–10% opacity behind a hero is permitted; more than one is not.

### Card rules (from brief)

Every white card must include the brand chrome:

- **Top-right corner** — the isolated arrow (`assets/asset-seta.png`), ~48–64px wide.
- **Bottom-right corner** — the short logo (`assets/logo-curta.png`), ~40–56px wide.

Use `.pw-card--branded` in `colors_and_type.css` to get this chrome for free.

### Corners, borders, shadows

- **Radii** — 8 / 12 / 20 / 28 / pill. Cards default to **20px**. Buttons default to **pill**.
- **Borders** — 1px `#E6E6E6` hairlines. Avoid colored borders except for focus rings.
- **Shadows** — soft, cool, low-spread. Three steps: `shadow-1` (resting), `shadow-2` (cards), `shadow-3` (elevated/modals). No inner shadows.
- **No glassmorphism. No heavy blur.** Transparency is reserved for the arrow watermark trick.

### Spacing

8pt baseline grid. Tokens: 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96. Cards use 32 padding; section rhythm is 48–96.

### Motion & states

- **Easing** — single curve: `cubic-bezier(0.2, 0.8, 0.2, 1)`. Snappy in, gentle out.
- **Durations** — 120 / 200 / 320 ms. Nothing slower.
- **Hover** — buttons darken one step (blue → blue-ink, amber → amber-ink) and gain one shadow step. Links turn blue-ink and underline.
- **Pressed** — `translateY(1px)`, no color change beyond the darken.
- **Focus** — 3px blue halo (`--shadow-focus`).
- **No bounce, no rubber-band, no confetti.** The only "playful" gesture is the brand already being a play button.

### Layout rules

- Fixed top nav, 72px tall, white.
- Max content width: 1200px. Gutters: 24 mobile / 32 tablet / 48+ desktop.
- Sections breathe — minimum 64px top/bottom padding on desktop.

---

## Iconography

**No icon set was provided.** The brand's only inherent glyph is the duotone **arrow mark** (`asset-seta.png`) — treat it as a logo, not a reusable icon.

For UI icons we **substitute Lucide** (via CDN). Lucide is stroke-based, 24×24, 1.5–2px strokes, rounded joins — this matches Poppins' soft-geometric feel better than Heroicons (too thin) or Material (too squared).

- **CDN** — `https://unpkg.com/lucide@latest`
- **Usage** — stroke color should inherit `currentColor`. In brand contexts use `--pw-blue` or `--pw-ink`; never amber (amber is reserved for titles + the arrow mark).
- **Sizes** — 16, 20, 24, 32.

**Emoji are not used.** Unicode symbols (→, ✓, ×) are permitted as plain text affordances in body copy only. For any bigger-than-inline indicator, use a Lucide icon.

> ⚠️ **Substitution flagged:** Lucide stands in for a missing icon set. If Performaweb has a canonical icon library, please share it and we'll replace Lucide throughout.

---

## Caveats & open questions

- **No codebase / no Figma.** UI kits and product slides are not yet built because we'd otherwise be inventing UI rather than _recreating_ it. Please share a codebase, Figma file, or even screenshots of the live product so we can build `ui_kits/` properly.
- **Icon set** — we're using Lucide as a stand-in. If there's a house icon set, please send it.
- **Blue isn't in the logo.** The brief specifies `#0077C8` as the primary accent, but the wordmark itself is amber + black. We've treated blue as the _action_ color (buttons, links, focus) and amber as the _headline_ color, which resolves the tension cleanly — confirm this split works for you.
- **Photography style, illustration, motion guidelines beyond hover/press** — not specified. Assumptions documented above; flag anything that feels off.

---

## Bold ask

👉 **Please share a codebase link (GitHub, ZIP) or a Figma URL for any existing Performaweb product.** Without it, the UI kit and slide templates are deferred. Everything else (colors, type, fonts, cards, buttons) is ready to use today via `colors_and_type.css`.
