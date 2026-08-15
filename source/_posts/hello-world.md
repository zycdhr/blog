---
title: 欢迎来到我的博客
date: 2026-08-15 13:00:00
tags:
  - 公告
categories:
  - 随笔
cover: https://cdn.jsdelivr.net/npm/butterfly-extsrc@1.1.0/img/1.jpg
---

## 你好，世界！

欢迎来到我的个人技术博客！这里是我记录学习、分享思考的地方。

### 博客技术栈

这个博客基于以下技术构建：

| 技术 | 说明 |
|------|------|
| Hexo | 快速、简洁且高效的静态博客框架 |
| Butterfly | 功能丰富、美观大方的 Hexo 主题 |
| GitHub Pages | 免费的静态网站托管服务 |
| GitHub Actions | 自动化构建和部署 |

### 快速开始

如果你也想搭建一个类似的博客，只需要几步：

```bash
# 安装 Hexo
npm install -g hexo-cli

# 初始化博客
hexo init my-blog
cd my-blog

# 安装 Butterfly 主题
npm install hexo-theme-butterfly hexo-renderer-pug hexo-renderer-stylus

# 新建文章
hexo new "我的第一篇文章"

# 本地预览
hexo server

# 生成静态文件
hexo clean && hexo generate
```

### 代码高亮示例

```python
def fibonacci(n):
    """生成斐波那契数列"""
    a, b = 0, 1
    result = []
    for _ in range(n):
        result.append(a)
        a, b = b, a + b
    return result

print(fibonacci(10))
# 输出: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

### 接下来

我会在这里分享：

- 技术学习笔记
- 项目实战经验
- 开发工具推荐
- 读书心得

敬请期待！
