# 小木块 · littlewood.io

用中学知识，把反直觉的科学问题画明白。静态站点，每篇文章一个自包含 HTML 文件（CSS/JS/SVG 全部内联，无构建、无外部依赖）。

- 首页：`public/index.html`（文章目录）
- 文章：`public/hydrostatic-paradox.html`（《为什么 1 千克的薄层水，仍可能让挡板承受 1000 吨力？》）
- 部署（Cloudflare Worker 静态资源，域名 littlewood.io）：push 到 `main` 自动部署，或手动：

```sh
npx wrangler deploy
```

