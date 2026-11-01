# xward-website

The page at <https://xward.app> for Xward, an iPhone countdown app. This repository is public. The app's own repository is private.

- Files under `public/` are served as they are, with no build step. A push to `main` deploys to production on Vercel.
- The page's claims come from the app's recorded decisions, in `docs/decisions.md` of the app's repository, which is at `../Xward` on the developer's machine. Check them before you change the copy.
- Keep everything else from the app's repository out of this one, including decision IDs and internal notes.
- The page loads no external resources and has no analytics.
