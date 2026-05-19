---
slug: library-index
type: index
status: active
created: 2026-05-19
updated: 2026-05-19T20:51
---

# Library Index

Metadata for items in the Co-Goods library. Serials are assigned on entry to the repo — every library item has one (`in repo = has a serial`). The full record is in each item's `.md` file; this index is the at-a-glance view.

See the architecture decisions behind this collection in
[`p-002-website-v1/staging/architecture-review-log.md`](../) (D3, D4 — outside the repo)
and the promoted ADRs (ADR-004, ADR-005, ADR-007).

## Items

| Serial | Title | Slug | Type | Authors | Year | Cited | Featured | Added by | Added |
|---|---|---|---|---|---|---|---|---|---|
| l-00001 | Antirival goods, network effects and the sharing economy | olleros-antirival-goods | paper | [[people/f-xavier-olleros\|F. Xavier Olleros]] | 2018 | ✓ | ✓ | [[people/pontus-karlsson\|Pontus Karlsson]] | 2026-05-19 |

## Columns

- **Serial** — `l-#####` (zero-padded; assigned on entry to repo)
- **Title** — display title
- **Slug** — bare slug (for grep / wikilink)
- **Type** — `book` / `paper` / `podcast-episode` / `article` / `post` / `video` / `course`
- **Authors** — `[[people/<slug>|Display Name]]` wikilink
- **Year** — for sorting; matches the item's `year:` frontmatter
- **Cited** — ✓ if `is-cited: true`, empty otherwise
- **Featured** — ✓ if `is-featured: true`, empty otherwise
- **Added by** — the Co-Goods contributor who curated this entry into the repo (wikilink to `people/`)
- **Added** — ISO date (`YYYY-MM-DD`) when added to the repo
