# Generate Product Images Video

[English](README.md) | 中文

这是一个可复用的 Codex skill，用来把电商商品图需求转换成结构化 brief 和可复用提示词包。

## Skill

| Skill | 说明 |
| --- | --- |
| `product-shots-prompt-briefs` | 把商品视觉需求转换成只产出提示词的 brief，适用于 Amazon 商品图、A+ 模块、广告图和社媒图 |

## 概览

`product-shots-prompt-briefs` 是一个只产出提示词的 skill。它不直接生成图片，也不调用任何生图 API，而是把商品需求整理成简洁 brief 和可复用 prompt，方便粘贴到别的图像工作流里继续使用。

目前支持：

- Amazon 主图
- Amazon 副图套图
- Amazon A+ 详情模块
- 广告图
- 社媒图
- 仅输出提示词包的请求

## 仓库结构

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

## 安装

这个仓库已经调整为“根目录单 skill”结构，方便 CC Switch 这类工具更稳定地识别。

如果你使用支持“仓库根目录 skill”的 GitHub 安装方式，可以直接从这里安装：

```text
https://github.com/Mike-0319/Generate-product-images-video
```

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
