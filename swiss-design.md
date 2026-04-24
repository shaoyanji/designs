---
name: SwissInternational
description: The grid as law. Objective clarity, sans-serif tone, asymmetry, breath.
colors:
  --bg: "#ffffff"
  --bg-gray: "#f4f4f4"
  --text: "#111111"
  --text-secondary: "#555555"
  --accent: "#0066cc"
  --accent-hover: "#004499"
  --border: "#e0e0e0"
rounded:
  xs: "2px"
  sm: "4px"
  md: "8px"
spacing:
  unit: "8px"
  sm: "16px"
  md: "24px"
  lg: "48px"
typography:
  h1:
    fontFamily: "Helvetica Now"
    fontSize: "2.5rem"
    fontWeight: 700
    lineHeight: 1.2
  body:
    fontFamily: "Helvetica Now"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  mono:
    fontFamily: "Source Code Pro"
    fontSize: "0.875rem"
layout:
  columns: 12
  maxWidth: "1120px"
  gutter: "24px"
  baseline: "1.6rem"
---
## Overview
Content is king. The designer makes information objectively clear through grid discipline, asymmetric composition, and sans-serif neutrality. There is no decorative flourish — only hierarchy, proportion, and white space.

## Color System
Restrained to convey hierarchy without chroma noise.
Only one accent color (`--accent` blue); everything else monochrome.

## Typography
Helvetica Now is the voice of neutrality. Baselines are sacred. All vertical margins are multiples of 8px.

## Layout
A 12-column grid centered within 1120px. Asymmetry is intentional but grid-constrained.

## Elevation
No drop-shadows. Cards have an almost-invisible emboss; `box-shadow: 0 1px 3px rgba(0,0,0,0.08)`.

## Do's and Don'ts
- Do trust the grid
- Do use 1 type family
- Do asymmetric balance, not centered
- Do baseline alignment for all text
- Do never pure black — `#111` is enough
- Do prioritize readability above all else
- Don't add extra colors
- Don't animate for decoration
- Don't underline — use bold