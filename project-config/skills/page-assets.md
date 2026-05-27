# Page Assets Skill

Use this skill whenever the user asks to save, create, generate, edit, or organize images and other visual assets for a specific website page or unit.

## Purpose

Keep page-specific images close to the page that uses them, instead of collecting all images in one global folder.

## Default Rule

Store page-specific assets inside that page's own `assets/` folder.

Examples:

```text
site/knowledge-graph/
├─ index.html
└─ assets/
   └─ diagram-01.png
```

```text
site/books/book-01/unit-01/
├─ index.html
└─ assets/
   └─ hero.png
```

## Shared Assets

Use `site/shared/assets/` only for assets reused across multiple pages, such as logos, icons, default covers, or global UI graphics.

## Workflow

When saving an image for a page:

1. Identify the target page or unit.
2. Locate that page's folder under `site/`.
3. If the page folder exists, check for an `assets/` folder inside it.
4. If `assets/` does not exist, create it.
5. Save the image into that `assets/` folder.
6. Use relative paths from the page, such as:

```html
<img src="./assets/diagram-01.png" alt="">
```

## Page Image Presentation

When adding a meaningful bitmap image to a textbook page:

- Place the image in a `<figure>`.
- Add an `alt` attribute that describes the instructional content of the visible image.
- Add a centered `<figcaption>` that explains the instructional meaning of the image.
- If the image has an external or traceable source, add a second caption line beginning with `圖片來源：` and preserve the source link when available.
- If the image is user-provided and the user does not want a source line, omit the source line rather than inventing one.
- Make the image clickable to open a larger view when the image contains details that may be hard to inspect in the normal page flow.

Use this pattern for a clickable page image:

```html
<figure class="source-figure">
  <button class="image-zoom-button" type="button" aria-label="放大檢視圖示" data-image-modal-open data-modal-src="./assets/example.png" data-modal-alt="Descriptive alt text.">
    <img src="./assets/example.png" alt="Descriptive alt text.">
  </button>
  <figcaption>
    圖片說明文字。<br>
    圖片來源：來源名稱，<a href="...">原始連結</a>
  </figcaption>
</figure>
```

Use one shared modal per page for these image buttons. The modal should:

- Show the full image, not the cropped display window.
- Close with a visible close button, backdrop click, and the `Escape` key.
- Return keyboard focus to the image button that opened it.
- Use `cursor: zoom-in` on the clickable image and accessible labels on the open and close buttons.
- Support multiple images on the same page by reading `data-modal-src` and `data-modal-alt` from the clicked button.
- Leave the displayed crop non-destructive: if the page shows a cropped image, the modal should still open the full asset.

The recommended page-level modal pattern is:

```html
<div class="image-modal" role="dialog" aria-modal="true" aria-label="圖片放大檢視" data-image-modal hidden>
  <div class="image-modal-content">
    <button class="image-modal-close" type="button" aria-label="關閉大圖" data-image-modal-close>×</button>
    <img src="" alt="" data-image-modal-img>
  </div>
</div>
```

Use a small script that:

- Finds all `[data-image-modal-open]` buttons.
- Copies each clicked button's `data-modal-src` and `data-modal-alt` into `[data-image-modal-img]`.
- Opens the modal by removing `hidden` and adding the open class.
- Clears the modal image `src` when closing.
- Restores focus to the button that opened the modal.

## Caption And Source Decisions

Write captions for instructional meaning, not file provenance or editing operations.

- If the image explains a concept, the first caption line should state what the learner should see in the image.
- If there is an external or stable source URL, add a second line beginning with `圖片來源：`.
- If a user supplies an image for the page and explicitly says not to include a source, do not add `圖片來源：使用者提供`.
- If a user supplies an image but also gives an external source URL, use the external source URL in the source line.
- Do not mention visual crop operations in the caption.
- Keep caption punctuation consistent: use a full-width period when the caption is a full sentence; omit it for a short label if the user requests that exact label.

## Paired Images

Use a paired image layout when two figures are meant to be compared directly, such as model versions, before/after diagrams, or two views of the same concept.

- Place the two `<figure>` elements inside a wrapper such as `.figure-pair`.
- On desktop, use two columns and keep both images on the same horizontal row.
- Start with equal columns only when the two images have similar aspect ratios.
- When aspect ratios differ, adjust the column ratio to improve legibility, such as `45% / 55%`, instead of forcing both images into identical visual width.
- Use a shared fixed or clamped image-frame height on desktop, and set images to `object-fit: contain` so diagrams are not cropped.
- Avoid using `overflow: hidden` in a way that permanently hides important diagram content; if a frame crops or cuts off a diagram, increase the frame height or rebalance column widths.
- Keep each image independently clickable through the shared page modal, using its own `data-modal-src` and `data-modal-alt`.
- On mobile, stack paired images vertically and let each image return to natural width and height.
- Give each image its own caption and source line when sources differ.

## If the Page Folder Does Not Exist

If the target page folder does not exist yet:

- Ask whether to create the page folder, unless the user's request clearly implies creating that page.
- If creating the folder, use:

```text
site/<page-slug>/
├─ index.html
└─ assets/
```

## Naming

Use concise lowercase filenames with hyphens.

Good:

```text
hero.png
concept-map.png
linked-data-example.png
diagram-01.png
```

Avoid:

```text
IMG_1234.png
final-final.png
image.png
```

## Source and Generated Image Separation

- Original user-provided source images may remain in `sources/` if they are source material.
- AI-generated drafts or experiments may go in `generated/`.
- Only selected images used by the website should be copied or saved into the relevant `site/<page>/assets/` folder.

## Publishing

Images inside `site/` are publishable website assets. Before committing, follow:

- `project-config/skills/publishing-checklist.md`
