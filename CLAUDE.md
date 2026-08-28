# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

博客内容源仓库，与框架无关的纯 Markdown 内容。被 `blog-vitepress` 和 `blog-rspress` 通过 git submodule 消费。

## Content Structure

```
posts/              # 博客文章（*.md）
about.md            # 关于页
public/             # 静态资源
    ├── favicon.ico
    ├── favicon.png
    ├── beian.png
    └── robots.txt
```

## Writing Guidelines

- 只使用标准 Markdown 语法 + YAML frontmatter
- 不使用任何框架特定的内联组件（如 `<Component />`、`<script setup>`）
- 不使用 Obsidian 特有语法（`[[wikilinks]]`、`> [!note]` callout 等）

## Frontmatter Fields

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| title | string | 是 | 文章标题 |
| date | string | 是 | 发布日期 (YYYY-MM-DD) |
| tags | string[] | 否 | 标签列表 |
| description | string | 否 | 文章描述 |
| cover | string | 否 | 封面图片路径 |
| category | string | 否 | 文章分类 |
| draft | boolean | 否 | 是否为草稿（默认 false）

## Adding a New Post

在 `posts/` 下创建 `YYYY-MM-DD-slug.md`：

```yaml
---
title: 文章标题
date: YYYY-MM-DD
tags:
  - tag1
  - tag2
description: 文章摘要
category: 分类
draft: false
---

文章内容...
```

## Content Privacy Rules

创建或编辑博客文章时，避免包含：

- 真实姓名、公司名、客户名（如"惠农"等业务相关名称）
- 本地文件路径（如 `/Users/xxx`）
- API Key、Token、密码等凭证
- 代理地址（如 `127.0.0.1:7890`）和内部环境变量配置
- 内部培训内容、工作量评估、费用预算等公司内部信息

从 Obsidian 笔记转为博客文章时，应移除上述内容并确保文章适合公开发布。
