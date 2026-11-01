# xward-website

[xward.app](https://xward.app) 的页面。Xward 是一款 iPhone 倒数 app。

`public/` 里的静态文件原样发布，没有构建步骤。推送到 `main` 后，Vercel 会自动部署到生产环境。

本地预览：直接打开 `public/index.html`。

截图在 `public/screens/`，是 app 的真实界面配样例数据，界面改了要重新截。尺寸是宽 804 像素、sRGB 的 JPEG。

## 域名

域名和 DNS 在 Cloudflare。`www.xward.app` 用 301 跳到 `xward.app`，这不在代码里，是 Cloudflare 后台 xward.app 下的两项配置：

- DNS 记录：`A`，名字 `www`，地址 `192.0.2.1`，开代理。这个地址只是占位，请求到不了它。
- Redirect Rule，名字 `www to root`：把 `https://www.xward.app/*` 跳到 `https://xward.app/${1}`，状态码 301，保留查询参数。
