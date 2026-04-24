---
name: CyberGlow
description: Terminal elegance meets neon metropolis. Dark voids pierced by saturated light.
colors:
  --bg-deep: "#050505"
  --bg-surface: "#0f1219"
  --text: "#e6e8ef"
  --text-dim: "#6b7088"
  --cyan: "#00f0ff"
  --magenta: "#ff00aa"
  --amber: "#ffb800"
  --green: "#00ff8c"
  --red: "#ff2d4d"
rounded:
  none: "0px"
  xs: "2px"
  sm: "4px"
  md: "6px"
spacing:
  xs: "8px"
  sm: "16px"
  md: "24px"
  lg: "48px"
typography:
  h1:
    fontFamily: "Orbitron"
    fontSize: "2.5rem"
    letterSpacing: "0.08em"
    textShadow: "0 0 10px var(--cyan)66"
  body:
    fontFamily: "JetBrains Mono"
    fontSize: "0.9rem"
    lineHeight: 1.6
---
## Overview
The interface as an HUD in a near-future craft. Dark by default; colored light is the only illumination. Thin borders, monospace voice, dense with signals.

## Color System
Canvas `#050505`; surfaces `#0f1219`. Accents radiate additive light:
- **Cyan**: navigation
- **Magenta**: alerts
- **Amber**: warnings
- **Green** or online presence

Each accent defines a state family — text, borders, glows, shadows.

## Glow Pattern
``box-shadow: 0 0 12px color33, inset 0 0 4px color22;``

## Typography
Orbitron (boxy, technical) for headlines; JetBrains Mono everywhere else. Tight tracking on labels (0.1em) uppercase.

## Layout
A grid-over-grid layout; base is 24px, nested HUDs at 4px steps. Left sidebar status feed; right column is diagnostics.

Borders are 1–2px colored hairlines (`color33`). Z-indices: base=0, glow=10, overlay=20.

## Components
Neon buttons: transparent fill, colored border, glow; hover fills as wash. Terminal panels: line numbers, syntax highlighting. HUD brackets: corner glyphs.

## Do's and Don'ts
- Do use glow to convey system state
- Do use 8px base for all spacing
- Do hide non-essential data behind hover
- Do use cyan/amber for system vs user
- Do keep background at `#050505`
- Don't use colors outside the accent set
- Don't use curves
- Don't remove borders