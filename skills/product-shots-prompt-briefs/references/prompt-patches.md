---
name: prompt-patches
description: Compact platform, industry, style, and negative prompt patches extracted from product-shots for prompt-only reuse.
---

# Prompt Patches

Append only the patches needed for the current request.

## Platform Patches

### Amazon

- Format: `1:1 1024x1024` for main and secondary images
- A+ Hero: `21:9 2388x1024`
- A+ Standard Module: `3:2 1536x1024`
- Patch: `studio product photography, pure white background, even soft lighting, e-commerce listing aesthetic`

### Shopify or Independent Site

- Format: `1080x1080` or `1080x1350`
- Patch: `lifestyle product photography, brand-aligned color palette, premium retail aesthetic`

### Instagram

- Format: `4:5` or `9:16`
- Patch: `modern aesthetic, lifestyle photography, warm tones, center focus`

### TikTok

- Format: `9:16`
- Patch: `authentic, natural lighting, slightly imperfect, UGC style`

### LinkedIn

- Format: `1.91:1`
- Patch: `corporate quality, authoritative, business-focused, clean`

## Industry Patches

### Beauty

- Patch: `high-end minimalist chic, soft diffused lighting, premium matte texture, neutral tones`

### Fashion

- Patch: `editorial fashion photography, muted color palette, sharp focus on fabric, sophisticated pose`

### Tech

- Patch: `Apple-style minimalist design, clean white space, sharp geometric lines, soft shadows`

### Lifestyle

- Patch: `authentic natural sunlight, warm candid moments, soft focus background`

### Travel

- Patch: `cinematic landscape, golden hour lighting, vast perspective`

### Food

- Patch: `mouth-watering photography, macro texture, steam and freshness, soft top-down lighting`

### Fitness

- Patch: `dynamic action shot, high intensity, strong shadows`

## Style Modifiers

- `minimalist`: `minimalist, clean, simple, negative space`
- `high-impact`: `high impact, bold, vibrant, dramatic`

## Unified Negative Prompt

Always append:

```text
social media UI, screenshot, watermark, messy background, distorted text, phone frame, app interface
```

If the platform forbids text overlays, append:

```text
text overlay, words, letters, typography
```
