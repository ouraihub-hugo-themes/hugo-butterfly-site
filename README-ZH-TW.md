# Hugo Butterfly 示例網站

[简体中文](README.md) | [English](README-EN.md) | 繁體中文

---
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
# 訪問 http://localhost:1313
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

### 📝 添加新文章

```bash
hugo new zh/posts/my-post.md     # 中文
hugo new en/posts/my-post.md     # 英文
hugo new zh-tw/posts/my-post.md  # 繁體
```

### 🔧 配置文件

所有配置位於 `config/_default/`：
- `hugo.toml` - Hugo 主配置
- `languages.toml` - 多語言設置
- `params.toml` - 主題參數

### 🌍 線上訪問

https://hugobutterfly.github.io

### 📖 部署指南

詳見 [README-EN.md](README-EN.md) (英文) | [README-ZH.md](README-ZH.md) (簡體)

### 📖 部署指南

詳見 [DEPLOYMENT-ZH-TW.md](DEPLOYMENT-ZH-TW.md)
