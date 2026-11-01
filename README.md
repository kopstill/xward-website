# xward-website

[xward.app](https://xward.app) 的页面。Xward 是一款 iPhone 倒数 app。

`public/` 里的静态文件原样发布，没有构建步骤。推送到 `main` 后，Vercel 会自动部署到生产环境。

本地预览：直接打开 `public/index.html`。

截图在 `public/screens/`，是 app 的真实界面配样例数据，界面改了要重新截。尺寸是宽 804 像素、sRGB 的 JPEG。

## 域名

域名在 Cloudflare 注册，它要求使用自己的域名服务器，所以 DNS 记录留在 Cloudflare。那里只有下面三条记录，都不开代理（DNS only），取值来自 Vercel 项目的域名设置：

| 类型 | 名字 | 内容 |
| --- | --- | --- |
| `A` | `@` | `216.150.1.1` |
| `A` | `@` | `216.150.16.1` |
| `CNAME` | `www` | `b0a3037401259471.vercel-dns-016.com` |

`www.xward.app` 用 308 跳到 `xward.app`。这不在代码里，是 Vercel 项目 Settings > Domains 里的配置。证书由 Vercel 自动签发和续期。
