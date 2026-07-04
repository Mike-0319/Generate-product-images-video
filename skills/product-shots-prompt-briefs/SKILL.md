---
name: product-shots-prompt-briefs
description: Build prompt-only briefs for product visuals by distilling the product-shots ecosystem into reusable image-generation prompts. Use when Codex should turn a product request, product photo, or e-commerce visual task into structured prompts without calling any image API. Covers Amazon main images, Amazon A+ detail modules, secondary-image plans, platform and industry prompt patches, negative constraints, and prompt packs that can be pasted into another image tool or workflow.
---

# Product Shots Prompt Briefs

## Overview

Turn the original product-shots prompt logic into a prompt library. Produce a structured brief and one or more ready-to-use prompts. Do not call image generation tools from this skill.

中文说明：
把原本 `product-shots` 体系里分散的提示词逻辑整理成一个“提示词库”型 skill。这个 skill 只负责产出结构化 brief 和可直接复用的提示词，不负责调用任何生图接口。

## Workflow

1. Identify the deliverable type.
   Map the request to one of: `main-image`, `secondary-set`, `aplus-detail`, `ad-creative`, `social-post`, or `prompt-pack-only`.

2. Build a minimal brief.
   Read [references/core-brief-template.md](references/core-brief-template.md) and fill the fields that are known from the user request or source image.

3. Inject prompt patches.
   Read [references/prompt-patches.md](references/prompt-patches.md) and append:
   - the platform patch
   - the industry patch when a match is obvious
   - the style modifier when requested
   - the unified negative constraints

4. Load deliverable-specific prompt recipes only when needed.
   - For Amazon main images, secondary images, and A+ modules, read [references/amazon-prompt-recipes.md](references/amazon-prompt-recipes.md).
   - For other platforms, stay prompt-only and use the core brief plus prompt patches.

5. Return a prompt pack instead of rendering.
   Always output:
   - `brief_summary`
   - `master_prompt`
   - `negative_prompt`
   - `recommended_aspect_ratio`
   - `recommended_size_or_module`
   - `reference_image_required`
   - `copy_notes` when text should appear on the design

中文说明：

1. 先判断用户要的是什么类型的图。
   把需求归类到主图、副图套图、Amazon A+ 详情图、广告图、社媒图，或者仅输出提示词包。

2. 生成最小化 brief。
   先读取 `references/core-brief-template.md`，把平台、主题、素材、风格这些已知信息填进去。

3. 注入提示词补丁。
   读取 `references/prompt-patches.md`，按需拼接平台 patch、行业 patch、风格 modifier 和统一负面约束。

4. 只在需要时读取更细的提示词配方。
   如果是 Amazon 主图、副图或 A+，再读取 `references/amazon-prompt-recipes.md`；如果不是，就停留在通用 prompt brief 层。

5. 最后输出 prompt pack，而不是直接生成图片。
   结果应该是“可以直接复制到别的图像模型里使用”的提示词集合。

## Output Contract

Use this exact shape unless the user asks for something different:

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

中文说明：
默认输出格式固定成两段：
- `Brief summary`：概括平台、交付物、主题、受众、风格
- `Prompt pack`：给出主提示词、负面提示词、推荐比例、推荐尺寸或模块、是否必须参考图、以及图上文案说明

这样做的目的，是让这份 skill 的输出既能给人看，也能直接喂给下游模型或别的自动化流程。

## Rules

- Keep the reply in the user's language.
- Prefer prompt packs over prose explanations.
- Preserve product fidelity when a reference image exists by including: `Match product color, material, and details from reference image exactly`.
- When the request is for Amazon main images, obey the strict white-background and no-overlay rules from the Amazon reference file.
- When the request needs text on the image, keep the visual prompt and text copy guidance separate so the prompt can be reused across different image models.
- If routing is ambiguous, choose the closest deliverable and state the assumption in one short line.

中文说明：
- 始终使用用户当前的语言回复。
- 优先输出可复用的提示词包，不要把结果写成很长的纯解释性文字。
- 如果用户提供了参考图，提示词里要明确要求“产品外观与参考图一致”。
- 如果目标是 Amazon 主图，必须遵守白底、单品、无额外叠字和无装饰元素这些硬规则。
- 如果图片里需要文字，要把“视觉提示词”和“文案说明”拆开，这样后面切换不同模型时更稳。
- 如果路由不完全明确，选最接近的交付类型，并用一句短说明把假设讲清楚。
