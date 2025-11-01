# Hugo Butterfly 示例网站部署规划

## 📋 部署架构

```
hugo-butterfly-site (demo repo)
├── 源代码 → GitHub: ouraihub-hugo-themes/hugo-butterfly-site
├── 构建产物 → GitHub Pages: hugobutterfly/hugobutterfly.github.io
└── 主题子模块 ← ouraihub-hugo-themes/hugo-butterfly
```

## 🎯 目标

1. **Demo 仓库** (`ouraihub-hugo-themes/hugo-butterfly-site`)
   - 存储示例网站源代码
   - 包含Hugo配置、内容、i18n、archetypes等
   - 自动构建并部署到GitHub Pages

2. **GitHub Pages 仓库** (`hugobutterfly/hugobutterfly.github.io`)
   - 存储构建后的静态网站
   - 通过GitHub Pages自动发布
   - 访问地址: https://hugobutterfly.github.io

3. **主题仓库** (`ouraihub-hugo-themes/hugo-butterfly`)
   - 作为子模块被引用
   - 用户可以自动获取最新主题

---

## 📁 .gitignore 策略

### 不需要提交的文件/目录

| 项目 | 原因 | 优先级 |
|------|------|--------|
| `public/` | Hugo构建产物，应该由CI/CD生成 | ⭐⭐⭐ |
| `resources/` | Hugo缓存文件 | ⭐⭐⭐ |
| `.hugo_build.lock` | Hugo构建锁文件 | ⭐⭐ |
| `hugo_stats.json` | Tailwind CSS统计数据（构建生成） | ⭐⭐ |
| `node_modules/` | NPM依赖（如果有package.json） | ⭐⭐⭐ |
| `.env` | 环境变量（敏感信息） | ⭐⭐⭐ |
| `OS文件` | `.DS_Store`, `Thumbs.db` | ⭐⭐ |
| `IDE配置` | `.vscode/`, `.idea/` | ⭐ |
| `*.log` | 日志文件 | ⭐⭐ |

### 需要提交的目录

✅ `config/` - Hugo配置
✅ `content/` - 文章内容
✅ `i18n/` - 国际化文件
✅ `layouts/` - 自定义布局（如有）
✅ `archetypes/` - 内容模板
✅ `static/` - 静态文件
✅ `assets/` - 资源文件
✅ `data/` - 数据文件
✅ `.gitmodules` - 主题子模块配置

---

## 🔧 GitHub Actions 工作流设计

### 触发条件
- 推送到 `master` 分支时自动构建
- 手动触发 (`workflow_dispatch`) 时构建

### 工作流步骤

1. 检出代码（包含子模块初始化）
2. 安装Hugo和Node.js环境
3. 构建Hugo静态网站
4. 部署到 hugobutterfly/hugobutterfly.github.io

---

## 📋 操作检查清单

### 第一阶段：清理源仓库
- [ ] 创建 `.gitignore` 文件
- [ ] 删除 `public/` 目录
- [ ] 删除 `hugo_stats.json`
- [ ] 删除 `.hugo_build.lock`
- [ ] 验证 `.gitmodules` 正确

### 第二阶段：GitHub仓库设置
- [ ] 创建 `ouraihub-hugo-themes/hugo-butterfly-site` 仓库
- [ ] 创建 `hugobutterfly/hugobutterfly.github.io` 仓库
- [ ] 配置GitHub Pages设置
- [ ] 生成部署密钥或配置Token

### 第三阶段：创建工作流
- [ ] 创建 `.github/workflows/deploy.yml`
- [ ] 配置工作流权限
- [ ] 测试工作流执行

### 第四阶段：验证部署
- [ ] 访问 https://hugobutterfly.github.io
- [ ] 验证所有语言版本正常
- [ ] 检查主题样式加载
- [ ] 验证搜索功能

