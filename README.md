# penkeep_website

Marketing site for **[penkeep.com](https://penkeep.com)** — Penkeep, a local-first
WYSIWYG markdown editor with first-class comments and per-file encryption.

Static site (single `index.html`, inline CSS/JS, Google Fonts via CDN). Deployed to
GitHub Pages from `main` (root). The Penkeep application itself is developed in a
separate repository and its source is not published.

## Downloads

Release binaries are plain static files under `download/<tag>/`, served at
`https://penkeep.com/download/<tag>/<asset>`. The last **3** versions are kept.

- `download/releases.json` — what `index.html` reads to build its download links.
- `releases.html` — notes, downloads and SHA-256 checksums for every kept version.

**This repo deliberately has no GitHub releases and no tags.** GitHub attaches
"Source code" archives to every release and provides no way to suppress them, and
Penkeep is not open source — so downloads are served as files instead. Please don't
add a release here; add a folder, update those two files, and push.

Built on prior work from [gutter](https://github.com/davidrigie/gutter) by David Rigie (MIT).
