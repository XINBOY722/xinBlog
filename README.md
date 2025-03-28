# xinBlog

我的个人博客项目，记录技术学习和生活感悟。

## 项目特点
- 基于 [Hexo](https://hexo.io/) 静态博客框架
- 使用 [Butterfly](https://github.com/jerryc127/hexo-theme-butterfly) 主题
- 支持 Markdown 写作
- 自动部署到 GitHub Pages

## 快速开始

### 安装依赖
```bash
npm install
```
### 本地运行
```bash
hexo server
```
### 生成静态文件
```bash
hexo generate
```
### 部署
```bash
hexo deploy
```
### 项目结构
```bash
xinBlog/
├── source/          # 文章和资源文件
├── themes/          # 主题文件
├── _config.yml      # 站点配置文件
└── package.json     # 项目依赖
```