# SVG Diagrams Skill

Use this skill when creating or revising inline SVG diagrams for website pages.

## Purpose

Inline SVG diagrams should explain concepts clearly, stay readable inside textbook pages, and work on both desktop and mobile screens.

## When to Use Inline SVG

Use inline SVG when the diagram is conceptual, text-heavy, or likely to need later editing.

Good fits:

- Entity-relation diagrams.
- Concept maps.
- Simple process or comparison diagrams.
- Small explanatory diagrams embedded inside examples.

Use raster images instead when the page needs photographic detail, texture, or a generated illustration.

## Typography

SVG text is scaled by the SVG `viewBox`, so CSS pixel sizes can appear smaller than normal HTML text after rendering.

Rules:

- Set `font-family: inherit` on the SVG.
- Compare rendered SVG text against nearby body text, not only the CSS value.
- Make SVG labels larger than they may seem necessary in code.
- For textbook diagrams, use strong label sizes and avoid tiny notes.
- Recheck after changing `viewBox`, SVG width, or minimum width.

Starting points:

```css
.diagram-label {
  font-size: 32px;
  font-weight: 800;
}

.diagram-note {
  font-size: 22px;
  font-weight: 700;
}
```

For smaller embedded diagrams:

```css
.relation-mini-label {
  font-size: 28px;
  font-weight: 800;
}

.relation-mini-note {
  font-size: 20px;
  font-weight: 700;
}
```

## Layout

- Keep diagrams visually simple: a few nodes, clear arrows, short labels.
- Use the same visual grammar across one page: similar node shapes, line weights, colors, and label hierarchy.
- Make node boxes wide enough for the actual text, especially English titles and longer translated titles.
- Avoid letting text touch the edge of a node box.
- Use concrete names when they teach better than abstract labels. For example, use translated book titles instead of only "English version" or "Japanese version" when appropriate.

## Mobile Behavior

Avoid letting SVG diagrams stretch the entire page horizontally.

Preferred pattern:

```css
.svg-figure {
  overflow-x: auto;
}

.svg-figure svg {
  width: 100%;
  min-width: 540px;
  height: auto;
  font-family: inherit;
}
```

Use a smaller `min-width` when the diagram can stay legible. Use a larger `min-width` only when labels would otherwise become unreadable.

Verify:

- Desktop view should not show a distracting horizontal scrollbar unless the diagram is intentionally wide.
- Mobile view may scroll inside the figure.
- The page itself should not horizontally overflow.

## Accessibility

For meaningful SVG diagrams:

- Add `role="img"`.
- Add a `<title>` and `<desc>`.
- Connect them with `aria-labelledby`.
- Give the surrounding `<figure>` an `aria-label` when helpful.

Example:

```html
<svg viewBox="0 0 760 360" role="img" aria-labelledby="diagram-title diagram-desc">
  <title id="diagram-title">Author and Works</title>
  <desc id="diagram-desc">The author entity links to several work entities.</desc>
</svg>
```

Use unique IDs for `<title>`, `<desc>`, markers, and arrowheads. Do not reuse marker IDs inside multiple SVGs on the same page.

## Verification Checklist

Before finishing:

- Refresh the local preview.
- Compare SVG text size with the surrounding HTML text.
- Check that no text overflows its node box.
- Check that arrows do not cover labels.
- Check desktop width for unnecessary internal scrollbars.
- Check mobile width for page-level horizontal overflow.
- Confirm the diagram appears in the correct reading order, immediately after the text or card it explains.
