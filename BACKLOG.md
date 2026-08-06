# penkeep_website — backlog

Deferred tasks for the penkeep.com site / hosting.

## Domain verification (GitHub Pages, for the Cloudflare-proxied setup)
Verify `penkeep.com` at the account level so GitHub trusts it even when Cloudflare's
orange-cloud proxy fronts it (otherwise GitHub's periodic DNS check sees Cloudflare IPs
and can flag the custom domain as misconfigured / risk domain takeover).
- GitHub → Settings → Pages → **Verify a domain** → add the `_github-pages-challenge-okoker`
  **TXT** record it gives you to Cloudflare DNS → click Verify.
- Safe to keep the proxy on (grey-cloud not required for verification).

## Public reference docs (5 links still 404)
`okoker/penkeep` stays **private** by decision, so every site link pointing into it dead-ends for
visitors. The download links are fixed (binaries are static files under `download/<tag>/`); these
five still need a public target, and each wants a document written for an outside reader — not a
copy-paste of the private repo's internal docs:
- **Threat model** — footer *Threat model*, and the Security section's
  *"Read exactly what Phase 1 protects →"*. Needs the real scope: what the `.emd` format protects
  (XChaCha20-Poly1305 + Argon2id + zstd, per-file passphrases, no master key) and what it does
  **not** — the decrypted-plaintext-in-memory residue limits the site already claims are published,
  plus unsigned/un-notarized builds. The site's own copy says *"we don't oversell it"*, so this
  page is load-bearing for that claim.
- **CLI docs** — footer *CLI docs*. `crates/emd-cli` exists and is the second consumer of the
  format; document the commands and the file format enough for someone to decrypt their own `.emd`
  without the app. This is the strongest answer to "what if penkeep disappears".
- **Bare *GitHub* links** — nav and footer. There is no public source repo to point at, so either
  drop them, or point them at whatever public doc repo the two items above land in.

Decide the venue first: a `docs/` tree in `penkeep_website` (simplest, renders on Pages) vs. a
separate public repo. Everything above follows from that choice.

## OG social image
No `og.png` yet — `index.html` references `https://penkeep.com/og.png` for OG/Twitter cards,
so link previews are text-only. Add a 1200×630 image in the Cipher style and drop it at the
site root.
