---
name: ZenMinimal
description: Quiet. Monochrome. Space is element, not background. Japanese ink-wash calm.
colors:
  --bg: "#fcfcfc"
  --bg-elev: "#f4f4f4"
  --text: "#1a1a1a"
  --text-tinted: "#444444"
  --text-subtle: "#888888"
  --ink: "#333333"
  --accent: "#c44d00"
  --border: "#e0e0e0"
rounded:
  sm: "2px"
  md: "4px"
  lg: "8px"
spacing:
  sm: "16px"
  md: "32px"
  lg: "64px"
  xl: "128px"
typography:
  h1:
    fontFamily: "Noto Serif JP"
    fontSize: "2.75rem"
    lineHeight: 1.3
  body:
    fontFamily: "Noto Sans"
    fontSize: "1.0625rem"
    lineHeight: 1.75
---
## Overview
Zen Minimal starts from less-is-nothing. Every element must justify each pixel. The aesthetic channels *ma* — the space between things — where quietness becomes active ingredient.

## Color System
Essentially monochrome with one accent. Paper off-white; ink charcoal.
Accent appears sparingly — only where the eye must land.

## Typography
Noto Serif JP for headlines (Japanese serif, ink-trap elegance); Noto Sans for body (geometric neutrality). Generous leading; tight tracking on caps.

## Layout
Invisible 8px baseline; margins prefer multiples of 8/16 but slight offsets (2–4px) maintain an illusion of chance.

Sections separated by 64px; vast negative space controls rhythm.

## Components
Primary button: transparent with ink border; hover fills with ink, reversing to white-on-black.
Inputs: only a bottom rule — expands upward on focus into a full field outline.

## Motion
Slow. Ease-out, 0.3–0.5s. No bounce. Motion feels viscous.

## Do's and Don'ts
- Do keep it quiet
- Do leave more space than you think you need
- Do single accent across app
- Do ensure text never pure black on white
- Do treat fonts as artifacts, not tools
- Do poke a hole in the grid occasionally
- Don't use gradients or glows
- Don't spring-animate
- Don't use more than 2 fonts