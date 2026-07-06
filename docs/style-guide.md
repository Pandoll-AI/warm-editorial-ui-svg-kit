# Warm Editorial UI Style Guide

## Identity

Warm Editorial UI is closest to a Codex-like warm editorial report surface with a technical artifact frame. It should feel like a polished document made for serious reading, not like a marketing landing page.

Core qualities:

- Warm ivory page, white paper surfaces.
- Thin warm-gray borders instead of heavy depth.
- Serif headings for editorial authority.
- Mono labels and metadata for technical clarity.
- Muted clay accent for lines, warnings, labels, and emphasis.
- Prompt-to-output structure when the artifact is generated from an AI instruction.

## Tokens

Use these values directly for standalone HTML. Translate them into the host design system for app work.

```css
:root {
  --ue-ivory: #FAF9F5;
  --ue-paper: #FFFFFF;
  --ue-slate: #141413;
  --ue-clay: #D97757;
  --ue-clay-d: #B85C3E;
  --ue-oat: #E3DACC;
  --ue-olive: #788C5D;
  --ue-g100: #F0EEE6;
  --ue-g200: #E6E3DA;
  --ue-g300: #D1CFC5;
  --ue-g500: #87867F;
  --ue-g700: #3D3D3A;

  --ue-serif: ui-serif, Georgia, "Times New Roman", Times, serif;
  --ue-sans: system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  --ue-mono: ui-monospace, "SF Mono", Menlo, Monaco, Consolas, monospace;

  --ue-wrap: 980px;
  --ue-wrap-wide: 1120px;
  --ue-pad-x: 24px;
  --ue-radius-sm: 8px;
  --ue-radius-md: 10px;
  --ue-radius-lg: 14px;
  --ue-border: 1.5px solid var(--ue-g300);
  --ue-border-soft: 1.5px solid var(--ue-g200);
  --ue-shadow-hover: 0 10px 30px rgba(20, 20, 19, 0.10);
  --ue-shadow-final: 0 10px 28px rgba(20, 20, 19, 0.07);
}
```

## Typography

- H1: serif, medium weight, 32-46px for reports, up to 62px only for a true landing hero.
- H2: serif, around 27px.
- Card title: serif, 18-20px.
- Body: sans, 14-16.5px.
- Eyebrow, labels, code, metadata, file paths: mono, 10-12.5px, uppercase where useful.

For Korean content, keep body text in a readable sans. Serif headings can work, but avoid fragile decorative Hangul display treatment unless the project already has a suitable Korean serif font.

## Layout

- Use max-width 980px for focused reports.
- Use max-width 1120px for galleries or previews.
- Use 24-32px side padding.
- Use 56-80px top spacing for the page head.
- Use 44-72px between major sections.
- Collapse two-column comparisons to one column below about 640px.

## Components

### Eyebrow

Small mono uppercase label with a short clay line before it. Use it to declare the document context.

### Prompt Card

White paper card with a mono label and an italic serif prompt quote. Include a compact copy button when useful.

### Divider

Centered mono label with horizontal lines on both sides. Use it to separate "input" from "output" or one report phase from another.

### Artifact Frame

Browser-like frame with:

- White paper container.
- Thin border.
- Warm-gray top bar.
- Three subtle dots.
- Mono file/context metadata.
- Generous internal padding.

### Comparison Cells

Use two cells for "asked vs actual", "before vs after", "assumption vs reality", or "request vs implementation implication". Highlight the risk/actual side with a clay border and pale clay background.

### Stat Strip

Use sparingly for report metadata: file counts, risk counts, assumptions, scan counts, or completion status. Keep it mono and compact.

### Insight Cards

Use for risks, blindspots, unknowns, review findings, or decisions. Each card should contain one idea, a compact label, a title, short explanation, and optional action row.

### Final Card

Use for the final instruction, improved prompt, decision, or next action. Make it feel conclusive with a darker border or subtle shadow.

## Interaction

- Hover cards: `transform: translateY(-3px)` and a soft shadow.
- Transitions: 120-150ms.
- Copy success: olive background with paper text.
- Links: subtle underline with offset, clay on hover.

## Content Guidance

Lead with the user request or decision context, then show the generated artifact. This style works because it makes the relationship between prompt and output visible.

Prefer crisp labels:

- `THE PROMPT`
- `WHAT THE AGENT PRODUCED`
- `THE BLINDSPOTS`
- `ACTION`
- `WHY IT BITES`
- `FINAL PROMPT`

Avoid long subtitle copy under every title. Use supporting text only when it materially improves comprehension.

## Implementation Notes

- For single-file delivery, inline CSS from `assets/tokens.css` and `assets/components.css`.
- For a framework app, preserve the app's routing/build conventions and translate the visual tokens into existing CSS variables or theme primitives.
- Keep cards for real information containers. Do not wrap every section in a card by default.
- Do not add external dependencies only for this style.
- If using the provided template, replace sample copy and metadata before delivery.
