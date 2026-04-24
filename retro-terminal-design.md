---
name: RetroTerminal
description: 1970s–1990s monochrome terminal aesthetic — CRT scanlines, phosphor glow, pixel grid.
colors:
  --bg: "#1a1c20"
  --screen: "#0f1216"
  --text: "#d4d4d4"
  --green: "#33ff00"
  --amber: "#ffb000"
  --cyan: "#00f0f0"
  --red-dim: "#881111"
  --grid: "rgba(51,255,0,0.06)"
rounded:
  none: "0px"
  sm: "2px"
spacing:
  unit: "2px"
  xs: "4px"
  sm: "8px"
  md: "16px"
typography:
  h1:
    fontFamily: "VT323"
    fontSize: "2.5rem"
    textShadow: "0 0 6px var(--green)"
  body:
    fontFamily: "JetBrains Mono"
    fontSize: "0.875rem"
    lineHeight: 1.5
bloom:
  enabled: true
  color: "var(--green)"
  intensity: 0.2
guides:
  type: "fixed"
  step: "4px"
  color: "rgba(51,255,0,0.06)"
---
## Overview
Monochrome CRT terminals — the era of DEC VT220, Amiga Workbench, early Macintosh. Scanlines, phosphor bloom, a grid working in 2px increments.

## Color System
Primary is phosphor green (`#33ff00`). Amber and cyan are alternatives. Backgrounds are near-black (`#0f1216` text on `#1a1c20`).

## Typography
VT323 (pixel font from VGA era) for headlines; JetBrains Mono rendered with no antialiasing.

## Visual Effects
- **Scanlines**: `linear-gradient(0deg, transparent 50%, rgba(0,0,0,0.2) 50%)`, 4px size
- **Bloom**: glow around text and key elements
- **Blinking cursor**: solid block with 1s step blink

## Layout
2px pixel grid underlay; elements align to grid; borders exactly 1 or 2px.

## Components
Window chrome: minimal; buttons beveled (top/left lighter, bottom-right darker). Inputs: bottom-border only until focus.

## Motion
None, or abrupt no-interpol. No smooth easing.

## Do's and Don'ts
- Use 2px precise grid
- Text no antialiasing
- Scanline overlay across app
- Active = solid color; dim inactive
- Density is a virtue
- No blur shadows — CRTs don't have them
- Radius = 0 or 2px maximum