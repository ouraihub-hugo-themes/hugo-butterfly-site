# Hugo Butterfly 示例网站 - 部署指南

[简体中文](DEPLOYMENT-ZH.md) | [English](DEPLOYMENT-EN.md) | [繁體中文](DEPLOYMENT-ZH-TW.md)

---

### 前置条件

- GitHub 账户及两个仓库已准备好：
  - `ouraihub-hugo-themes/hugo-butterfly-site`（源代码）
  - `hugobutterfly/hugobutterfly.github.io`（GitHub Pages）
- 个人访问令牌（用于跨仓库部署）

### 步骤 1：创建 GitHub 仓库

**源代码仓库：**
- 组织: `ouraihub-hugo-themes`
- 仓库名: `hugo-butterfly-site`
- 可见性: Public
- 描述: Hugo Butterfly 示例网站源代码

**GitHub Pages 仓库：**
- 账户: `hugobutterfly`
- 仓库名: `hugobutterfly.github.io`
- 可见性: Public（GitHub Pages 要求）
- 描述: Hugo Butterfly 官方示例网站

### 步骤 2：配置 GitHub Pages

在 `hugobutterfly/hugobutterfly.github.io` 仓库中：
1. 进入 Settings → Pages
2. Source: Deploy from a branch
3. Branch: master
4. Folder: / (root)

### 步骤 3：创建个人访问令牌

1. GitHub → Settings → Developer settings → Personal access tokens
2. 点击 "Tokens (classic)" → "Generate new token"
3. Token 名称: `pages-deploy-token`
4. 权限: `repo`, `workflow`
5. 有效期: 90 天
6. 复制令牌值

### 步骤 4：添加 Secret 到源仓库

在 `ouraihub-hugo-themes/hugo-butterfly-site` 仓库中：
1. Settings → Secrets and variables → Actions
2. 新建仓库 secret
3. 名称: `PAGES_REPO_TOKEN`
4. 值: 粘贴你的个人访问令牌
5. 点击"Add secret"

### 步骤 5：推送代码到 GitHub

```bash
cd E:\workspace\hugo\hugo-butterfly-site

# 添加远程仓库
git remote add origin https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git

# 确保在 master 分支
git branch -M master

# 推送到 GitHub
git push -u origin master
```

### 步骤 6：监控部署

1. 访问: https://github.com/ouraihub-hugo-themes/hugo-butterfly-site/actions
2. 观察工作流执行状态
3. 查看是否有绿色勾号（成功）或红色 X（失败）
4. 如有问题，查看日志

### 步骤 7：验证在线网站

工作流完成后（5-10 分钟）：
1. 访问: https://hugobutterfly.github.io
2. 验证所有页面正常加载
3. 测试搜索功能
4. 检查所有语言版本：
   - 中文: /zh/
   - 英文: /en/
   - 繁体: /zh-tw/

### 部署工作流

GitHub Actions 工作流自动执行：
1. 检出代码（含子模块）
2. 安装 Hugo 和 Node.js
3. 安装主题依赖
4. 构建 Hugo 网站
5. 使用 Pagefind 生成搜索索引
6. 部署到 GitHub Pages
7. 推送到 hugobutterfly.github.io 仓库

### 故障排除

**工作流失败：**
- 检查 Actions 日志查看错误详情
- 验证 PAGES_REPO_TOKEN 配置是否正确
- 确保主题仓库是公开的且可访问

**搜索不工作：**
- 验证构建后 `public/_pagefind/` 目录存在
- 检查浏览器 Network 标签中 pagefind.js 是否加载
- 确保 `config/_default/params.toml` 中搜索已启用

**页面不显示：**
- 检查 GitHub Pages 设置
- 验证 hugobutterfly.github.io 分支/文件夹设置
- 清除浏览器缓存
