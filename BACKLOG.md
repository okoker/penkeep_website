# penkeep_website — backlog

Deferred tasks for the penkeep.com site / hosting.

## Domain verification (GitHub Pages, for the Cloudflare-proxied setup)
Verify `penkeep.com` at the account level so GitHub trusts it even when Cloudflare's
orange-cloud proxy fronts it (otherwise GitHub's periodic DNS check sees Cloudflare IPs
and can flag the custom domain as misconfigured / risk domain takeover).
- GitHub → Settings → Pages → **Verify a domain** → add the `_github-pages-challenge-okoker`
  **TXT** record it gives you to Cloudflare DNS → click Verify.
- Safe to keep the proxy on (grey-cloud not required for verification).

## Public downloads (currently broken)
The Download section links to `github.com/okoker/penkeep/releases`, which is now a **private**
repo → 404 for visitors, and the app binaries aren't publicly downloadable. Fix:
- Publish release binaries to **`penkeep_website`** releases (or **Cloudflare R2**), and
- Repoint the site's download buttons + the release-API fetch in `index.html` accordingly.

## OG social image
No `og.png` yet — `index.html` references `https://penkeep.com/og.png` for OG/Twitter cards,
so link previews are text-only. Add a 1200×630 image in the Cipher style and drop it at the
site root.
