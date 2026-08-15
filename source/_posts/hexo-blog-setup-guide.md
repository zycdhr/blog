---
title: Hexo + Butterfly + GitHub Actions 自动部署指南
date: 2026-08-15 13:30:00
tags:
  - Hexo
  - GitHub Actions
  - CI/CD
categories:
  - 教程
cover: https://cdn.jsdelivr.net/npm/butterfly-extsrc@1.1.0/img/3.jpg
---

## 前言

本文记录了使用 Hexo 搭建静态博客、配合 Butterfly 主题和 GitHub Actions 实现自动部署的完整流程。

## 环境准备

- Node.js >= 18
- Git
- GitHub 账号

## 安装 Hexo

```bash
npm install -g hexo-cli
hexo init blog
cd blog
npm install
```

## 安装 Butterfly 主题

```bash
npm install hexo-theme-butterfly hexo-renderer-pug hexo-renderer-stylus
```

在 `_config.yml` 中设置主题：

```yaml
theme: butterfly
```

## 配置 GitHub Actions 自动部署

在 `.github/workflows/deploy.yml` 中添加部署工作流：

```yaml
name: Deploy Hexo to GitHub Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 22
      - run: npm ci
      - run: npx hexo generate
      - uses: actions/upload-pages-artifact@v3
        with:
          path: ./public
      - uses: actions/deploy-pages@v4
```

## 验证 Token

按照 GitHub REST API 认证文档，使用 `Authorization: Bearer` 头部进行认证：

```bash
curl -H "Authorization: Bearer YOUR_TOKEN" \
     -H "User-Agent: My-App" \
     https://api.github.com/user
```

> **注意**：永远不要在 URL 中传递 Token，也不要将 Token 提交到代码仓库。

## 总结

通过 Hexo + Butterfly + GitHub Actions 的组合，我们可以：

1. 在本地用 Markdown 写文章
2. 推送到 GitHub 后自动构建部署
3. 通过 GitHub Pages 免费访问博客

祝写博客愉快！
