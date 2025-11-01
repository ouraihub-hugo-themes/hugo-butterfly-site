# Hugo Butterfly Demo Site - Deployment Guide

[简体中文](DEPLOYMENT-ZH.md) | English | [繁體中文](DEPLOYMENT-ZH-TW.md)

---

### Prerequisites

- GitHub account with two repositories ready:
  - `ouraihub-hugo-themes/hugo-butterfly-site` (source code)
  - `hugobutterfly/hugobutterfly.github.io` (GitHub Pages)
- Personal Access Token for cross-repository deployment

### Step 1: Create GitHub Repositories

**Source Repository:**
- Organization: `ouraihub-hugo-themes`
- Repository: `hugo-butterfly-site`
- Visibility: Public
- Description: Hugo Butterfly example website source code

**Pages Repository:**
- Account: `hugobutterfly`
- Repository: `hugobutterfly.github.io`
- Visibility: Public (required for GitHub Pages)
- Description: Hugo Butterfly official example website

### Step 2: Configure GitHub Pages

In `hugobutterfly/hugobutterfly.github.io`:
1. Go to Settings → Pages
2. Source: Deploy from a branch
3. Branch: master
4. Folder: / (root)

### Step 3: Create Personal Access Token

1. GitHub → Settings → Developer settings → Personal access tokens
2. Click "Tokens (classic)" → "Generate new token"
3. Token name: `pages-deploy-token`
4. Scopes: `repo`, `workflow`
5. Expiration: 90 days
6. Copy the token value

### Step 4: Add Secret to Source Repository

In `ouraihub-hugo-themes/hugo-butterfly-site`:
1. Settings → Secrets and variables → Actions
2. New repository secret
3. Name: `PAGES_REPO_TOKEN`
4. Value: Paste your Personal Access Token
5. Click "Add secret"

### Step 5: Push Code to GitHub

```bash
cd E:\workspace\hugo\hugo-butterfly-site

# Add remote repository
git remote add origin https://github.com/ouraihub-hugo-themes/hugo-butterfly-site.git

# Ensure you're on master branch
git branch -M master

# Push to GitHub
git push -u origin master
```

### Step 6: Monitor Deployment

1. Visit: https://github.com/ouraihub-hugo-themes/hugo-butterfly-site/actions
2. Watch the workflow execution
3. Check for green checkmark (success) or red X (failure)
4. View logs if there are issues

### Step 7: Verify Live Site

After workflow completes (5-10 minutes):
1. Visit: https://hugobutterfly.github.io
2. Verify all pages load correctly
3. Test search functionality
4. Check all language versions:
   - Chinese: /zh/
   - English: /en/
   - Traditional Chinese: /zh-tw/

### Deployment Workflow

The GitHub Actions workflow automatically:
1. Checks out code with submodules
2. Installs Hugo and Node.js
3. Installs theme dependencies
4. Builds Hugo site
5. Generates search index with Pagefind
6. Deploys to GitHub Pages
7. Pushes to hugobutterfly.github.io repository

### Troubleshooting

**Workflow fails:**
- Check Actions logs for error details
- Verify PAGES_REPO_TOKEN is correctly configured
- Ensure theme repository is public and accessible

**Search not working:**
- Verify `public/_pagefind/` directory exists after build
- Check that pagefind.js loaded in browser Network tab
- Ensure search is enabled in `config/_default/params.toml`

**Pages not showing:**
- Check GitHub Pages settings
- Verify hugobutterfly.github.io has correct branch/folder settings
- Clear browser cache
