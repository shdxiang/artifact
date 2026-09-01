# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

小木块/Littlewood (https://littlewood.io) — a static Chinese science site: counterintuitive questions explained with middle-school knowledge. Currently one article: "为什么 1 千克的薄层水，仍可能让挡板承受 1000 吨力？" (hydrostatic pressure paradox).

- Every page is one self-contained HTML file in `public/` with all CSS, JS, and SVG inline. No build step, no dependencies, no external fonts/CDN — keep it that way (hard requirement from the original brief).
- `public/index.html` — landing page (mascot logo in logo.svg/favicon.svg), cards linking to the question pages. A new article = a new `public/<english-slug>.html` + a card here.
- `public/hydrostatic-paradox.html` — the article.
- `wrangler.toml` — Cloudflare Worker static-assets config serving `public/`, custom domain littlewood.io.

## Commands

- Deploy: push to `main` — Cloudflare auto-deploys from the GitHub repo (`npx wrangler deploy` also works but needs auth)
- Preview locally: `npx wrangler dev` or just open the HTML file in a browser

## Conventions

- Keep kg (mass) vs kgf (force) strictly separated in copy — the hydrostatic article's whole point is not confusing them.
- Force-arrow colors are semantic and consistent across every figure: orange F原, purple F新, green gravity, teal normal force, blue pressure distribution. Don't reassign them.
- Chalkboard theme (2026-09): page ground is a green board (soft vignette, no frame); figures/cards are light "paper panels" pinned on it (soft shadow + tape corners on .figbox) and keep the original semantic colors. Anything drawn directly on the board is chalk-colored (text #f2efe4, yellow #e8c86a accents).
- Numbers on the page are labeled "概念示例" (conceptual examples); don't present them as measured values.

## Editorial principles (site review, 2026-09)

- Question site, not knowledge site: every article opens with an "impossible" question and answers it; knowledge is the tool, never the topic. Titles are questions, not textbook entries.
- Two-layer articles: 快速理解 first (core logic + the interactive demo), then a `.layer-break` divider ("已经理解了？…") before the deeper half.
- Figures carry the story: figures + captions alone should convey ~70% of an article; one figure answers exactly one question; formulas support figures, not prose.
- Interactives stay deliberately simple: 1–2 variables, purpose is understanding, not simulation.
- Keep the 图解 NN series numbering and English-slug URLs (e.g. /hydrostatic-paradox.html).
