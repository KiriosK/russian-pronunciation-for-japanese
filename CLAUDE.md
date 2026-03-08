# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS site — a Russian pronunciation guide for Japanese speakers. No build step, no framework, no JavaScript.

## Structure

- `index.html` — main page with navigation cards to all topic pages
- `style.css` — single shared stylesheet for all pages
- `*.html` — topic pages: `zh-z.html`, `r-l.html`, `f-v.html`, `ts-shch.html`, `vowels.html`, `soft.html`

## Conventions

**Fonts**
- UI / Japanese text: `Noto Sans JP`
- Headings: `Shippori Mincho`
- Russian text with stress marks (combining U+0301): `Noto Serif` — fixes combining acute accent rendering over wrong character in Noto Sans JP

**Russian stress marks**
Use Unicode combining acute (U+0301) directly on the vowel, e.g. `о́`, `а́`. Never use separate HTML or CSS hacks for this.

**CSS variables** (defined in `:root`)
- Colors: `--accent-red`, `--accent-blue`, `--accent-green`, `--accent-purple`, `--accent-orange`
- Apply to heading borders and highlight spans via modifier classes: `.blue`, `.green`, etc.

**Highlight spans** for Russian letters: `<span class="hl-red">`, `hl-blue`, `hl-green`, `hl-purple`, `hl-orange`

**Nav active state**: add `class="nav-link active"` to the link matching the current page.

## Adding a New Page

1. Copy an existing topic page (e.g. `vowels.html`) as a template
2. Add `<link rel="stylesheet" href="style.css">` (root-relative, no subdirectory)
3. Add a nav link in every page's `<nav>` block
4. Add a `.sound-card` entry on `index.html`
