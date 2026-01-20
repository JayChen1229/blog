---
description: 部落格開發與部署流程
---

# 部落格開發與部署流程

## 開發模式

啟動本地開發伺服器：
// turbo
```bash
npm run dev
```

開發伺服器將在 http://localhost:4321 運行。

## 建置專案

建置靜態網站：
// turbo
```bash
npm run build
```

建置完成後，靜態檔案會在 `dist/` 目錄。

## 預覽建置結果

本地預覽建置後的網站：
// turbo
```bash
npm run preview
```

## 新增文章

1. 在 `src/content/blog/` 目錄建立新的 `.mdx` 檔案
2. 添加必要的 frontmatter：

```mdx
---
title: "文章標題"
description: "文章描述，用於 SEO 和預覽"
pubDate: "2025-01-20"
tags: ["Tag1", "Tag2"]
slug: "article-slug"
---

文章內容...
```

## SEO 驗證

建置後檢查 SEO 元素：
// turbo
```bash
# 確認 sitemap 已產生
cat dist/sitemap-index.xml

# 檢查 robots.txt
cat dist/robots.txt

# 驗證 Open Graph meta tags
grep -o 'og:[^"]*' dist/index.html
```

## 部署

專案設定為部署至 Cloudflare Pages。
推送至 main 分支會自動觸發部署。
// turbo
```bash
git add .
git commit -m "描述修改內容"
git push origin main
```
