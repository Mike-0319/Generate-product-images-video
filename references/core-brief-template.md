---
name: core-brief-template
description: Minimal prompt-brief template distilled from product-shots. Use for any prompt-only output before adding platform, industry, or Amazon-specific recipes.
---

# Core Brief Template

Use this file first. Keep the brief small and only populate fields the request actually supports.

## Template

```text
Confirmed:
- Platform: {platform}
- Deliverable: {deliverable}
- Format and dimensions: {format_dimensions}
- Content topic: {topic}
- Visual assets: {assets}
- Optimization target: {optimization}
- Target audience: {audience}
- Style direction: {style}
- Variant count: {count}

Visual DNA to inject:
- Platform patch: {platform_patch}
- Industry patch: {industry_patch}
- Style modifier: {style_modifier}

Negative constraints:
- {negative_constraints}
```

## Completeness Rule

Proceed when these are known or can be inferred safely:

- platform
- deliverable
- topic
- visual assets

Everything else can fall back to defaults:

- optimization target: `engagement`
- target audience: `general`
- style direction: `modern`
- variant count: `1`

## Deliverable Mapping

- `main-image`: single e-commerce product hero image
- `secondary-set`: conversion-oriented carousel images
- `aplus-detail`: Amazon A+ module prompts
- `ad-creative`: paid social or display visual
- `social-post`: organic feed, story, reel, or carousel post
- `prompt-pack-only`: no platform-specific route, just reusable prompts
