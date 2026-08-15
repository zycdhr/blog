# Yongchao's Blog

基于 Hexo + Butterfly 主题的个人技术博客，使用 GitHub Actions 自动部署到 GitHub Pages。

## 技术栈

- **框架**: [Hexo](https://hexo.io/)
- **主题**: [Butterfly](https://butterfly.js.org/)
- **部署**: GitHub Actions + GitHub Pages

## 本地开发

```bash
# 安装依赖
npm install

# 本地预览 (http://localhost:4000/blog/)
npx hexo server

# 生成静态文件
npx hexo clean && npx hexo generate

# 新建文章
npx hexo new "文章标题"
```

## 目录结构

```
blog/
├── .github/workflows/   # GitHub Actions 部署工作流
├── scaffolds/           # 文章模板
├── source/
│   ├── _posts/          # 博客文章
│   ├── about/           # 关于页面
│   ├── tags/            # 标签页面
│   └── categories/      # 分类页面
├── _config.yml          # Hexo 主配置
├── _config.butterfly.yml # Butterfly 主题配置
└── package.json
```

## 自动部署

推送到 `main` 分支后，GitHub Actions 会自动：
1. 安装依赖
2. 构建 Hexo 静态站点
3. 部署到 GitHub Pages

访问地址: https://zycdhr.github.io/blog/
