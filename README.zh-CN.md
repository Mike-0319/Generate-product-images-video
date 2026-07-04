# Generate Amazon Product Images

[English](README.md) | 中文

这是一个面向电商商品视觉场景的 Codex skill 小合集。

## Skills

| Skill | 说明 |
| --- | --- |
| `product-shots-prompt-briefs` | 把电商商品图需求整理成结构化 brief 和可复用提示词包 |

## 概览

`product-shots-prompt-briefs` 是一个只产出提示词的 skill。它不直接生成图片，也不调用任何生图 API，而是把商品图需求转换成简洁的 brief 和可复用 prompt，方便粘贴到别的图像工作流里继续使用。

目前支持：

- Amazon 主图
- Amazon 副图套图
- Amazon A+ 详情模块
- 广告图
- 社媒图
- 仅输出提示词包的请求

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

从 GitHub 安装当前可用 skill：

```bash
scripts/install-skill-from-github.py --repo Mike-0319/Generate-Amazon-product-images --path skills/product-shots-prompt-briefs
```

安装后重启 Codex，让 skill 被正确发现。

## 示例请求

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

本仓库采用 MIT License，详见 `LICENSE`。
