# Warm Editorial SVG Style Guide

Use this guide when Warm Editorial UI needs inline SVG cards, thumbnails, workflow diagrams, browser frames, icons, or visual summaries. The goal is not generic illustration. The SVG should look like a small editorial artifact: paper, ink, typed labels, restrained geometry, and a few content-specific marks.

## Source Pattern

The bundled harness was extracted from the HTML Effectiveness unknowns reference pages and rebuilt as a reusable local style:

- `assets/svg-style-harness.html`: reference harness for card thumbnails, hover behavior, and state styling.
- `assets/svg-sample-types.html`: 10 applied SVG archetypes with intent notes.
- `assets/svg-variant-gallery.html`: alternative scene compositions for stress testing.

Use the assets as visual references, not as fixed templates. Preserve the grammar while redrawing the subject.

## Core SVG Grammar

Use small, crisp shapes:

- `rect`, `line`, `circle`, `path`, and occasional `polyline`.
- Rounded rectangle corners from `2` to `7`.
- Stroke widths from `1.6` to `3`, with `2.2` to `2.6` as the default.
- `stroke-linecap="round"` and `stroke-linejoin="round"` for drawn marks.
- Sparse text labels only when they remain legible at the rendered size.

Avoid:

- Complex path-heavy illustration that cannot be inspected quickly.
- Stock icon silhouettes.
- Decorative blobs, gradients, mesh backgrounds, or fake 3D.
- Excessive tiny labels that collapse into noise.

## Thumbnail System

For index cards and preview tiles:

```html
<svg class="thumb-svg" viewBox="0 0 120 80" role="img" aria-label="...">
  ...
</svg>
```

Recommended sizing:

- SVG viewBox: `0 0 120 80`.
- Thumbnail container height: about `132px`.
- Card radius: `8px` to `12px`.
- SVG inner margin: `8` to `12` viewBox units.
- Main object footprint: 70-85% of the viewBox.

The SVG should still read when reduced to a card thumbnail. Prefer one dominant object plus two or three supporting marks.

## Token Classes

Use classes for repeated warm-editorial marks:

```css
.st { stroke: var(--ue-slate); stroke-width: 2.4; fill: none; stroke-linecap: round; stroke-linejoin: round; }
.fl { fill: var(--ue-paper); stroke: var(--ue-slate); stroke-width: 2.4; }
.cl { fill: var(--ue-clay); }
.ol { fill: var(--ue-olive); }
.oa { fill: var(--ue-oat); }
.sl { fill: var(--ue-slate); }
.wh { fill: var(--ue-paper); }
.ln { stroke: var(--ue-g500); stroke-width: 1.8; fill: none; stroke-linecap: round; }
.lc { stroke: var(--ue-clay); stroke-width: 2.2; fill: none; stroke-linecap: round; stroke-linejoin: round; }
.lo { stroke: var(--ue-olive); stroke-width: 2.2; fill: none; stroke-linecap: round; stroke-linejoin: round; }
.da { stroke-dasharray: 4 4; }
```

Use semantic class combinations:

- `.fl` for paper panels, file cards, modal shells, browser windows.
- `.st` for primary outlines and drawn connectors.
- `.ln` for secondary separators, metadata lines, and inactive traces.
- `.lc` for active path, warning path, or selected trace.
- `.lo` for confirmation, completion, or resolved state.
- `.da` for unknown, speculative, queued, or scanned paths.

## Palette Rules

Use the Warm Editorial UI palette:

- Page/thumbnail background: `#FAF9F5`.
- Paper surfaces: `#FFFFFF`.
- Primary ink: `#141413`.
- Clay accent: `#D97757`.
- Olive state: `#788C5D`.
- Oat fill: `#E3DACC`.
- Warm gray separators: `#D1CFC5`, `#87867F`.

Keep clay as an accent. It should identify state, action, or risk, not flood the whole drawing.

## Hover Grammar

When the original reference style matters, implement card and SVG hover together:

```css
.card {
  transition: transform 140ms ease, box-shadow 140ms ease, border-color 140ms ease;
}

.card:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(20, 20, 19, 0.10);
  border-color: var(--ue-slate);
}

.card:hover .thumb {
  background: var(--ue-oat);
}

.card:hover .fl {
  fill: var(--ue-g100);
}

.card:hover .accent-move {
  transform: translateX(3px);
}
```

Hover should change one small semantic detail in the SVG:

- Arrow advances.
- Active trace brightens.
- Selected card fills with oat.
- File tab shifts.
- Status dot changes from clay to olive.

Avoid unrelated wobble or decorative motion.

## Scene SVGs

For larger report scenes, keep the same grammar but use a larger viewBox:

- `viewBox="0 0 640 360"` or `0 0 960 540`.
- Hard-coded fills are acceptable when the scene is standalone, but keep them within the same palette.
- Use a browser or report frame as the outer object.
- Use 3-5 large regions instead of many tiny widgets.
- Preserve whitespace; do not fill every corner.

Use `preserveAspectRatio="xMidYMid slice"` for full-bleed hero-like scenes only when cropping is intentional.

## Archetypes

Use these archetypes from `assets/svg-sample-types.html`:

- Document inspection: stacked paper sheets, highlighted unknowns, marginal notes.
- Workflow path: nodes, dashed unknown path, active clay route.
- Quality gate: checklist, screenshot frame, status dots.
- Source comparison: two paper panels, one emphasized difference.
- Agent delegation: central brief, branch lines, small reviewer cards.
- Code artifact: file frame, lines, callout trace.
- Risk map: grid or matrix with one clay risk area.
- Deck/storyline: slide stack, title rhythm, small chart marks.
- Article transformation: source page, summary cards, output frame.
- SVG system kit: swatches, stroke samples, reusable primitive set.

## Quality Checklist

Before delivering SVG-heavy Warm Editorial UI, verify:

- Every inline SVG has a fixed viewBox and accessible label.
- The SVG remains legible at its final rendered size.
- Shapes use the warm token palette and do not drift into generic blue/purple SaaS styling.
- Stroke hierarchy is clear: primary ink, secondary gray, accent clay/olive.
- The visual explains the content type or workflow, not just decoration.
- Hover behavior changes both the card and one SVG detail when hover is expected.
- No text, path, or icon is clipped in desktop or mobile screenshots.
- The delivered HTML renders in a browser with non-empty screenshots.

If the SVG fails the screenshot check, reduce detail before adding more styling.
