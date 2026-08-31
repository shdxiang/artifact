# artifact

静态科普页面：《为什么 1 千克的薄层水，仍可能让挡板承受 1000 吨力？》

- 页面源码：`public/hydrostatic-paradox.html`（单文件，无外部依赖）
- 部署（Cloudflare Worker 静态资源）：

```sh
npx wrangler deploy
```

需先 `npx wrangler login`。部署后 `index.html` 自动作为站点首页并跳转到正文页。
