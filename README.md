# 江浙沪旅行手册

页面本体只有 `dist/index.html`，无第三方前端依赖。Cloudflare Workers 会直接托管该静态文件。

## 首次发布（只需操作一次）

1. 在 GitHub 新建一个空仓库，把本目录内容推送到该仓库。
2. 登录 Cloudflare，进入 **Workers & Pages → Create application → Import a repository**。
3. 连接 GitHub 并选择刚才的仓库。
4. Build command 留空；Deploy command 填 `npx wrangler deploy`；Root directory 留空。
5. 保存并部署。完成后会获得公开的 `*.workers.dev` 网址。

此后只需修改并 push 到 GitHub 默认分支，Cloudflare Workers Builds 会自动重新发布。

## 本地预览

直接双击 `dist/index.html` 即可离线查看。实时天气需要联网；无网络时会显示上次成功获取的数据。
