---
name: dev-terminal
category: dev-environment
date: 2026-04-24
source_image: assets/reference-keyboard-editor.jpg
---

# Dev Terminal Aesthetic

Personal development environment design language extracted from reference photography. The governing principle is **functional density** — every pixel earns its place, color is sparse and semantically loaded, and the boundary between hardware and software interface is intentionally blurred.

## Reference Context

The source image shows a split mechanical keyboard held in both hands, with a digital overlay of a code editor (likely Neovim) displaying `flake.nix`. The keyboard is black with white/gray keycaps and a red coiled cable. Ambient lighting is deep blue/purple.

## Color System

| Token | Value | Usage |
|-------|-------|-------|
| `editor-bg` | `#1e1e1e` | Editor background — deeper than UI chrome |
| `ui-bg` | `#252526` | Sidebar, status bar, panels |
| `border` | `#3e3e42` | Subtle dividers between panes |
| `text` | `#d4d4d4` | Primary code text |
| `text-dim` | `#808080` | Comments, inactive line numbers |
| `keyword` | `#569cd6` | Keywords, control flow (`let`, `in`, `if`) |
| `string` | `#ce9178` | Strings, paths — warm terracotta |
| `function` | `#dcdcaa` | Functions, builtins — muted gold |
| `type` | `#4ec9b0` | Types, builtins — teal |
| `accent-red` | `#d73a49` | Errors, git deletions, cable accent |
| `accent-green` | `#6a9955` | Git additions, success states |
| `status-blue` | `#007acc` | Status bar active file, branch info |

## Typography

- **Primary**: JetBrains Mono or SF Mono — monospaced, highly legible at small sizes
- **Size scale**: 13px editor body, 11px status bar, 14px headers
- **Line height**: 1.5 for code, 1.2 for UI chrome
- **Weight**: 400 regular, 700 bold for keywords only

## Hardware Affordances

The design treats the keyboard as part of the interface:
- Keycap colors (white/gray on black) mirror the editor's text-on-dark contract
- The red coiled cable is an intentional accent — it introduces warmth into an otherwise cool palette
- Split layout implies the user values ergonomics and modularity

## UI Chrome Rules

- **Status bar** is always visible: file name, git branch, modification count (`+18 ~3`), position (`52:29`), language mode
- **Sidebars** collapse to icons — text labels appear on hover only
- **Borders** are 1px hairlines at `#3e3e42` — never shadows, never rounded corners on panels
- **Cursor**: block cursor in insert mode, thin line in normal mode

## Ambient Lighting

Deep blue/purple bias lighting (≈ 450nm) reduces eye strain in dark rooms. The light reflects off the keyboard plate and creates a halo around the hands. This is not decorative — it serves a physiological function and visually frames the input device.

## Interaction Patterns

- **Modal editing** (Vim/Neovim) — interface state is explicit, not implicit
- **Keyboard-first** — all actions have keybindings; mouse is secondary
- **Git integration** — diff signs in gutter, branch in status bar, commit hash inline
- **Fuzzy finding** — quick-open files with partial string matching, no tree browsing

## Nix Expression Context

The reference code is Nix — a functional, declarative configuration language. The syntax highlighting rules above are optimized for this: blue keywords (`let`, `in`, `with`), teal builtins (`builtins`, `pkgs`), terracotta strings (`"aarch64-darwin"`), muted gold attributes (`system.defaults`).

## Adaptation Notes

When applying this design to web UIs or dashboards:
- Keep the editor-bg/ui-bg/border three-layer depth
- Use the syntax palette for semantic data encoding (blue = system/config, green = success/path, red = error/blocker)
- Do not add gradients, glow, or blur effects — these break the flat, dense aesthetic
- Respect the 1.5 line-height minimum; cramming text tighter signals "I don't expect you to read this"

## Assets

- `assets/reference-keyboard-editor.jpg` — Source photograph
