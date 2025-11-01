# Hugo Butterfly 示例網站 - 部署指南

[简体中文](DEPLOYMENT-ZH.md) | [English](DEPLOYMENT-EN.md) | [繁體中文](DEPLOYMENT-ZH-TW.md)

---

### 前置條件

- GitHub 帳戶及兩個倉庫已準備好：
  - `ouraihub-hugo-themes/hugo-butterfly-site`（源代碼）
  - `hugobutterfly/hugobutterfly.github.io`（GitHub Pages）
- 個人訪問令牌（用於跨倉庫部署）

### 步驟 1：創建 GitHub 倉庫

**源代碼倉庫：**
- 組織: `ouraihub-hugo-themes`
- 倉庫名: `hugo-butterfly-site`
- 可見性: Public
- 描述: Hugo Butterfly 示例網站源代碼

**GitHub Pages 倉庫：**
- 帳戶: `hugobutterfly`
- 倉庫名: `hugobutterfly.github.io`
- 可見性: Public（GitHub Pages 要求）
- 描述: Hugo Butterfly 官方示例網站

### 步驟 2：配置 GitHub Pages

在 `hugobutterfly/hugobutterfly.github.io` 倉庫中：
1. 進入 Settings → Pages
2. Source: Deploy from a branch
3. Branch: master
4. Folder: / (root)

### 步驟 3：創建個人訪問令牌

1. GitHub → Settings → Developer settings → Personal access tokens
2. 點擊 "Tokens (classic)" → "Generate new token"
3. Token 名稱: `pages-deploy-token`
4. 權限: `repo`, `workflow`
5. 有效期: 90 天
6. 複製令牌值

### 步驟 4：添加 Secret 到源倉庫

在 `ouraihub-hugo-themes/hugo-butterfly-site` 倉庫中：
1. Settings → Secrets and variables → Actions
2. 新建倉庫 secret
3. 名稱: `PAGES_REPO_TOKEN`
4. 值: 粘貼你的個人訪問令牌
5. 點擊"Add secret"

### 步驟 5：推送代碼到 GitHub

```bash
cd E:\workspace\hugo\hugo-butterfly-site

# 添加遠程倉庫
git remote add origin https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git

# 確保在 master 分支
git branch -M master

# 推送到 GitHub
git push -u origin master
```

### 步驟 6：監控部署

1. 訪問: https://github.com/ouraihub-hugo-themes/hugo-butterfly-site/actions
2. 觀察工作流執行狀態
3. 查看是否有綠色勾號（成功）或紅色 X（失敗）
4. 如有問題，查看日誌

### 步驟 7：驗證線上網站

工作流完成後（5-10 分鐘）：
1. 訪問: https://hugobutterfly.github.io
2. 驗證所有頁面正常加載
3. 測試搜索功能
4. 檢查所有語言版本：
   - 中文: /zh/
   - 英文: /en/
   - 繁體: /zh-tw/

### 部署工作流

GitHub Actions 工作流自動執行：
1. 檢出代碼（含子模塊）
2. 安裝 Hugo 和 Node.js
3. 安裝主題依賴
4. 構建 Hugo 網站
5. 使用 Pagefind 生成搜索索引
6. 部署到 GitHub Pages
7. 推送到 hugobutterfly.github.io 倉庫

### 故障排除

**工作流失敗：**
- 檢查 Actions 日誌查看錯誤詳情
- 驗證 PAGES_REPO_TOKEN 配置是否正確
- 確保主題倉庫是公開的且可訪問

**搜索不工作：**
- 驗證構建後 `public/_pagefind/` 目錄存在
- 檢查瀏覽器 Network 標籤中 pagefind.js 是否加載
- 確保 `config/_default/params.toml` 中搜索已啟用

**頁面不顯示：**
- 檢查 GitHub Pages 設置
- 驗證 hugobutterfly.github.io 分支/文件夾設置
- 清除瀏覽器緩存
