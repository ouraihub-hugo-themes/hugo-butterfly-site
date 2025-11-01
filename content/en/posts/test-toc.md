---
title: "Testing Table of Contents Functionality"
slug: "testing-table-of-contents-functionality"
date: 2025-10-29T15:00:00+08:00
draft: false
categories: ["Testing"]
tags: ["TOC", "Table of Contents", "Feature Test"]
cover: "https://images.unsplash.com/photo-1456324504439-367cee3b3c32?w=800"
description: "This is an article for testing the Table of Contents (TOC) functionality, containing multi-level heading structure."
toc: true

aliases:
  - /en/2025/10/testing-table-of-contents-functionality/
---

This is an article for testing the Table of Contents (TOC) functionality. The article contains multi-level headings to verify TOC generation, scroll highlighting, and click navigation features.

<!--more-->

## Chapter 1: Introduction

This is the content of Chapter 1. In this chapter, we will introduce the basic concepts and usage of the table of contents feature.

### 1.1 What is TOC

TOC (Table of Contents) is a tool that helps readers quickly understand the article structure and navigate to specific sections.

### 1.2 Purpose of TOC

The table of contents can:

- Provide an overview of the article structure
- Quickly locate sections of interest
- Enhance reading experience
- Display current reading progress

## Chapter 2: Features

This chapter introduces various features of TOC.

### 2.1 Auto Generation

TOC automatically generates the directory structure from article headings (H2, H3, etc.) without manual maintenance.

### 2.2 Scroll Highlighting

When users scroll the page, TOC automatically highlights the currently reading section, letting users clearly know their reading position.

#### 2.2.1 Highlighting Algorithm

Uses Intersection Observer API to detect whether heading elements enter the viewport, achieving precise scroll highlighting.

#### 2.2.2 Smooth Transition

Highlight state switching uses CSS transition animations to provide a smooth visual experience.

### 2.3 Click Navigation

Clicking any section in TOC smoothly scrolls the page to the corresponding heading position.

### 2.4 Reading Progress

TOC displays the current reading progress percentage at the top, letting users know their progress through the article.

## Chapter 3: Responsive Design

TOC has different presentations on different devices.

### 3.1 Desktop

On desktop (screen width ≥ 1024px), TOC is fixed in the sidebar using sticky positioning to follow page scrolling.

### 3.2 Mobile

On mobile (screen width < 1024px), TOC is hidden by default and can be toggled via a button.

#### 3.2.1 Floating Display

Mobile TOC displays as a floating card in the bottom right corner, not occupying the main content area.

#### 3.2.2 Touch Optimization

Mobile TOC links have larger click areas for easier touch operation.

## Chapter 4: Style Design

TOC style design follows the Butterfly theme's visual style.

### 4.1 Card Style

TOC uses card style, consistent with other theme components.

### 4.2 Color Scheme

- Normal links: Gray text
- Hover links: Theme color background + theme color text
- Active links: Theme color background + white text

### 4.3 Dark Mode

TOC fully supports dark mode, using dark background and light text in dark theme.

## Chapter 5: Technical Implementation

This chapter introduces TOC technical implementation details.

### 5.1 Hugo Template

Uses Hugo's `.TableOfContents` variable to automatically generate TOC HTML structure.

### 5.2 TypeScript Module

TOC interactive functionality is implemented in TypeScript, including:

- Scroll monitoring
- Highlight switching
- Click navigation
- Progress calculation

### 5.3 CSS Styles

Uses Tailwind CSS v4 and custom CSS to implement TOC styles.

#### 5.3.1 Layout

Uses Flexbox and Grid to implement responsive layout.

#### 5.3.2 Animation

Uses CSS transition and transform to implement smooth animation effects.

## Chapter 6: Performance Optimization

TOC implementation focuses on performance optimization.

### 6.1 Intersection Observer

Uses Intersection Observer API instead of traditional scroll event listening to reduce performance overhead.

### 6.2 Debouncing

For frequently triggered events (like scrolling), uses requestAnimationFrame for debouncing.

### 6.3 Lazy Loading

TOC only initializes when needed, not affecting initial page load speed.

## Chapter 7: Accessibility

TOC implementation considers accessibility (A11y).

### 7.1 Semantic HTML

Uses semantic HTML tags (nav, ul, li, a) to build TOC structure.

### 7.2 Keyboard Navigation

All links in TOC can be accessed via keyboard Tab key.

### 7.3 Screen Readers

Adds appropriate ARIA labels to TOC to ensure screen reader users can also use it.

## Chapter 8: Future Improvements

TOC functionality has some areas for improvement.

### 8.1 Collapse/Expand

Support collapsing and expanding sub-sections to make TOC more compact.

### 8.2 Search Functionality

Add a search box in TOC to quickly locate specific sections.

### 8.3 Custom Configuration

Allow users to customize TOC display levels (e.g., only show H2 and H3).

## Summary

Table of Contents (TOC) is an important feature for enhancing reading experience. Through features like auto generation, scroll highlighting, and click navigation, TOC helps readers better understand article structure and quickly navigate to content of interest.

This article introduced TOC's features, responsive design, style design, technical implementation, performance optimization, and accessibility, hoping to help you better understand and use this functionality.
