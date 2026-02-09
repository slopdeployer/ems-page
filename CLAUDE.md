# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page event website for **EMS – European Mining Summit**, a Bitcoin mining and energy industry conference. Built with Vite + vanilla HTML/CSS/JS (no frameworks).

## Commands

- `npm run dev` — Start Vite dev server (hot reload)
- `npm run build` — Production build to `dist/`
- `npm run preview` — Serve production build locally

No linter, formatter, or test runner is configured.

## Architecture

This is a single-page static site with three source files:

- `index.html` — Entire page structure (nav, hero, about, speakers, schedule, waitlist form, sponsor form, footer)
- `style.css` — All styles, linked directly from HTML
- `main.js` — Navbar scroll behaviour, mobile menu toggle, scroll-reveal animations via IntersectionObserver, form submit handlers (currently client-side only, logs to console)
- `favicon.svg` — SVG favicon

Vite is used purely as a dev server and bundler — no plugins, no config file (`vite.config.js`), no preprocessors.

## Conventions

- **CSS naming**: BEM methodology — block, block__element, block--modifier (e.g. `.hero__title`, `.btn--accent`, `.schedule__type--keynote`)
- **HTML**: Semantic elements (`<nav>`, `<header>`, `<section>`, `<footer>`, `<form>`) with descriptive IDs for scroll targets
- **Responsive**: Mobile-first design. Base styles target mobile; `@media (max-width: 768px)` overrides handle layout changes for smaller screens
- **CSS custom properties**: All colours, spacing, and typography tokens are defined as `--variables` in `:root`
- **Fonts**: Inter (body) + JetBrains Mono (monospace accents) via Google Fonts

## Design Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--navy` | `#002F6C` | Dominant brand colour, dark sections |
| `--white` | `#FFFFFF` | Text on dark, light sections |
| `--green` | `#00C853` | Accent colour, CTAs, highlights |
| `--teal` | `#00BFA5` | Secondary accent, glow effects |
| `--font` | Inter | Body text |
| `--mono` | JetBrains Mono | Tags, timestamps, badges |

The visual identity emphasises green energy, Nordic nature, sustainability, and high tech.
