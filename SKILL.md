---
name: performaweb-design
description: Use this skill to generate well-branded interfaces and assets for Performaweb, either for production or throwaway prototypes/mocks/etc. Contains essential design guidelines, colors, type, fonts, assets, and UI kit components for prototyping.
user-invocable: true
---

Read the README.md file within this skill, and explore the other available files.
If creating visual artifacts (slides, mocks, throwaway prototypes, etc), copy assets out and create static HTML files for the user to view. If working on production code, you can copy assets and read the rules here to become an expert in designing with this brand.
If the user invokes this skill without any other guidance, ask them what they want to build or design, ask some questions, and act as an expert designer who outputs HTML artifacts _or_ production code, depending on the need.

## Quick reference

- Brand: **Performaweb** — lowercase wordmark, two-tone (black "performa" + amber "web") locked to a duotone play-arrow mark.
- Primary accent / buttons / links: **#0077C8** (blue).
- Titles: **#F8AD07** (amber). Body: **#706F6F** (grey). Ink: **#1A1A1A**.
- Typeface: **Poppins** (Regular 400 + Bold 700). TTFs in `fonts/`.
- Cards are white with **arrow top-right** and **logo curta bottom-right** — non-negotiable brand rule.
- Import `colors_and_type.css` to get CSS variables, element defaults, `.pw-btn`, and `.pw-card--branded`.

## Files

- `README.md` — full brand, content, visual, and iconography guidelines.
- `colors_and_type.css` — tokens + base elements + primitives.
- `assets/` — logo-performaweb.png, logo-curta.png, asset-seta.png.
- `fonts/` — Poppins TTFs.
- `preview/` — rendered specimen cards.

## Caveats

- No codebase or Figma was provided — UI kits and product-specific slide templates are deferred pending source material.
- Icon set is substituted with Lucide; replace if Performaweb has a house set.
