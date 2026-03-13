# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page educational/marketing site about garage door torsion spring physics and safety. Built for A Plus Garage Doors as a "science of" content piece that doubles as a call-to-action for professional spring replacement services.

## Architecture

This is a **single-file static site** — all HTML, CSS, and JavaScript live in `garage-springs.html`. No build tools, no dependencies, no server required. Open the file directly in a browser.

### Structure within `garage-springs.html`

- **CSS** (lines 8–615): CSS custom properties in `:root` for theming (dark palette with danger/energy/accent colors). All styles are vanilla CSS — no preprocessor.
- **HTML** (lines 617–942): Five content sections (Mechanics, Numbers, Energy Comparison, Interactive Simulator, Danger Zone) plus hero and footer CTA. Sections use `fade-up` class for scroll-reveal animations.
- **JavaScript** (lines 944–1038): Two features:
  - `IntersectionObserver` for scroll-triggered fade-in and energy bar animations
  - Winding Simulator: slider-driven spring visualization with real-time SVG path generation and physics readouts (torque, energy, PSI, danger level)

### Key Design Patterns

- **Fonts**: Bebas Neue (headings), Source Sans 3 (body), JetBrains Mono (labels/data) — loaded from Google Fonts CDN
- **SVGs are inline**: Hero spring diagram and anatomy diagram are hand-coded SVG, not external assets
- **Simulator spring coil** is procedurally generated via JS — the `updateSim()` function builds SVG path data based on slider position with non-linear force curves

## Development

Open `garage-springs.html` in a browser. No build step needed.

```bash
open garage-springs.html          # macOS
```
