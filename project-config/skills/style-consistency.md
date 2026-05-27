# Style Consistency Skill

Use this skill when creating or reviewing website pages, components, unit layouts, diagrams, or visual explanations.

## Purpose

Keep the electronic textbook professional, concise, readable, and consistent across separate work sessions.

## Audience Fit

Design for:

- First-year university students.
- General adult learners.
- Classroom projection.
- Mobile browsing.

## Writing Style

- Professional and concise.
- Explain terms clearly without sounding informal.
- Avoid unnecessary jargon.
- Keep paragraphs focused.
- Use consistent terms across pages and units.
- Do not use corner quotation marks in generated site text.
- Do not add bold emphasis in generated prose.

## Typography

- Keep font sizes consistent across similar elements.
- Use a predictable heading scale.
- Avoid oversized text except for true page titles.
- Ensure body text remains comfortable on mobile.
- Ensure projected text is readable from a classroom setting.
- Do not use viewport-width font scaling for normal interface text.

## Layout

- Prioritize reading flow and navigation.
- Avoid dense blocks of text without spacing or structure.
- Use diagrams, tables, or examples when they clarify difficult concepts.
- Check that text does not overlap or crowd other elements.
- Make page layouts work on both desktop and phone widths.

## Cards And Comparisons

- Use cards for concept examples, repeated items, and compact comparisons.
- For Chinese prose with more than one short line of explanation, prefer horizontal cards: a small icon area on the left and text on the right.
- Avoid three-column cards when each card contains long Chinese paragraphs; they become cramped on desktop and stack poorly on mobile.
- Use consistent icon logic across the same group of cards. For example, all `實體` cards should use the same icon metaphor.
- Use cards to replace wide comparison tables when the content is conceptual rather than numeric.
- For two-method comparisons, prefer two large side-by-side panels, one per method, with short internal points. On mobile, stack the panels vertically.
- Do not include an extra left-hand "scenario" column in comparison layouts unless it adds necessary meaning; unnecessary scenario labels can distract from the comparison.
- Keep card body text close to normal body text size. Avoid making card text noticeably smaller than the surrounding explanation.
- For icon cards, keep icons simple and semantic:
  - Rule/model concepts can use a rule book or document icon.
  - System or platform concepts can use a monitor, network, or database icon.
  - Entity concepts should use a generic object/node icon rather than a person icon unless the entity is specifically a person.

## Image Captions and Sources

- Center image captions under the image.
- Use two caption lines when an image has both a descriptive caption and a source.
- First line: a short descriptive caption ending with a full-width period.
- Second line: begin with `圖片來源：`, then name the source, and preserve the source link when available.
- Keep source links as ordinary text links, such as `原始 PDF`.
- Use this HTML pattern:

```html
<figcaption>
  中文編目的卡片目錄。<br>
  圖片來源：國家圖書館，圖書資料編目與書目資源，<a href="...">原始 PDF</a>
</figcaption>
```

## Projection Considerations

- Use sufficient contrast.
- Avoid tiny captions as the only explanation.
- Keep key concepts visible and legible.
- Avoid layouts that require horizontal scrolling.

## Mobile Considerations

- Ensure headings wrap cleanly.
- Keep navigation usable with touch.
- Avoid wide tables unless they are adapted for small screens.
- Confirm images and diagrams scale within the viewport.

## Review Checklist

- Are similar headings and labels using similar sizes?
- Is the page readable on a phone?
- Would the main content remain legible when projected?
- Are terms used consistently?
- Does the page feel like an electronic textbook rather than a marketing page?
