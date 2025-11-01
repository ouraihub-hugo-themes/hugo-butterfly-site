---
title: "Code Highlighting Test"
slug: "code-highlighting-test"
date: 2024-10-30T10:00:00+08:00
draft: false
categories: ["Technology"]
tags: ["Testing", "Code Highlighting"]
cover: "https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800"
description: "Testing code highlighting functionality"

aliases:
  - /en/2024/10/code-highlighting-test/
---

## JavaScript Code Example

```javascript
// This is a JavaScript example
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

## TypeScript Code Example

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

## Python Code Example

```python
# Python example code
def fibonacci(n):
    """Calculate Fibonacci sequence"""
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

# Usage example
calc = Calculator()
print(calc.add(5, 3))
print(calc.multiply(4, 6))
```

## Go Code Example

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

## CSS Code Example

```css
/* Modern CSS styles */
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

## HTML Code Example

```html
<!DOCTYPE html>
<html lang="en">
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
        <li><a href="/">Home</a></li>
        <li><a href="/posts/">Posts</a></li>
        <li><a href="/about/">About</a></li>
      </ul>
    </nav>
  </header>
  
  <main class="container">
    <h1>Welcome to Hugo Butterfly</h1>
    <p>This is an elegant blog theme</p>
  </main>
  
  <script src="/js/bundle.js"></script>
</body>
</html>
```

## Bash Script Example

```bash
#!/bin/bash

# Hugo build script
echo "Starting Hugo site build..."

# Clean old build files
rm -rf public

# Compile TypeScript
pnpm run ts:build

# Compile CSS
pnpm run css:build

# Build Hugo site
hugo --minify

echo "Build complete!"
```

## SQL Query Example

```sql
-- Create users table
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Insert data
INSERT INTO users (username, email) VALUES
    ('alice', 'alice@example.com'),
    ('bob', 'bob@example.com');

-- Query data
SELECT u.username, u.email, COUNT(p.id) as post_count
FROM users u
LEFT JOIN posts p ON u.id = p.user_id
GROUP BY u.id
ORDER BY post_count DESC;
```

## Long Code Example (Testing Height Limit)

```javascript
// This is a long code example to test height limit and expand functionality
class BlogSystem {
  constructor() {
    this.posts = [];
    this.categories = [];
    this.tags = [];
    this.users = [];
  }

  // Add post
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

  // Get post
  getPost(id) {
    return this.posts.find(post => post.id === id);
  }

  // Update post
  updatePost(id, updates) {
    const post = this.getPost(id);
    if (post) {
      Object.assign(post, updates);
      post.updatedAt = new Date();
      return post;
    }
    return null;
  }

  // Delete post
  deletePost(id) {
    const index = this.posts.findIndex(post => post.id === id);
    if (index !== -1) {
      this.posts.splice(index, 1);
      return true;
    }
    return false;
  }

  // Search posts
  searchPosts(keyword) {
    return this.posts.filter(post => 
      post.title.includes(keyword) || 
      post.content.includes(keyword)
    );
  }

  // Get posts by category
  getPostsByCategory(category) {
    return this.posts.filter(post => post.category === category);
  }

  // Get posts by tag
  getPostsByTag(tag) {
    return this.posts.filter(post => post.tags.includes(tag));
  }

  // Get popular posts
  getPopularPosts(limit = 10) {
    return this.posts
      .sort((a, b) => b.views - a.views)
      .slice(0, limit);
  }

  // Increment views
  incrementViews(id) {
    const post = this.getPost(id);
    if (post) {
      post.views++;
      return post;
    }
    return null;
  }

  // Like post
  likePost(id) {
    const post = this.getPost(id);
    if (post) {
      post.likes++;
      return post;
    }
    return null;
  }
}

// Usage example
const blog = new BlogSystem();

blog.addPost({
  title: 'How to Build a Blog with Hugo',
  content: 'Hugo is a fast static site generator...',
  author: 'Alice',
  category: 'Technology',
  tags: ['Hugo', 'Blog', 'Static Site']
});

blog.addPost({
  title: 'TypeScript Best Practices',
  content: 'TypeScript provides type safety...',
  author: 'Bob',
  category: 'Programming',
  tags: ['TypeScript', 'JavaScript', 'Best Practices']
});

console.log('All posts:', blog.posts);
console.log('Technology posts:', blog.getPostsByCategory('Technology'));
console.log('Popular posts:', blog.getPopularPosts(5));
```
