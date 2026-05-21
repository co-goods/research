---
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-21T22:18
---

# Frontmatter Conventions

How YAML frontmatter is structured across the collections in this repo. Each collection has a small per-type schema on top of a shared set of universal fields.

## Universal fields

Every content item carries these where relevant:

- `status: active | inactive` — controls whether the item appears on the site at all.
- `stage: draft | published` — when active, whether the page shows a WIP banner.
- `created` and `updated` — ISO dates. `created` is set at file creation and never changes; `updated` reflects the last meaningful revision.
- `example: false` — opt-in flag for dummy / test content used to exercise the website's templates without claiming research-domain status.

### `status` vs `stage`

`status: active, stage: draft` is the canonical "publish your work-in-progress so the community can engage with it" pattern. The page is reachable, the URL is stable, and a WIP banner indicates the content isn't final.

Never use `stage: final` — the terminal stage label is `published`.

## Per-collection extensions

Each collection extends the universal fields with type-specific ones. The authoritative reference is the matching template under `templates/`.

### Library

Library items carry a `serial` (`l-#####`), a `type` discriminator (`book | paper | podcast-episode | article | post | video | course`), bibliographic fields (`authors`, `publication-date`, `publisher`, etc.), and role flags (`is-cited`, `is-featured`).

### People

Profiles carry `affiliation` (`co-goods-team | depalma-pilot | external-author | unclaimed`) plus optional integration fields (`account-status`, `clerk-id`, `links`) reserved for future "claim this profile" support.

### Reports

Reports use `type: lightpaper | whitepaper | position-paper | model-paper` plus version-specific fields inside each version folder.

## Example

```yaml
---
slug: example-insight
status: active
stage: published
type: insight
created: 2026-05-01
updated: 2026-05-21
observations: [weekend-readership-spike]
sources: [smith-network-coordination-2022]
tags: [coordination, network-effects]
---
```

The matching templates under `templates/` show the full set of available fields per collection.
