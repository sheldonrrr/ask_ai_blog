# 博客部署指引

本文档说明如何部署 Ask AI Plugin 博客站点到 Cloudflare Pages。

## 一键部署

cd ./blog #进入blog目录
npm run build #本地生成静态站点目录
wrangler pages deploy .vitepress/dist --project-name=ask-ai-blog #部署到Cloudflare Pages

## 项目结构

```
blog/
├── .vitepress/
│   └── config.mts      # VitePress 配置
├── public/
│   └── images/         # 共用图片资源 (中英文共用)
├── zh/                 # 中文内容 (主要维护)
│   ├── index.md
│   ├── about.md
│   ├── docs/           # 中文文档
│   └── posts/          # 中文博客文章
├── en/                 # 英文内容 (同步更新)
│   ├── index.md
│   ├── about.md
│   ├── docs/           # 英文文档
│   └── posts/          # 英文博客文章
└── wrangler.toml       # Cloudflare Pages 配置
```

## 内容维护说明

- **主要维护中文** (`zh/`)，然后同步更新英文 (`en/`)
- **图片共用**: 所有图片放在 `public/images/`，中英文文档引用同一图片
- **文件对应**: `zh/docs/xxx.md` 对应 `en/docs/xxx.md`，方便同步维护

## 本地开发

```bash
cd blog
npm install
npm run dev
```

访问 http://localhost:5173

## 构建

```bash
npm run build
```

构建产物在 `.vitepress/dist/`

## 部署到 Cloudflare Pages

### 自动部署 (推荐)

已配置 GitHub Actions，当 `blog/` 目录有更新并 push 到 `main` 分支时自动部署。

**配置步骤：**

1. 在 GitHub 仓库设置 Secrets:
   - `CLOUDFLARE_API_TOKEN`: Cloudflare API Token (需要 Pages 权限)
   - `CLOUDFLARE_ACCOUNT_ID`: Cloudflare Account ID

2. 获取 Cloudflare API Token:
   - 访问 https://dash.cloudflare.com/profile/api-tokens
   - 创建 Token，选择 "Edit Cloudflare Workers" 模板
   - 或自定义权限: Account > Cloudflare Pages > Edit

3. 获取 Account ID:
   - 访问 https://dash.cloudflare.com/
   - 右侧栏可以看到 Account ID

4. Push 代码即可自动部署:
   ```bash
   git add .
   git commit -m "Update blog"
   git push origin main
   ```

### 手动部署

```bash
cd blog
npm run deploy
```

需要先登录 wrangler:
```bash
npx wrangler login
```

## 首次部署

首次部署会自动创建 Cloudflare Pages 项目 `ask-ai-blog`。

部署成功后访问: `https://ask-ai-blog.pages.dev`

## 自定义域名

1. 在 Cloudflare Dashboard > Pages > ask-ai-blog > Custom domains
2. 添加自定义域名
3. 按提示配置 DNS

## 图片使用

在 Markdown 中引用图片:

```markdown
![描述](/images/screenshot.png)
```

图片实际存放在 `public/images/screenshot.png`

## 多语言 URL 结构

- 中文: `/zh/docs/xxx`
- 英文: `/en/docs/xxx`
- 首页默认重定向到中文

## 常见问题

### 构建失败

1. 检查 Node.js 版本 (建议 18+)
2. 删除 `node_modules` 重新安装
3. 检查 Markdown 语法错误

### 图片不显示

1. 确认图片在 `public/images/` 目录
2. 路径使用 `/images/xxx.png` (以 `/` 开头)

---

*最后更新: 2026-02-09*