# Hugo Butterfly 示例网站

[English](#english-version) | [简体中文](#中文版本) | [繁體中文](#繁体中文版本)

---

## 中文版本

### 📖 项目介绍

这是 **Hugo Butterfly 主题** 的完整示例网站，展示了如何使用Hugo和Butterfly主题构建一个支持多语言的现代化博客网站。

### ✨ 主要特性

- **三语言支持**: 中文 (zh)、英文 (en)、繁体中文 (zh-tw)
- **响应式设计**: 完美适配各种设备
- **主题切换**: 8种主题颜色方案可选
- **搜索功能**: 内置Pagefind搜索
- **代码高亮**: 支持多种编程语言
- **社交分享**: 集成社交媒体分享
- **评论系统**: 支持Giscus、Gitalk等多种评论方案

### 📁 项目结构

```
hugo-butterfly-site/
├── config/              # Hugo配置
│   └── _default/
│       ├── hugo.toml           # 主Hugo配置
│       ├── languages.toml       # 多语言配置
│       ├── params.toml          # 主题参数
│       ├── params.zh.toml       # 中文参数
│       ├── params.en.toml       # 英文参数
│       └── params.zh-tw.toml    # 繁体参数
├── content/             # 网站内容
│   ├── zh/              # 中文内容
│   ├── en/              # 英文内容
│   └── zh-tw/           # 繁体内容
├── i18n/                # 国际化翻译
│   ├── zh.toml
│   ├── en.toml
│   └── zh-tw.toml
├── themes/              # Hugo主题
│   └── hugo-butterfly/  # 主题子模块
├── static/              # 静态文件
├── layouts/             # 自定义布局
├── .github/workflows/   # GitHub Actions
│   └── deploy.yml       # 自动部署工作流
└── DEPLOYMENT-*.md      # 部署文档

```

### 🚀 快速开始

#### 本地开发

```bash
# 克隆仓库（包含子模块）
git clone --recurse-submodules https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git
cd hugo-butterfly-site

# 运行Hugo开发服务器
hugo server

# 访问 http://localhost:1313
```

#### 构建生产版本

```bash
# 构建静态网站
hugo --minify

# 生成的网站在 public/ 目录中
```

### 🔧 配置指南

#### 修改网站信息

编辑 `config/_default/params.toml`:

```toml
# 网站标题
title = "Hugo Butterfly"

# 网站描述
description = "A beautiful Hugo theme"

# 作者信息
[author]
name = "Your Name"
```

#### 添加新文章

创建新文章最简单的方法：

```bash
hugo new zh/posts/my-first-post.md
# 或
hugo new en/posts/my-first-post.md
hugo new zh-tw/posts/my-first-post.md
```

然后编辑生成的Markdown文件。

#### 配置社交媒体

编辑 `config/_default/params.toml` 中的 `[[social]]` 部分：

```toml
[[social]]
icon = 'fab fa-github'
name = 'GitHub'
url = 'https://github.com/your-username'
```

### 🎨 主题选项

修改 `config/_default/params.toml` 中的主题相关设置：

```toml
# 启用暗黑模式
dark = true

# 默认主题（如果实现了主题切换）
defaultTheme = "sapphire"
```

### 📚 内容管理

#### 文章前置信息 (Front Matter)

```markdown
---
title: "我的第一篇文章"
date: 2025-01-01T12:00:00Z
updated: 2025-01-02T12:00:00Z
draft: false
categories:
  - 技术
tags:
  - Hugo
  - Butterfly
---

# 文章内容从这里开始
```

#### 支持的Markdown特性

- 代码块高亮
- 表格
- 脚注
- 任务列表
- 删除线
- 上标/下标
- 数学公式 (可选)
- Mermaid图表 (可选)

### 🌐 多语言配置

本网站支持三种语言：

| 代码 | 语言 | 权重 |
|------|------|------|
| zh | 中文 | 1 (默认) |
| en | 英文 | 2 |
| zh-tw | 繁体中文 | 3 |

修改 `config/_default/languages.toml` 来调整语言设置。

### 🔄 更新主题

主题通过Git子模块管理，更新方法：

```bash
# 进入主题目录
cd themes/hugo-butterfly

# 拉取最新版本
git pull origin master

# 返回到项目根目录
cd ../..

# 提交更新
git add themes/hugo-butterfly
git commit -m "Update hugo-butterfly theme"
git push
```

### 📖 更多文档

- `DEPLOYMENT-PLAN.md` - 部署规划
- `DEPLOYMENT-VERIFICATION.md` - 部署验证清单
- `GITHUB-DEPLOYMENT-CHECKLIST.md` - GitHub部署检查清单

### 🌍 在线访问

构建后的示例网站托管在GitHub Pages：

👉 **https://hugobutterfly.github.io**

### 📝 许可证

本项目采用 MIT 许可证。详见 LICENSE 文件。

### 💬 反馈与支持

如有问题或建议，请：
- 提交Issue
- 发起Pull Request
- 联系项目维护者

---

## English Version

### 📖 Introduction

This is a complete example website for the **Hugo Butterfly theme**, demonstrating how to build a modern multilingual blog using Hugo and the Butterfly theme.

### ✨ Features

- **Multilingual Support**: Chinese (zh), English (en), Traditional Chinese (zh-tw)
- **Responsive Design**: Perfect on all devices
- **Theme Switching**: 8 color theme options
- **Search**: Built-in Pagefind search
- **Code Highlighting**: Support for multiple programming languages
- **Social Sharing**: Integrated social media sharing
- **Comments**: Support for Giscus, Gitalk, and more

### 🚀 Quick Start

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git
cd hugo-butterfly-site

# Run development server
hugo server
```

Visit `http://localhost:1313`

### 📚 Documentation

- `DEPLOYMENT-PLAN.md` - Deployment planning
- `DEPLOYMENT-VERIFICATION.md` - Deployment verification
- `GITHUB-DEPLOYMENT-CHECKLIST.md` - GitHub deployment checklist

### 🌍 Live Demo

👉 **https://hugobutterfly.github.io**

---

## 繁体中文版本

### 📖 專案介紹

這是 **Hugo Butterfly 主題** 的完整示例網站，展示如何使用Hugo和Butterfly主題建立一個支持多語言的現代化部落格網站。

### ✨ 主要特性

- **三語言支持**: 中文 (zh)、英文 (en)、繁體中文 (zh-tw)
- **響應式設計**: 完美適配各種設備
- **主題切換**: 8種主題顏色方案可選
- **搜索功能**: 內置Pagefind搜索
- **代碼高亮**: 支持多種編程語言
- **社交分享**: 集成社交媒體分享
- **評論系統**: 支持Giscus、Gitalk等多種評論方案

### 🚀 快速開始

```bash
# 克隆倉庫（包含子模組）
git clone --recurse-submodules https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git
cd hugo-butterfly-site

# 運行Hugo開發服務器
hugo server
```

訪問 `http://localhost:1313`

### 📚 文檔

- `DEPLOYMENT-PLAN.md` - 部署規劃
- `DEPLOYMENT-VERIFICATION.md` - 部署驗證
- `GITHUB-DEPLOYMENT-CHECKLIST.md` - GitHub部署檢查清單

### 🌍 線上訪問

👉 **https://hugobutterfly.github.io**

