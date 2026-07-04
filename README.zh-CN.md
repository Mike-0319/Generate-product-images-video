# Generate Amazon Product Images

[English](README.md) | 中文

这是一个用于公开分发 Codex skill 的仓库。

## Skills

- `product-shots-prompt-briefs`：把电商商品图需求整理成结构化 brief 和可复用提示词包

## 这个 Skill 做什么

- 把商品图需求转换成简洁的结构化 brief
- 生成可复用的 `master_prompt` 和 `negative_prompt`
- 支持 Amazon 主图、副图套图、A+ 详情模块、广告图、社媒图，以及仅输出提示词包
- 把产品还原要求与图片文案说明分开，方便后续复用

## 这个 Skill 不做什么

- 不直接生成图片
- 不上传素材
- 不调用 OpenAI、Midjourney 或其他生图 API

## 仓库结构

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

## 安装

如果你使用 Codex 的 skill 安装脚本，可以这样从 GitHub 安装：

```bash
scripts/install-skill-from-github.py --repo Mike-0319/Generate-Amazon-product-images --path skills/product-shots-prompt-briefs
```

安装后重启 Codex，让新 skill 被发现。

## 使用示例

```text
Use $product-shots-prompt-briefs to turn this Amazon main image request into a reusable prompt pack.
```

```text
Use $product-shots-prompt-briefs to create an Amazon A+ prompt pack for a skincare product with a premium minimalist style.
```

```text
Use $product-shots-prompt-briefs to create a social post prompt pack for a lifestyle product launch.
```

## 输出结构

这个 skill 默认会返回类似这样的结构：

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

## 编码说明

仓库文本文件建议保持 `UTF-8`，避免在公开分发和跨平台编辑时出现中文乱码。

## License

本仓库使用 MIT License，详见 `LICENSE`。
