# Design Inventory

A pre-populated library of visual design system manifests for agent-driven front-end work. Each folder contains a `DESIGN.md` file that encodes a complete design language in a structured, machine-readable format.

## What This Is

This repository is **design tokens as contracts**. Instead of asking an agent to invent a visual language from scratch, you point it at a known system. The agent reads the YAML front matter, extracts tokens, and applies them consistently — conserving output tokens that would otherwise be spent describing colors, spacing, and typography over and over.

## The Format

Every `DESIGN.md` follows the [Google `design.md` spec](https://github.com/google-labs-code/design.md) (v0alpha). It has two layers:

1. **YAML front matter** — machine-readable tokens for colors, typography, spacing, rounded corners, components, layout rules
2. **Markdown body** — human explanations of the philosophy, usage constraints, and things to avoid

### Front Matter Schema

```yaml
---
name: <design_system_name>
description: <one-line summary>
colors:
  --bg: "#xxxxxx"
  --text: "#xxxxxx"
  --accent: "#xxxxxx"
  ...
typography:
  h1:
    fontFamily: <font>
    fontSize: <size>
    fontWeight: <number>
  body: { ... }
  label: { ... }
rounded:
  xs: "<radius>"
  sm: "<radius>"
  md: "<radius>"
  lg: "<radius>"
spacing:
  xs: "<spacing>"
  sm: "<spacing>"
  md: "<spacing>"
  lg: "<spacing>"
components:
  button-primary: { ... }
  card: { ... }
  ...
layout:
  columns: <number>   # optional
  maxWidth: "<value>" # optional
  baseline: "<value>" # optional
---
```

Fields like `components` may include CSS snippets referencing tokens (`var(--bg)`, `{colors.--accent}`).

## Why This Exists

When an agent builds a UI, it normally spends many tokens describing the visual language — "use a dark theme, with blue accents, monospaced font, rounded buttons, subtle borders." That's 100–200 tokens per conversation. With this inventory, the agent can **import** an existing system in one line:

```
Use design system: biophilic
```

That instantly loads 14 systems into context with a known vocabulary. The agent no longer needs to invent or debate colors, fonts, radiuses — they're already declared, named, and sanctioned.

This is the **static-data analogue** of a skill library: instead of storing workflows, we store aesthetic palettes that can be referenced by name.

## Available Systems

| Folder | Vibe | Use When |
|--------|------|----------|
| `neumorphic/` | Soft extruded plastic, gentle shadows | Dashboard for wellness, fitness, gentle tools |
| `art-deco/` | 1920s geometric luxury, gold & black | Premium fintech, auction site, glamorous brand |
| `bauhaus/` | Primary color functionalism, hard borders | Dev tools, educational platforms, honest interfaces |
| `brutalist/` | Raw scale, acid colors, aggressive offset | Developer consoles, hackathon mvp, anti-corporate |
| `cyber-glow/` | Neon HUD, CRT phosphor, monospace density | Sci-fi dashboards, security ops, synthwave |
| `swiss/` | Grid clarity, Helvetica, asymmetric breath | Content-heavy sites, docs portals, publishing |
| `pop-retro/` | Mid-century commercial, hard shadows | Playful SaaS, creative tools, summer vibes |
| `wabi-sabi/` | Organic imperfection, paper texture | Meditation apps, artisan brands, slow media |
| `zen-minimal/` | Quiet monochrome, breathing room | Minimal dashboards, reading apps, zen tools |
| `renaissance-fresco/` | Aged plaster, pigment warmth | Art platforms, cultural archives, elegant portfolios |
| `biophilic/` | Living curves, watercolor, dappled light | Health/wellness, nature products, calming |
| `constructivist/` | Russian avant-garde, diagonals, slant | Propaganda tools, political apps, radical brands |
| `memphis/` | 80s dopamine, squiggles, mismatch | Youth culture, gaming, whimsical toys |
| `retro-terminal/` | Phosphor green, scanlines, pixel grid | Legacy system UIs, hacker tools, retro computing |

The existing `clinical-instrument/` and `dev-terminal/` are kept as reference implementations that predate the spec alignment.

## How to Use

An agent encountering a request to "design a UI" should:

1. **Pick a system** — Based on user vibe, domain, mood; consult the table above
2. **Load the tokens** — Read `DESIGN.md` front matter. Map `colors`, `typography`, `spacing`, `rounded` into a theme object
3. **Apply consistently** — Every component uses tokens, never hard-coded values
4. **Respect the "Do's and Don'ts"** — These guardrails are as important as the palette

### Quick Reference Pattern

```
Interface: {design_system}
Tokens: {colors, typography, spacing, components}
Apply-To: {all elements}
Constraints: read "Do's and Don'ts" section
```

### Example Agent Directive

```
Design a dashboard for monitoring LLM inference costs.
Interface: cyber-glow
Base tokens from README table.
Generate HTML+CSS using only those tokens.
Do not invent new colors or fonts.
```

The agent then reads `cyber-glow/DESIGN.md`, extracts its tokens, and writes constrained CSS that stays in family.

## Extending the Inventory

To add a new design system:

1. Create a subfolder named after the aesthetic (kebab-case)
2. Add a `DESIGN.md` following the Google `design.md` spec
3. Include a distinct color palette, typography choices, layout philosophy
4. Write a concise "Do's and Don'ts" section that acts as guardrails
5. Update this README's table with the new entry

### Naming Convention

- Folder: kebab-case, noun or adjective-noun (`neo-brutalist`, `digital-brutalism`, `swiss-modern`)
- `name:` in front matter matches folder name
- `description:` is one line, 8–12 words, captures the aesthetic in a phrase

## Token Export for Build Tools

A script can parse all `DESIGN.md` files and emit JSON for consumption by UI libraries:

```bash
# Example: extract tokens from all systems
find . -name DESIGN.md | while read f; do
  yq e '.colors' "$f"
done > tokens.json
```

Or use the official CLI:

```bash
npx @google/design.md export --format tailwind neumorphic/DESIGN.md > neumorphic.theme.json
```

##Philosophy

We treat visual design as **static data** — something that can be loaded, swapped, and composed at build time. The design system is not a suggestion; it is a compile-time contract. This conservation approach reduces output tokens dramatically because the agent references tokens by name rather than spelling them out repeatedly.

A 5:1 output-to-input ratio means: for every 100 tokens spent loading a system, you save ~500 tokens that would have been spent describing the same elements across multiple files.

## Related

- [Google Design.md Spec](https://github.com/google-labs-code/design.md) — canonical format definition
- `clinical-instrument/` and `dev-terminal/` — pre-spec reference designs (legacy format)
