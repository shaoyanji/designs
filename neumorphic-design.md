---
name: Neumorphic
description: Soft, tactile surfaces that feel extruded from the background. Light as physical material.
colors:
  --bg: "#e0e5ec"
  --surface: "#e0e5ec"
  --text: "#4a5568"
  --text-dim: "#718096"
  --shadow-light: "#ffffff"
  --shadow-dark: "#a3b1c6"
  --primary: "#667eea"
  --primary-hover: "#5a67d8"
  --success: "#48bb78"
  --warning: "#ed8936"
  --error: "#f56565"
typography:
  h1:
    fontFamily: "Inter"
    fontSize: "2.25rem"
    fontWeight: 700
  body:
    fontFamily: "Inter"
    fontSize: "1rem"
    fontWeight: 400
  label:
    fontFamily: "Inter"
    fontSize: "0.75rem"
    fontWeight: 600
    letterSpacing: "0.05em"
rounded:
  sm: "4px"
  md: "8px"
  lg: "16px"
spacing:
  xs: "4px"
  sm: "8px"
  md: "16px"
  lg: "24px"
layout:
  mode: inset-extruded
---
## Overview
Neumorphism — soft UI — renders elements as extrusions from a continuous surface. The illusion of depth comes from two opposing shadows: a light source above-left casts a light shadow top-left and a dark shadow bottom-right. The result feels like pressing into soft material.

## Colors
- **Surface (`#e0e5ec`)**: cool gray-blue, the single source of truth  
- **Text (`#4a5568`)**: desaturated slate — no pure black
- **Primary (`#667eea`)**: a moderated indigo, saturated enough to be noticed but restrained

**Shadows** are just lighter and darker versions of surface mixed with white (light) and charcoal (dark). They are the only depth cue.

## Typography
Inter's geometric neutrality supports the abstracted material. Visually, Inter is engineered, not written — matching the machine-made aesthetic.

## Elevation
| State | Shadow |
|-------|--------|
| Raised | `8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light)` |
| Pressed | `inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light)` |

The inset variant inverts the shadow direction, making the element feel sunken into the material.

## Shapes
All components are rounded, not square (`≥4px`). This suggests softness and prevents the material from feeling like plastic.

## Do's and Don'ts
- **Do** keep the global light source top-left consistently
- **Do** use inset shadow for text fields — they're depressions awaiting input
- **Do** reserve primary color for text and focus rings only; never fill
- **Don't** use flat colors with solid borders; the shadow creates the edge
- **Don't** apply drop-shadows on top of neumorphic shadows
- **Don't** use elevation greater than 8px — beyond that it turns cartoonish