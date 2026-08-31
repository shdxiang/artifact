# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A static single-page science explainer (Chinese): "为什么 1 千克的薄层水，仍可能让挡板承受 1000 吨力？" — hydrostatic pressure paradox for lay readers.

- `public/hydrostatic-paradox.html` — the entire site: one self-contained HTML file with all CSS, JS, and SVG inline. No build step, no dependencies, no external fonts/CDN — keep it that way (hard requirement from the original brief).
- `public/index.html` — site landing page ("小木块/Littlewood" — counterintuitive science explained with middle-school knowledge; mascot logo in logo.svg/favicon.svg), links to the question pages.
- `wrangler.toml` — Cloudflare Worker static-assets config serving `public/`.

## Commands

- Deploy: `npx wrangler deploy` (needs `npx wrangler login` once)
- Preview locally: `npx wrangler dev` or just open `public/hydrostatic-paradox.html` in a browser

## Conventions

- All content edits happen inside the one HTML file; keep kg (mass) vs kgf (force) strictly separated in copy — the page's whole point is not confusing them.
- Force-arrow colors are semantic and consistent across every figure: orange F原, purple F新, green gravity, teal normal force, blue pressure distribution. Don't reassign them.
- Numbers on the page are labeled "概念示例" (conceptual examples); don't present them as measured values.

## Editorial principles (site review, 2026-09)

- Question site, not knowledge site: every article opens with an "impossible" question and answers it; knowledge is the tool, never the topic. Titles are questions, not textbook entries.
- Two-layer articles: 快速理解 first (core logic + the interactive demo), then a `.layer-break` divider ("已经理解了？…") before the deeper half.
- Figures carry the story: figures + captions alone should convey ~70% of an article; one figure answers exactly one question; formulas support figures, not prose.
- Interactives stay deliberately simple: 1–2 variables, purpose is understanding, not simulation.
- Keep the 图解 NN series numbering and English-slug URLs (e.g. /hydrostatic-paradox.html).
