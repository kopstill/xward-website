# xward-website

The page at [xward.app](https://xward.app) for Xward, an iPhone countdown app.

Vercel serves the static files in `public/` as they are, with no build step. A push to `main` deploys to production.

To preview the page locally, open `public/index.html` in a browser.

The screenshots in `public/screens/` show the real app with sample data. Retake them when the app's interface changes. Each one is an sRGB JPEG, 804 pixels wide.

`public/favicon.svg` is the source of the site's icons. `favicon.ico` (16, 32, and 48 pixels) and `apple-touch-icon.png` (180 pixels, with square corners) are exported from it, so export them again when it changes.

## Domain

The domain is registered with Cloudflare, which requires its own name servers, so the DNS records stay there. Cloudflare holds only these three records, all set to DNS only, with the proxy off. Their values come from the domain settings of the Vercel project.

| Type | Name | Content |
| --- | --- | --- |
| `A` | `@` | `216.150.1.1` |
| `A` | `@` | `216.150.16.1` |
| `CNAME` | `www` | `b0a3037401259471.vercel-dns-016.com` |

`www.xward.app` redirects to `xward.app` with a 308 status. This redirect isn't in the code; it's set in the Vercel project under **Settings** > **Domains**. Vercel issues and renews the certificate automatically.
