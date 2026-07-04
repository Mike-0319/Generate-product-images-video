# Generate Amazon Product Images

English | [中文](README.zh-CN.md)

A small collection of reusable Codex skills for e-commerce product visuals.

## Skills

| Skill | Description |
| --- | --- |
| `product-shots-prompt-briefs` | Turn e-commerce image requests into structured prompt briefs and reusable prompt packs |

## Overview

`product-shots-prompt-briefs` is a prompt-only skill. It does not render images or call any image generation API. Instead, it converts a product image request into a compact brief plus reusable prompts that can be pasted into another image workflow.

It supports:

- Amazon main images
- Amazon secondary image sets
- Amazon A+ detail modules
- Ad creatives
- Social posts
- Prompt-pack-only requests

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

## Installation

Install the available skill from GitHub:

```bash
scripts/install-skill-from-github.py --repo Mike-0319/Generate-Amazon-product-images --path skills/product-shots-prompt-briefs
```

After installation, restart Codex so the skill can be discovered.

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
