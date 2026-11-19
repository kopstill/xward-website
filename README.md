# xward-website

The page at [xward.app](https://xward.app) for Xward, an iPhone countdown app.

Vercel serves the static files in `public/` as they are, with no build step. A push to `main` deploys to production.

To preview the site locally, serve `public/` with a static server, such as `python3 -m http.server --directory public`, and open <http://localhost:8000>. The privacy policy and support pages use paths from the site root, so they need the server.

`public/privacy/` is the privacy policy and `public/support/` the support page. The App Store listing links to both, and the app's settings link to the privacy policy, so keep their addresses. The two pages share `public/page.css`; the home page keeps its styles inline. When the privacy policy's content changes, update its effective date.

The screenshots in `public/screens/` show the real app with sample data. Retake them when the app's interface changes. Each one is an sRGB JPEG, 804 pixels wide.

`public/favicon.svg` is the source of `favicon.ico` (16, 32, and 48 pixels), so export the ICO again when the SVG changes. Its hourglass is deliberately 1.3 times the size of the app icon's.

`public/logo.svg` and `public/apple-touch-icon.png` (180 pixels, with square corners) follow the app icon, so update both when it changes. `logo.svg` adds rounded corners and a hairline edge that keeps its shape visible on the dark page.

## Domain

The domain is registered with Cloudflare, which requires its own name servers, so the DNS records stay there. The website needs these three records, all set to DNS only, with the proxy off. Their values come from the domain settings of the Vercel project. Cloudflare Email Routing, which forwards `hello@xward.app`, adds and manages its own mail records.

| Type | Name | Content |
| --- | --- | --- |
| `A` | `@` | `216.150.1.1` |
| `A` | `@` | `216.150.16.1` |
| `CNAME` | `www` | `b0a3037401259471.vercel-dns-016.com` |

`www.xward.app` redirects to `xward.app` with a 308 status. This redirect isn't in the code; it's set in the Vercel project under **Settings** > **Domains**. Vercel issues and renews the certificate automatically.
