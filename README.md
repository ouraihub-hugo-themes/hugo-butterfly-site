# Hugo Butterfly 示例网站

[English](#english-version) | [简体中文](#中文版本) | [繁體中文](#繁体中文版本)

---

## 中文版本

### 📖 项目介绍

这是 **Hugo Butterfly 主题** 的完整示例网站，包含中文、英文、繁体中文三种语言支持。

### ✨ 主要特性

- **三语言支持**: 中文、英文、繁体中文
- **响应式设计**: 完美适配各种设备
- **8种主题**: 冷色和暖色主题可选
- **搜索功能**: Pagefind 全文搜索
- **代码高亮**: 多种编程语言支持

### 🚀 快速开始

#### 本地开发（无搜索）
```bash
hugo server
# 访问 http://localhost:1313
```

#### 完整构建（含搜索索引）
```bash
pnpm install
pnpm run build
pnpm run preview
```

#### 开发构建（含搜索，较快）
```bash
pnpm install
pnpm run build:dev
pnpm run preview
```

### 📚 pnpm 脚本说明

| 命令 | 说明 | 用途 |
|------|------|------|
| `pnpm install` | 安装依赖 | 必须先运行 |
| `pnpm run build` | 生产构建+搜索索引 | 部署到生产环境 |
| `pnpm run build:dev` | 开发构建+搜索索引 | 本地测试搜索 |
| `pnpm run dev` | 快速开发服务器 | 快速开发（无搜索） |
| `pnpm run preview` | 预览构建结果 | 查看生产版本效果 |
| `pnpm run clean` | 清理构建产物 | 清理 public/ 和缓存 |

### 🔍 搜索功能部署

**本地测试搜索：**
```bash
pnpm install
pnpm run build:dev
pnpm run preview
# 访问 http://localhost:1313 并测试搜索
```

**验证搜索生成成功：**
```bash
ls -la public/_pagefind/
# 应该看到 pagefind.js, pagefind.json, ui.js, ui.css
```

**GitHub Actions 自动部署：**
- 工作流文件: `.github/workflows/deploy.yml`
- 自动执行: Hugo构建 → Pagefind索引生成 → 部署到GitHub Pages
- 搜索索引会自动在部署时生成

### 📝 添加新文章

```bash
hugo new zh/posts/my-post.md     # 中文
hugo new en/posts/my-post.md     # 英文
hugo new zh-tw/posts/my-post.md  # 繁体
```

### 🔧 配置文件

所有配置位于 `config/_default/`：
- `hugo.toml` - Hugo 主配置
- `languages.toml` - 多语言设置
- `params.toml` - 主题参数

### 🌍 在线访问

https://hugobutterfly.github.io

---

## English Version

### 📖 Introduction

This is a complete example website for the **Hugo Butterfly theme** with support for Chinese, English, and Traditional Chinese.

### ✨ Features

- **Multilingual**: Chinese, English, Traditional Chinese
- **Responsive**: Works on all devices
- **8 Themes**: Cool and warm color schemes
- **Search**: Pagefind full-text search
- **Code Highlight**: Multiple programming languages

### 🚀 Quick Start

#### Development mode (no search)
```bash
hugo server
```

#### Full build (with search)
```bash
pnpm install
pnpm run build
pnpm run preview
```

#### Dev build (with search, faster)
```bash
pnpm install
pnpm run build:dev
pnpm run preview
```

### 📚 pnpm Scripts

| Command | Description | Usage |
|---------|-------------|-------|
| `pnpm install` | Install dependencies | Must run first |
| `pnpm run build` | Production build + search | Deploy to production |
| `pnpm run build:dev` | Dev build + search | Test search locally |
| `pnpm run dev` | Quick dev server | Fast development |
| `pnpm run preview` | Preview build result | Check production look |
| `pnpm run clean` | Clean artifacts | Clean public/ & cache |

### 🔍 Search Deployment

**Test search locally:**
```bash
pnpm install
pnpm run build:dev
pnpm run preview
# Visit http://localhost:1313 and test search
```

**Verify search generation:**
```bash
ls -la public/_pagefind/
# Should see: pagefind.js, pagefind.json, ui.js, ui.css
```

**GitHub Actions auto-deployment:**
- Workflow: `.github/workflows/deploy.yml`
- Auto-runs: Hugo build → Pagefind indexing → Deploy
- Search index generated automatically during deployment

### 🌍 Live Demo

https://hugobutterfly.github.io

---

## 繁體中文版本

### 📖 專案介紹

這是 **Hugo Butterfly 主題** 的完整示例網站，支持中文、英文、繁體中文三種語言。

### ✨ 主要特性

- **三語言支持**: 中文、英文、繁體中文
- **響應式設計**: 完美適配各種設備
- **8種主題**: 冷色和暖色主題可選
- **搜索功能**: Pagefind 全文搜索
- **代碼高亮**: 多種編程語言支持

### 🚀 快速開始

#### 開發模式（無搜索）
```bash
hugo server
```

#### 完整構建（含搜索）
```bash
pnpm install
pnpm run build
pnpm run preview
```

#### 開發構建（含搜索，較快）
```bash
pnpm install
pnpm run build:dev
pnpm run preview
```

### 📚 pnpm 指令

| 指令 | 說明 | 用途 |
|------|------|------|
| `pnpm install` | 安裝依賴 | 必須先運行 |
| `pnpm run build` | 生產構建+搜索索引 | 部署到生產環境 |
| `pnpm run build:dev` | 開發構建+搜索索引 | 本地測試搜索 |
| `pnpm run dev` | 快速開發服務器 | 快速開發 |
| `pnpm run preview` | 預覽構建結果 | 查看生產版本 |
| `pnpm run clean` | 清理構建產物 | 清理 public/ |

### 🔍 搜索部署

**本地測試搜索：**
```bash
pnpm install
pnpm run build:dev
pnpm run preview
```

**驗證搜索生成：**
```bash
ls -la public/_pagefind/
```

### 🌍 線上訪問

https://hugobutterfly.github.io
