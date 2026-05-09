# blog-content

> 博客内容源仓库，与框架无关的纯 Markdown 内容

这个仓库只包含博客的**内容**（文章、关于页、静态资源），不包含任何主题、布局或框架特定的代码。

## 设计原则

- 只使用标准 Markdown 语法 + YAML frontmatter
- 不使用任何框架特定的内联组件（如 `<Component />`、`<script setup>`）
- frontmatter 字段保持一致

## 内容结构

```
.
├── posts/              # 博客文章
│   ├── *.md
│   └── ...
├── about.md            # 关于页
└── public/             # 静态资源
    ├── favicon.ico
    ├── favicon.png
    ├── beian.png
    ├── robots.txt
    └── og/             # OG 图片（由消费仓库构建时生成）
```

## Frontmatter 字段

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| title | string | 是 | 文章标题 |
| date | string | 是 | 发布日期 (YYYY-MM-DD) |
| tags | string[] | 否 | 标签列表 |
| description | string | 否 | 文章描述 |
| cover | string | 否 | 封面图片路径 |
| category | string | 否 | 文章分类 |
| draft | boolean | 否 | 是否为草稿（默认 false） |

## 消费仓库

- [blog-vitepress](https://github.com/noid-l/myls-top) - VitePress 版本
- blog-rspress - Rspress 版本（React）

## 更新工作流

写新文章 → 提交到本仓库 → 消费仓库通过 git submodule 获取最新内容
