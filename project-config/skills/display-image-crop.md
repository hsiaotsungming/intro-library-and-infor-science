# Display Image Crop Skill

Use this skill when the user asks to crop an image as it appears on a website page, hide extra whitespace around an image, adjust the visible image area, or preserve the original image file while changing only the displayed crop.

## Purpose

Use non-destructive CSS cropping for page images unless the user explicitly asks to permanently edit the image file.

This keeps the source asset intact while allowing the page to show only the useful visual area.

## Default Rule

Wrap the image in a crop container and hide overflow.

Put visual framing on the container, not the image:

- `overflow: hidden`
- `aspect-ratio`
- `border`
- `border-radius`
- `background`

Move the image inside the crop window with `transform: translate(...)`, or use `object-fit` and `object-position` when that fits the layout better.

## Workflow

1. Confirm whether the user wants display-only cropping or permanent image editing.
2. If the request is about a website page, prefer display-only cropping.
3. Store the image in the page's own `assets/` folder, following `project-config/skills/page-assets.md`.
4. Add a figure-specific class so the crop does not affect other images.
5. Wrap the image in a dedicated crop container.
6. Set the crop container's visible window with `aspect-ratio`.
7. Offset the image with `transform`.
8. Keep or add a useful caption when the image supports explanation.
9. Verify that the cropped image, alt text, and caption still describe the visible content.

## Top And Bottom Crop Pattern

For a request such as "hide the top one quarter and bottom one quarter", the visible height is half of the original image height.

If the original image is `1456 x 1088`, the visible crop window is:

```text
1456 x 544
```

Use:

```css
aspect-ratio: 1456 / 544;
transform: translateY(-25%);
```

HTML pattern:

```html
<figure class="source-figure example-crop-figure">
  <div class="image-crop">
    <img src="./assets/example.png" alt="Descriptive alt text.">
  </div>
  <figcaption>
    A concise caption explaining what the image illustrates.
  </figcaption>
</figure>
```

CSS pattern:

```css
.example-crop-figure .image-crop {
  width: 100%;
  max-width: 760px;
  aspect-ratio: 1456 / 544;
  overflow: hidden;
  border: 1px solid var(--line);
  border-radius: 8px;
  background: #ffffff;
}

.example-crop-figure .image-crop img {
  display: block;
  width: 100%;
  max-width: none;
  border: 0;
  border-radius: 0;
  transform: translateY(-25%);
}
```

## General Formula

- Hide top fraction `T` and bottom fraction `B`.
- Visible height fraction is `1 - T - B`.
- Container aspect ratio is `imageWidth / (imageHeight * visibleHeightFraction)`.
- Translate the image by `-T` on the vertical axis.
- For left and right cropping, use the same method with width and `translateX(...)`.

## Caption Guidance

The caption should explain the instructional meaning of the image, not the crop operation itself.

For source images, follow `project-config/skills/style-consistency.md` for caption and source formatting.
