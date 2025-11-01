# GitHub 部署检查清单

## 📋 部署配置总结

### 仓库结构
```
hugo-butterfly-site (源代码仓库)
├── 存储位置: https://github.com/ouraihub-hugo-themes/hugo-butterfly-site
├── 分支: master (主分支)
└── 触发: push到master或手动workflow_dispatch
```

### 部署目标
```
hugobutterfly.github.io (GitHub Pages仓库)
├── 存储位置: https://github.com/hugobutterfly/hugobutterfly.github.io
├── 分支: master (GitHub Pages分支)
└── 访问: https://hugobutterfly.github.io
```

---

## ✅ 已完成的准备工作

### 1. 源仓库清理
- [x] 创建 `.gitignore` 文件
  - 排除: `public/`, `resources/`, `.hugo_build.lock`, `hugo_stats.json`
  - 排除: `node_modules/`, `.env`, `OS文件`, `IDE配置`
- [x] 删除 `public/` 目录（大小: 12M）
- [x] 删除 `hugo_stats.json` 文件
- [x] 删除 `.hugo_build.lock` 文件
- [x] 验证 `.gitmodules` 配置正确

### 2. 主题子模块
- [x] 子模块路径: `themes/hugo-butterfly`
- [x] 子模块URL: `https://github.com/ouraihub-hugo-themes/hugo-butterfly.git`
- [x] 子模块状态: 已初始化且可用

### 3. Hugo配置
- [x] 主题设置: `theme = 'hugo-butterfly'`
- [x] 多语言配置: zh, en, zh-tw
- [x] 内容结构: 正确的语言分类 (`content/zh/`, `content/en/`, `content/zh-tw/`)
- [x] i18n文件: 三种语言的翻译文件已配置

### 4. GitHub Actions工作流
- [x] 工作流文件: `.github/workflows/deploy.yml`
- [x] 触发条件: push到master分支或手动触发
- [x] 工作流步骤:
  1. 检出代码（包含子模块）
  2. 安装Hugo和Node.js
  3. 构建Hugo网站
  4. 上传制品到GitHub Pages
  5. 部署到GitHub Pages
  6. 额外: 推送到hugobutterfly.github.io仓库

---

## 🔧 所需的GitHub配置

### 必需步骤

#### 1. 创建两个仓库
```bash
# 在 ouraihub-hugo-themes 组织下
# 仓库名: hugo-butterfly-site
# 可见性: Public 或 Private（根据需求）
# 说明: Hugo Butterfly 示例网站源代码

# 在 hugobutterfly 账户下
# 仓库名: hugobutterfly.github.io
# 可见性: Public（GitHub Pages要求）
# 说明: Hugo Butterfly 官方示例网站
```

#### 2. 配置 hugobutterfly.github.io 仓库
```
设置 → Pages
├── Source: Deploy from a branch
├── Branch: master (或 gh-pages)
└── Folder: / (root)
```

#### 3. 配置部署令牌（两个选项）

**选项A: 使用 PAGES_REPO_TOKEN（推荐）**
1. 在 `hugobutterfly/hugobutterfly.github.io` 创建 Personal Access Token
   - Settings → Developer settings → Personal access tokens → Tokens (classic)
   - 权限: `repo`, `workflow`
   - 保存令牌

2. 在 `ouraihub-hugo-themes/hugo-butterfly-site` 仓库中添加Secret
   - Settings → Secrets and variables → Actions
   - 新建Secret: `PAGES_REPO_TOKEN`
   - 粘贴上面保存的令牌

**选项B: 使用部署密钥（替代方案）**
1. 在 `hugobutterfly/hugobutterfly.github.io` 生成SSH密钥对
2. 在 `ouraihub-hugo-themes/hugo-butterfly-site` 添加私钥为Secret

---

## 📝 工作流程详解

### 当你推送代码到 master 分支时

1. **触发**: GitHub Actions 自动启动
2. **检出**: 克隆源代码 + 初始化主题子模块
3. **构建**: Hugo 构建网站到 `public/` 目录
4. **双重部署**:
   - **方案A**: 使用GitHub Pages官方方式
     - 上传制品 → 自动部署到GitHub Pages
     - 访问: https://hugobutterfly.github.io
   
   - **方案B**: 推送到独立Pages仓库
     - 克隆 hugobutterfly.github.io
     - 复制 `public/*` 到该仓库
     - 提交并推送到 master 分支
     - GitHub Pages 自动发布

---

## 🚀 后续操作步骤

### 第1步: 准备GitHub
```
1. 在 https://github.com/ouraihub-hugo-themes 创建 hugo-butterfly-site 仓库
2. 在 https://github.com/hugobutterfly 创建 hugobutterfly.github.io 仓库
3. 配置hugobutterfly.github.io的GitHub Pages设置
4. 创建和配置 PAGES_REPO_TOKEN（如果使用跨仓库部署）
```

### 第2步: 推送源代码
```bash
cd E:/workspace/hugo/hugo-butterfly-site

# 添加远程仓库
git remote add origin https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git

# 推送到GitHub
git branch -M master
git push -u origin master
```

### 第3步: 验证部署
```
1. 访问 https://hugobutterfly.github.io
2. 检查页面是否正确加载
3. 验证所有语言版本 (zh, en, zh-tw)
4. 测试主题切换功能
5. 验证搜索功能（pagefind）
```

### 第4步: 后续维护
```bash
# 更新主题
cd themes/hugo-butterfly
git pull origin master
cd ../..

# 提交更新
git add themes/hugo-butterfly
git commit -m "Update hugo-butterfly theme"
git push origin master
```

---

## 📊 工作流程图

```
┌─────────────────────────────────────┐
│  推送到 master 分支                  │
└──────────────────┬──────────────────┘
                   │
                   ▼
        ┌──────────────────────┐
        │  GitHub Actions触发   │
        └──────────────┬───────┘
                       │
         ┌─────────────┼─────────────┐
         │             │             │
         ▼             ▼             ▼
   ┌─────────┐  ┌──────────┐  ┌──────────┐
   │ 检出代码 │  │ 安装环境 │  │ 初始化  │
   │ (含子模块)│  │ (Hugo) │  │ 子模块  │
   └────┬────┘  └────┬─────┘  └────┬─────┘
        │             │             │
        └─────────────┼─────────────┘
                      │
                      ▼
              ┌────────────────┐
              │ 构建Hugo网站   │
              │ public/ 输出   │
              └────────┬───────┘
                       │
         ┌─────────────┴─────────────┐
         │                           │
         ▼                           ▼
  ┌────────────────┐         ┌──────────────────┐
  │ GitHub Pages   │         │ 推送到Pages仓库  │
  │ 自动发布       │         │ 手动同步方案     │
  └────────────────┘         └──────────────────┘
         │                           │
         └─────────────┬─────────────┘
                       │
                       ▼
           ┌──────────────────────┐
           │ 访问示例网站         │
           │ hugobutterfly.github.io
           └──────────────────────┘
```

---

## ⚠️ 常见问题

### Q: 工作流失败怎么办？
A: 检查 Actions 日志：
- Settings → Actions → 查看失败的workflow
- 检查以下常见问题：
  - PAGES_REPO_TOKEN 是否正确配置
  - 子模块URL是否可访问
  - 主题仓库是否为公开

### Q: 如何更新主题？
A: 主题是通过子模块引用的
```bash
cd themes/hugo-butterfly
git pull origin master
cd ../..
git add themes/hugo-butterfly
git commit -m "Update theme"
git push
```

### Q: 如何自定义部署流程？
A: 编辑 `.github/workflows/deploy.yml`
- 修改构建命令
- 添加额外的构建步骤
- 配置不同的部署目标

### Q: GitHub Pages多久更新一次？
A: 通常在workflow完成后1-2分钟内更新

---

## 📞 下一步

1. 确认GitHub账户和组织已准备好
2. 运行 `git push` 将代码推送到GitHub
3. 观察 Actions 标签查看构建进度
4. 构建完成后访问 https://hugobutterfly.github.io

