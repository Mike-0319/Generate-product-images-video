---
name: amazon-prompt-recipes
description: Prompt recipes for Amazon main images, secondary images, and A+ modules, extracted and compressed from product-shots.
---

# Amazon Prompt Recipes

Use this file only when the request is for Amazon.

## Main Image Recipe

### Non-negotiable rules

- Pure white RGB(255,255,255) background
- Single product centered
- Product fills about 85% of frame
- Realistic studio product photo
- No added text
- No watermark
- No decorative graphics
- No extra props or packaging extras

### Base prompt

```text
Create an Amazon main product image for {product}. Match the reference image exactly in product shape, proportions, material, and details. Pure white RGB(255,255,255) background, centered composition, product fills about 85% of frame, even professional studio lighting, clean retail packshot, realistic photo style only. No extra objects, props, decorative graphics, watermark, text overlays, or packaging extras.
```

## Secondary Image Types

Use `1:1 1024x1024`. Keep the consistency clause:

```text
Match product color, material, and details from reference image exactly.
```

### Infographic

```text
Create an Amazon secondary infographic for {product}. Show the product clearly and add 4 to 6 feature callouts with clean hierarchy and high contrast text. Match product color, material, and details from reference image exactly.
```

### Multi-angle

```text
Create an Amazon multi-angle secondary image for {product}. Show front, side, and detail views in one clean composition. Match product color, material, and details from reference image exactly.
```

### Detail Shot

```text
Create an Amazon detail-shot secondary image for {product}. Use a macro crop to highlight material, texture, finish, or craftsmanship. Match product color, material, and details from reference image exactly.
```

### Lifestyle

```text
Create an Amazon lifestyle secondary image for {product}. Show the product in a realistic use scenario for the target buyer. Match product color, material, and details from reference image exactly.
```

### Variants

```text
Create an Amazon variants secondary image for {product}. Show all key colors, sizes, or versions in a uniform arrangement. Match product color, material, and details from reference image exactly.
```

## A+ Module Recipes

### Hero Banner

- Size: `2388x1024`
- Aspect: `21:9`
- Safe area: keep critical content inside inner 90%

```text
Create an Amazon A+ hero banner for {product}. Use the product as the visual anchor, keep the product appearance consistent with the reference image, and place all critical text and product silhouettes inside the inner 90% safe area. Premium brand storytelling, clean hierarchy, strong first impression.
```

### Selling Points Module

- Size: `1536x1024`
- Aspect: `3:2`

```text
Create an Amazon A+ selling-points module for {product}. Show 3 to 4 clear benefits with a clean grid, readable hierarchy, and product-consistent visuals. Keep all critical content inside the inner 90% safe area.
```

### Technology Module

```text
Create an Amazon A+ technology module for {product}. Highlight the core ingredient, mechanism, or differentiator with a clean premium layout. Keep all critical content inside the inner 90% safe area.
```

### Data Module

```text
Create an Amazon A+ data module for {product}. Focus on evidence, comparison, or measurable proof points with readable visual hierarchy. Keep all critical content inside the inner 90% safe area.
```

### How-to-Use Module

```text
Create an Amazon A+ how-to-use module for {product}. Show 3 to 5 clear steps with simple iconography and concise copy zones. Keep all critical content inside the inner 90% safe area.
```

## Recommended A+ Sequence

For a compact detail-page prompt pack, prefer:

1. Hero Banner
2. Selling Points
3. Technology
4. How to Use
