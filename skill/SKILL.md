---
name: warm-editorial-ui
description: Create warm editorial, paper-like UI for self-contained HTML artifacts, AI reports, research briefings, implementation plans, code review summaries, and prompt-to-result documents. Use when the user asks for Warm Editorial UI, editorial technical artifact styling, ivory/paper report UI, Codex-like warm report styling, or wants AI/Codex output presented as a polished browser-readable HTML artifact.
---

# Warm Editorial UI

## Goal

Create a quiet, readable, browser-native artifact that feels like an editorial technical report: warm ivory background, white paper surfaces, thin borders, serif headings, mono metadata, and restrained clay accents.

Use this style for dense AI output, planning reports, unknown/risk reviews, implementation briefs, research summaries, and prompt-to-result artifacts. Do not turn it into a generic SaaS landing page or dashboard unless the user explicitly asks for that surface.

## Quick Start

- For standalone HTML, start from `assets/warm-editorial-template.html`.
- For project UI work, copy the tokens from `assets/tokens.css` and component patterns from `assets/components.css` into the existing styling system.
- Read `references/style-guide.md` before substantial implementation or when translating the style into a React/Vue/Svelte app.
- For SVG-led cards, icons, thumbnails, or report diagrams, read `references/svg-style-guide.md` and reuse patterns from `assets/svg-style-harness.html`.
- For broad SVG generation tasks, inspect `assets/svg-sample-types.html`; it contains 10 reusable SVG archetypes with intent notes.

## Composition

Use this default structure:

1. Page head: mono eyebrow, serif title, short supporting sentence only if needed.
2. Prompt card: quote-like user prompt or task request, with optional copy action.
3. Divider: mono label separating input from output.
4. Artifact frame: browser-like report container with metadata bar.
5. Content blocks: comparison cells, stat strip, insight/blindspot cards, code or action rows.
6. Final card: final prompt, decision, or next action.

Keep the first viewport as one calm document composition. Avoid marketing hero clutter, large decorative imagery, pill clusters, heavy stat rows, and multiple competing text blocks.

For galleries or card indexes, use a compact grid of paper cards with inline SVG thumbnails. The thumbnail should be informative, not decorative: show the artifact type, workflow, diagram, or source structure in the SVG itself.

## Visual Rules

- Use `#FAF9F5` ivory for the page background and `#FFFFFF` paper for content surfaces.
- Use `#141413` slate for primary text and `#D97757` clay only for thin lines, labels, warnings, and small emphasis.
- Use serif type for H1/H2/card titles, sans for body copy, and mono for labels, file paths, metadata, code, and controls.
- For Korean serif display text, keep line-height generous: about 1.16+ for desktop hero text, 1.24+ on mobile, 1.42+ for prompt quotes, and 1.28+ for card titles.
- Keep long Korean prompt quotes and final synthesis headlines one visual step below hero/section scale: prompt quote around 28px desktop max with loose line-height, final synthesis around 40px desktop max and 25px mobile when the sentence wraps.
- Prefer 1.5px warm gray borders over shadows. Use shadows only on hover or final emphasis.
- Keep radius modest: 8-14px.
- Use generous outer whitespace and dense but readable inner report structure.
- Put clear air between mono labels and serif display headings. In final cards or synthesis blocks, use about 18-24px below labels like `SYNTHESIS` before the H2.
- Make hover motion subtle: translate up 2-3px with a soft shadow.
- Draw SVG assets with warm fills, round strokes, restrained primitive geometry, and visible hover states. Use `references/svg-style-guide.md` as the source of truth. Thumbnail SVGs should occupy the available visual field, not sit small inside the tile.

## Avoid

- Purple/blue default SaaS styling, dark-mode bias, neon, glassmorphism, and heavy gradients.
- Rounded marketing cards in the hero.
- Decorative badges, floating stickers, and disconnected callouts.
- All-sans typography that loses the editorial report character.
- Clay accent as a large button fill or broad background color.
- Hiding the prompt or final instruction inside plain body text when the artifact is prompt-driven.
- Generic stock icons or abstract SVG blobs that do not describe the content.

## Verification

When building an HTML or frontend surface, render it in a browser when possible. Check desktop and mobile screenshots for:

- Ivory background, paper surfaces, serif headings, mono metadata, and clay accent visibility.
- Text fitting without overlap or clipping.
- Artifact frame and cards remaining readable on narrow screens.
- Buttons and copy controls staying stable without layout shift.
- Inline SVGs using the warm token palette, fixed viewBox geometry, clear stroke hierarchy, and no clipped labels or symbols.
- Hover states changing both card depth and at least one SVG detail when interaction is part of the reference style.

For SVG-heavy work, run a screenshot pass against the delivered HTML and compare it to `assets/svg-style-harness.html` for density, palette, stroke weight, and hover behavior.
