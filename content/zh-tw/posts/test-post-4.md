---
title: "测試文章 4：响應式設計原則"
slug: "responsive-design-principles"
date: 2024-10-24T10:00:00+08:00
draft: false
categories: ["設計"]
tags: ["响應式", "UI/UX"]
cover: "https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800"
description: "學習响應式設計的核心原則和实践方法"

aliases:
  - /2024/10/测試文章-4响應式設計原則/
---

# 响應式設計原則

响應式設計让網站在不同設备上都能完美呈現。

## 核心原則

1. 流式布局
2. 弹性圖片
3. 媒體查詢
4. 移動優先

## 断點設置

```css
/* 移動端 */
@media (max-width: 768px) {
  /* 樣式 */
}

/* 平板 */
@media (min-width: 769px) and (max-width: 1024px) {
  /* 樣式 */
}

/* 桌面 */
@media (min-width: 1025px) {
  /* 樣式 */
}
```

## 最佳实践

- 使用相對单位（rem, em, %）
- 優化触摸目标大小
- 测試多种設备
- 性能優化

## 总结

响應式設計是現代 Web 開發的必备技能。

