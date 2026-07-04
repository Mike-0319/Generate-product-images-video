# Generate Product Images Video

English | [中文](README.zh-CN.md)

A reusable Codex skill for turning e-commerce product image requests into structured prompt briefs and reusable prompt packs.

## Skill

| Skill | Description |
| --- | --- |
| `product-shots-prompt-briefs` | Convert product visual requests into prompt-only briefs for Amazon images, A+ modules, ads, and social posts |

## Overview

`product-shots-prompt-briefs` is a prompt-only skill. It does not render images or call any image generation API. Instead, it converts a product request into a compact brief plus reusable prompts that can be pasted into another image workflow.

It supports:

- Amazon main images
- Amazon secondary image sets
- Amazon A+ detail modules
- Ad creatives
- Social posts
- Prompt-pack-only requests

## Repository Layout

```text
SKILL.md
agents/
  openai.yaml
references/
  core-brief-template.md
  prompt-patches.md
  amazon-prompt-recipes.md
README.md
README.zh-CN.md
LICENSE
```

## Installation

This repository is structured as a root-level single-skill repository so tools such as CC Switch can discover it more reliably.

If you use a GitHub skill installer that supports repository-root skills, install from:

```text
https://github.com/Mike-0319/Generate-product-images-video
```

## Example Requests

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

## License

This repository is released under the MIT License. See `LICENSE` for details.
