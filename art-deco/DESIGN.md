---
name: ArtDeco
description: Geometric opulence from the 1920s. Stepped forms, metallic sheen, bold symmetry.
colors:
  --bg: "#0f1014"
  --gold: "#c9a227"
  --gold-bright: "#f7c948"
  --gold-dark: "#8b6f1e"
  --silver: "#a8a9a4"
  --text: "#f0e9d2"
  --text-dim: "#9a9678"
  --black: "#080808"
  --white: "#f4f1ea"
  --accent: "#c4274b"
  --accent-alt: "#2a6f97"
rounded:
  xs: "2px"
  sm: "4px"
  md: "8px"
  lg: "0px"
spacing:
  xs: "8px"
  sm: "16px"
  md: "32px"
  lg: "64px"
typography:
  h1:
    fontFamily: "Playfair Display"
    fontSize: "3.5rem"
    fontWeight: 700
    letterSpacing: "0.02em"
  body:
    fontFamily: "Cormorant Garamond"
    fontSize: "1.125rem"
    lineHeight: 1.6
  label:
    fontFamily: "Bebas Neue"
    fontSize: "0.875rem"
    letterSpacing: "0.15em"
    fontWeight: 400
---
## Overview
Art Deco reclaims the Machine Age's ornament. Symmetry, geometry, metallic sheen. The aesthetic skyscraper setbacks and ocean liner interiors: straight lines, stepped profiles, chrome gleam. Every element appears cast in metal and lacquer.

## Color System
A palette built on five pillars:
- **`--bg`**: `#0f1014` — lacquer black, absorbs light
- **`--gold`**: `#c9a227` — central material; appears as borders, highlights, frames
- **`--gold-bright`**: `#f7c948` — glint, hover state
- **`--gold-dark`**: `#8b6f1e` — shadow-face of gold
- **`--accent`**: `#c4274b` — cinnabar, rare and theatrical; warns, alerts

All non-metallic colors are grayscale between `--bg-light` and `--white`.

## Typography
- **Headings**: Playfair Display — Didone contrast, sharp serifs, engraved plate feel
- **Body**: Cormorant Garamond — humanist softness to temper the metal
- **Labels**: Bebas Neue — all-caps, industrial stamping

## Forms & Geometry
Buttons use stepped profile: background in gold, top border in bright, bottom in dark, plus a solid black shadow. This simulates a raised, faceted surface.

## Do's and Don'ts
- **Do** maintain gold as the only two-tone material
- **Do** use 0 or 2px radius; right angles please
- **Do** reserve accents for rare alerts
- **Do** use symmetrical layouts within narrow (`960px`) width
- **Do** apply generous margins (`--spacing.lg`)
- **Don't** mix other bold colors — gold is the only ornament
- **Don't** use gradients
- **Don't** use curves; Deco is straight-lined geometry
- **Don't** use thin borders; 2px minimum