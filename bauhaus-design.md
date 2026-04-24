---
name: Bauhaus
description: Form follows function. Primary colors, square grids, sans-serif honesty, material truth.
colors:
  --red: "#e63946"
  --blue: "#457b9d"
  --yellow: "#ffb703"
  --black: "#1d1d1d"
  --white: "#ffffff"
  --bg: "#f5f2ed"
  --bg-alt: "#e8e4dd"
  --text: "#1a1a1a"
  --text-secondary: "#5a5a5a"
  --gray: "#8d99ae"
rounded:
  none: "0px"
  sm: "2px"
  md: "4px"
spacing:
  unit: "8px"
  xs: "8px"
  sm: "16px"
  md: "24px"
  lg: "48px"
typography:
  h1:
    fontFamily: "Futura"
    fontSize: "2.75rem"
    fontWeight: 700
    letterSpacing: "-0.02em"
  body:
    fontFamily: "Fira Sans"
    fontSize: "1rem"
    fontWeight: 400
  mono:
    fontFamily: "JetBrains Mono"
    fontSize: "0.85rem"
layout:
  columns: 12
---
## Overview
Bauhaus: form follows function. Ornament is structural, never superfluous. The aesthetic is honest — colors reveal their nature, borders declare themselves, typography stays neutral. This design reads like a factory floor made beautiful through pure geometry.

## Color System
Only the three primaries plus black and white, exactly as the school taught.
- **Red**: Energetic, alerts
- **Blue**: Calm, informational
- **Yellow**: Highlight, attention
- **Black**: Structure, text
- **White**: Ground, separation

All colors are flat, fully saturated. No gradients or tints.

## Typography
Sans-serif only. **Futura**: geometric circles, mathematical proportions. **Fira Sans**: neutral, readable. **JetBrains Mono**: technical, low-level.

## Layout
A strict 8px base unit grid. All elements snap to multiples. The grid is invisible but felt.

## Elevation
No shadow. Elevation signaled by size, color value, and position.

## Shapes
- Borders: `2px solid --black`
- Max radius: `4px`
- Corners square unless a specific reason to round

## Components
- Primary button: black fill, white text; hover inverts
- Secondary button: transparent with solid black border
- Cards: white fill, 2px black border only

## Rules
- Use primaries in equal measure — never let one dominate
- Every element aligns to 8px grid
- Borders on every interactive element
- No soft shadows or opacity
- Mix weights only deliberately – one font-weight per role