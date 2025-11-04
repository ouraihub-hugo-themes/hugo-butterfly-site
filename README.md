# Hugo Butterfly 示例网站

**简体中文** | [English](README-EN.md) | [繁體中文](README-ZH-TW.md)

---

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

###  pnpm 脚本说明

| 命令 | 说明 | 用途 |
|------|------|------|
| `pnpm install` | 安装依赖 | 必须先运行 |
| `pnpm run build` | 生产构建+搜索索引 | 部署到生产环境 |
| `pnpm run build:dev` | 开发构建+搜索索引 | 本地测试搜索 |
| `pnpm run dev` | 快速开发服务器 | 快速开发（无搜索） |
| `pnpm run preview` | 预览构建结果 | 查看生产版本效果 |
| `pnpm run clean` | 清理构建产物 | 清理 public/ 和缓存 |

###  搜索功能部署

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
- 自动执行: Hugo构建  Pagefind索引生成  部署到GitHub Pages
- 搜索索引会自动在部署时生成

###  添加新文章

```bash
hugo new zh/posts/my-post.md     # 中文
hugo new en/posts/my-post.md     # 英文
hugo new zh-tw/posts/my-post.md  # 繁体
```

###  配置文件

所有配置位于 `config/_default/`：
- `hugo.toml` - Hugo 主配置
- `languages.toml` - 多语言设置
- `params.toml` - 主题参数

###  在线访问

https://hugobutterfly.github.io

###  文档

- [部署指南](DEPLOYMENT-ZH.md)
- [主题文档](https://github.com/ouraihub-hugo-themes/hugo-butterfly)
