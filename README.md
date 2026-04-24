# Design Inventory

A curated collection of design systems, aesthetics, and interface patterns used across projects. Structured like the skills system — each design is a self-contained directory with a `DESIGN.md` manifest and optional linked assets.

## Directory Structure

```
designs/
├── README.md
├── <design-name>/
│   ├── DESIGN.md          # Manifest with YAML frontmatter
│   ├── assets/            # Images, screenshots, reference photos
│   ├── templates/         # Reusable HTML/CSS/JS snippets
│   ├── css/               # Standalone stylesheets
│   └── references/        # External links, papers, inspirations
```

## Usage

Reference a design by path when starting a new project. Copy the `css/` or `templates/` contents as a starting scaffold. Update the DESIGN.md if the design evolves in implementation.

## Current Designs

| Design | Category | Description |
|--------|----------|-------------|
| [dev-terminal](dev-terminal/DESIGN.md) | dev-environment | Dark editor/terminal aesthetic — mechanical keyboard, syntax palette, ambient lighting |
| [clinical-instrument](clinical-instrument/DESIGN.md) | web-ui | Diagnostic instrument UI — high-density data, cyan/gold contract, hexagram visual encoding |

## Adding a Design

1. Create a new directory under `designs/`
2. Write `DESIGN.md` with YAML frontmatter
3. Populate `assets/` with reference images or screenshots
4. Add reusable code to `templates/` or `css/`
5. Update the table above
