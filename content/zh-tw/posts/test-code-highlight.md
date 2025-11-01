---
title: "代码高亮测試"
slug: "code-highlighting-test"
date: 2024-10-30T10:00:00+08:00
draft: false
categories: ["技術"]
tags: ["测試", "代码高亮"]
cover: "https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800"
description: "测試代码高亮功能"

aliases:
  - /2024/10/代码高亮测試/
---

## JavaScript 代码示例

```javascript
// 這是一個 JavaScript 示例
function greet(name) {
  console.log(`Hello, ${name}!`);
  return `Welcome to Hugo Butterfly Theme`;
}

const user = {
  name: 'Developer',
  age: 25,
  skills: ['JavaScript', 'TypeScript', 'Hugo']
};

greet(user.name);
```

## TypeScript 代码示例

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

class UserService {
  private users: User[] = [];

  addUser(user: User): void {
    this.users.push(user);
  }

  getUserById(id: number): User | undefined {
    return this.users.find(u => u.id === id);
  }
}

const service = new UserService();
service.addUser({ id: 1, name: 'Alice', email: 'alice@example.com' });
```

## Python 代码示例

```python
# Python 示例代码
def fibonacci(n):
    """計算斐波那契数列"""
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

class Calculator:
    def __init__(self):
        self.result = 0
    
    def add(self, x, y):
        self.result = x + y
        return self.result
    
    def multiply(self, x, y):
        self.result = x * y
        return self.result

# 使用示例
calc = Calculator()
print(calc.add(5, 3))
print(calc.multiply(4, 6))
```

## Go 代码示例

```go
package main

import (
    "fmt"
    "time"
)

type Person struct {
    Name string
    Age  int
}

func (p Person) Greet() string {
    return fmt.Sprintf("Hello, I'm %s and I'm %d years old", p.Name, p.Age)
}

func main() {
    person := Person{
        Name: "John",
        Age:  30,
    }
    
    fmt.Println(person.Greet())
    fmt.Println("Current time:", time.Now())
}
```

## CSS 代码示例

```css
/* 現代化的 CSS 樣式 */
:root {
  --primary-color: #49b1f5;
  --text-color: #333;
  --bg-color: #fff;
}

.card {
  padding: 1.5rem;
  background: var(--bg-color);
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

@media (max-width: 768px) {
  .card {
    padding: 1rem;
  }
}
```

## HTML 代码示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hugo Butterfly Theme</title>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <header class="site-header">
    <nav class="navbar">
      <a href="/" class="logo">Butterfly</a>
      <ul class="menu">
        <li><a href="/">首页</a></li>
        <li><a href="/posts/">文章</a></li>
        <li><a href="/about/">關于</a></li>
      </ul>
    </nav>
  </header>
  
  <main class="container">
    <h1>欢迎使用 Hugo Butterfly</h1>
    <p>這是一個優雅的博客主题</p>
  </main>
  
  <script src="/js/bundle.js"></script>
</body>
</html>
```

## Bash 脚本示例

```bash
#!/bin/bash

# Hugo 构建脚本
echo "開始构建 Hugo 站點..."

# 清理旧的构建文件
rm -rf public

# 編译 TypeScript
pnpm run ts:build

# 編译 CSS
pnpm run css:build

# 构建 Hugo 站點
hugo --minify

echo "构建完成！"
```

## SQL 查詢示例

```sql
-- 創建用户表
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 插入数据
INSERT INTO users (username, email) VALUES
    ('alice', 'alice@example.com'),
    ('bob', 'bob@example.com');

-- 查詢数据
SELECT u.username, u.email, COUNT(p.id) as post_count
FROM users u
LEFT JOIN posts p ON u.id = p.user_id
GROUP BY u.id
ORDER BY post_count DESC;
```

## 長代码示例（测試高度限制）

```javascript
// 這是一個很長的代码示例，用于测試高度限制和展開功能
class BlogSystem {
  constructor() {
    this.posts = [];
    this.categories = [];
    this.tags = [];
    this.users = [];
  }

  // 添加文章
  addPost(post) {
    const newPost = {
      id: this.posts.length + 1,
      title: post.title,
      content: post.content,
      author: post.author,
      category: post.category,
      tags: post.tags || [],
      createdAt: new Date(),
      updatedAt: new Date(),
      views: 0,
      likes: 0
    };
    this.posts.push(newPost);
    return newPost;
  }

  // 獲取文章
  getPost(id) {
    return this.posts.find(post => post.id === id);
  }

  // 更新文章
  updatePost(id, updates) {
    const post = this.getPost(id);
    if (post) {
      Object.assign(post, updates);
      post.updatedAt = new Date();
      return post;
    }
    return null;
  }

  // 删除文章
  deletePost(id) {
    const index = this.posts.findIndex(post => post.id === id);
    if (index !== -1) {
      this.posts.splice(index, 1);
      return true;
    }
    return false;
  }

  // 搜索文章
  searchPosts(keyword) {
    return this.posts.filter(post => 
      post.title.includes(keyword) || 
      post.content.includes(keyword)
    );
  }

  // 按分類獲取文章
  getPostsByCategory(category) {
    return this.posts.filter(post => post.category === category);
  }

  // 按标签獲取文章
  getPostsByTag(tag) {
    return this.posts.filter(post => post.tags.includes(tag));
  }

  // 獲取熱門文章
  getPopularPosts(limit = 10) {
    return this.posts
      .sort((a, b) => b.views - a.views)
      .slice(0, limit);
  }

  // 增加浏览量
  incrementViews(id) {
    const post = this.getPost(id);
    if (post) {
      post.views++;
      return post;
    }
    return null;
  }

  // 點贊文章
  likePost(id) {
    const post = this.getPost(id);
    if (post) {
      post.likes++;
      return post;
    }
    return null;
  }
}

// 使用示例
const blog = new BlogSystem();

blog.addPost({
  title: '如何使用 Hugo 构建博客',
  content: 'Hugo 是一個快速的静態網站生成器...',
  author: 'Alice',
  category: '技術',
  tags: ['Hugo', 'Blog', 'Static Site']
});

blog.addPost({
  title: 'TypeScript 最佳实践',
  content: 'TypeScript 提供了類型安全...',
  author: 'Bob',
  category: '編程',
  tags: ['TypeScript', 'JavaScript', 'Best Practices']
});

console.log('所有文章:', blog.posts);
console.log('技術分類文章:', blog.getPostsByCategory('技術'));
console.log('熱門文章:', blog.getPopularPosts(5));
```
