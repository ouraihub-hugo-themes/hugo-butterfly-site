---
title: "测试文章 4：响应式设计原则"
slug: "responsive-design-principles"
date: 2024-10-24T10:00:00+08:00
draft: false
categories: ["设计"]
tags: ["响应式", "UI/UX"]
cover: "https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800"
description: "学习响应式设计的核心原则和实践方法"

aliases:
  - /2024/10/测试文章-4响应式设计原则/
---

# 响应式设计原则

响应式设计让网站在不同设备上都能完美呈现。

## 核心原则

1. 流式布局
2. 弹性图片
3. 媒体查询
4. 移动优先

## 断点设置

```css
/* 移动端 */
@media (max-width: 768px) {
  /* 样式 */
}

/* 平板 */
@media (min-width: 769px) and (max-width: 1024px) {
  /* 样式 */
}

/* 桌面 */
@media (min-width: 1025px) {
  /* 样式 */
}
```

## 最佳实践

- 使用相对单位（rem, em, %）
- 优化触摸目标大小
- 测试多种设备
- 性能优化

## 总结

响应式设计是现代 Web 开发的必备技能。

