---
name: clinical-instrument
category: web-ui
date: 2026-04-24
source_project: cbb-harness
---

# Clinical Instrument UI

A diagnostic-interface aesthetic for tools that present complex, qualitative data through a non-deterministic model. The visual language is **austere, retro-scientific, and content-dense**. Every element signals measurement, prescription, or state transition.

## Philosophy

The interface is an instrument panel, not a dashboard. The user is an "observer" gathering signals from an unknowable system (the "black box"). The UI should feel like reading a oscilloscope or a medical monitor — precise, unembellished, and slightly cold.

## Color System

| Token | Value | Role |
|-------|-------|------|
| `--bg` | `#0a0a0c` | Deepest layer — the black box itself |
| `--bg-elev` | `#111114` | Header, elevated surfaces |
| `--bg-card` | `#16161a` | Content panels |
| `--border` | `#222228` | Structural hairlines |
| `--text` | `#c8c8d0` | Primary readable text |
| `--text-dim` | `#6e6e78` | Labels, secondary info |
| `--cyan` | `#00c4e0` | Observation layer — what the system reads |
| `--cyan-dim` | `#00c4e022` | Subtle cyan backgrounds |
| `--gold` | `#d4af37` | Prescription layer — what the system prescribes |
| `--gold-dim` | `#d4af3722` | Subtle gold backgrounds |
| `--yang` | `#ff4d4d` | Activity / heat / excess |
| `--yin` | `#4d79ff` | Structivity / cold / deficiency |

## Typography

- **JetBrains Mono** at 300–600 weight
- Section headers: 0.8rem, uppercase, `letter-spacing: 0.08em`, gold underline
- Body: 0.75rem–0.8rem
- Metric labels: 0.65rem, `--text-dim`
- The uppercase + wide tracking signals "instrument label" rather than "marketing headline"

## Layout

Two-column grid: inputs pinned left (control panel), outputs flowing right.

```
+-------------+---------------------------+
|  INPUTS     |  POLARITY | 8 CRITERIA   |
|  (sensors)  |---------------------------|
|             |  HEXAGRAM | SYSTEM STATE |
|  LLM        |---------------------------|
|  OBSERVER   |  TREATMENT PLAN           |
|             |---------------------------|
|             |  DIAGNOSTIC PATH          |
+-------------+---------------------------+
```

Panels use 1px borders (`--border`), 6px border-radius, zero shadows. Stacking creates elevation through nesting, not effects.

## Visual Encoding

### Hexagram
Six horizontal lines — solid for yang (1), split for yin (0). Upper trigram above, lower trigram below. Directly maps to a 6-bit encoding from the system's polarity vector. Not decorative; it is the live bitstring output.

### Bifurcation Badge
Severity gradient tied to complexity levels:
- Level 0 (equilibrium): `#2d5a2d` on `#7ee787`
- Level 1 (oscillation): `#5a4a1a` on `#f0d060`
- Level 2 (complex): `#5a2d2d` on `#ff8888`
- Level 3 (chaotic): `#3a1a3a` on `#d080ff`

### Treatment Points
Small bordered tags: gold outline, transparent fill. Evoke physical labels on a body map or acupuncture chart.

### Bars
Track (`--bg`) + fill (`--cyan`, `--yang`, `--yin`, `--gold`). Animate width transitions so drift between diagnostic cycles is visible.

## Rules

- No gradients, glow, glassmorphism
- No charts/graphs libraries — the hexagram *is* the visualization
- No rounded pill buttons
- No color outside the defined system
- No shadows on panels
- Density is high — this is a tool for an observer making decisions

## CSS Template

See `css/clinical-instrument.css` for the full stylesheet.

## Assets

- `assets/bifurcation-reference.png` — Feigenbaum map diagram
- `assets/hexagram-glyphs.svg` — I Ching line symbols
