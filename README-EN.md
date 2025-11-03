# Hugo Butterfly Demo Site

[简体中文](README.md) | English | [繁體中文](README-ZH-TW.md)

---

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

### 📝 Create New Posts

```bash
hugo new zh/posts/my-post.md     # Chinese
hugo new en/posts/my-post.md     # English
hugo new zh-tw/posts/my-post.md  # Traditional Chinese
```

### 🔧 Configuration Files

All config in `config/_default/`:
- `hugo.toml` - Hugo main config
- `languages.toml` - Language settings
- `params.toml` - Theme parameters

### 🌍 Live Demo

https://hugobutterfly.github.io

### 📖 Deployment Guide

See [DEPLOYMENT-EN.md](DEPLOYMENT-EN.md)

