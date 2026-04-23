# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS/JS website for **野心会 (Yashinkai)** — a Japanese community primarily for occupational therapists (作業療法士) seeking personal and professional growth. No build system or package manager is used.

## Development

There is no build step. Open any `.html` file directly in a browser, or serve locally with:

```bash
# Python (if available)
python -m http.server 8000

# Node.js (if available)
npx serve .
```

No tests, no linting setup.

## Architecture

All pages are self-contained HTML files with **inline CSS and JS** (no external stylesheets or script files):

| File | Purpose |
|---|---|
| `index.html` | Landing page — hero, about, news, FAQ |
| `activities.html` | Event archive (第1〜4回) |
| `members.html` | Team member profiles |
| `blog.html` | Blog/news |
| `contact.html` | Contact form |
| `join.html` | Membership guide |
| `links.html` | External link directory |

Event media and transcripts live in numbered subdirectories: `第1回/`, `第2回/`, `第3回/`, `第4回/`.

## Design System

CSS custom properties are defined per-page in `<style>` blocks. Key values to keep consistent across pages:

- **Accent red:** `#D4380D`
- **Gold:** `#C49A00`
- **Background:** beige/cream tones
- **Fonts:** Hiragino Kaku Gothic ProN, Noto Sans JP (Japanese)
- **Layout:** CSS Grid + Flexbox; mobile breakpoint via media queries

## Common JS Patterns

Each page includes:
- Page-load progress/fade animation
- Mobile hamburger navigation toggle
- Scroll-triggered fade-in for `.fade-in` elements

When adding new pages, replicate these patterns from an existing page rather than creating separate JS files.
