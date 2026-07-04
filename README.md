# Generate Amazon Product Images

English | [中文](README.zh-CN.md)

This repository contains a reusable Codex skill collection.

## Skills

- `product-shots-prompt-briefs`: Turn e-commerce image requests into structured prompt briefs and reusable prompt packs

The skill turns e-commerce image requests into structured prompt briefs and reusable prompt packs. It is prompt-only by design and does not call any image generation API.

## What This Skill Does

- Converts product image requests into a compact brief
- Produces a reusable `master_prompt` and `negative_prompt`
- Supports Amazon main images, secondary image sets, A+ detail modules, ad creatives, social posts, and prompt-pack-only requests
- Keeps product fidelity instructions separate from text overlay guidance

## What This Skill Does Not Do

- It does not render images
- It does not upload assets
- It does not call OpenAI, Midjourney, or any other image API

## Repository Layout

```text
skills/
  product-shots-prompt-briefs/
    SKILL.md
    agents/
      openai.yaml
    references/
      core-brief-template.md
      prompt-patches.md
      amazon-prompt-recipes.md
```

## Install

If you use the Codex skill installer helper, install this skill from GitHub with:

```bash
scripts/install-skill-from-github.py --repo Mike-0319/Generate-Amazon-product-images --path skills/product-shots-prompt-briefs
```

After installation, restart Codex so the new skill is discovered.

## Usage

Example requests:

```text
Use $product-shots-prompt-briefs to turn this Amazon main image request into a reusable prompt pack.
```

```text
Use $product-shots-prompt-briefs to create an Amazon A+ prompt pack for a skincare product with a premium minimalist style.
```

```text
Use $product-shots-prompt-briefs to create a social post prompt pack for a lifestyle product launch.
```

## Output Shape

The skill is designed to return a structure like this:

```text
Brief summary:
- Platform:
- Deliverable:
- Topic:
- Audience:
- Style:

Prompt pack:
- Master prompt:
- Negative prompt:
- Aspect ratio:
- Size or module:
- Reference image required:
- Copy notes:
```

## Encoding Note

This repository includes text files that should be handled carefully to avoid mojibake. Keep the original encoding of existing files unless you intentionally perform a verified encoding migration.

## License

This repository is released under the MIT License. See `LICENSE` for details.
