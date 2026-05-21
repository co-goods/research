---
created: 2025-09-11
updated: 2026-05-21T22:17
---

# Co-Goods Research — Taxonomy and Conventions

How content is organised in `co-goods/research`. The authoritative reference for collection structure, file naming, frontmatter conventions, and wikilinks.

## Collections

| Collection | Voice / role | URL |
|---|---|---|
| `library/` | Bibliographic records (books, papers, podcasts, articles, videos, courses, posts) | `/library/<slug>` |
| `library/publishers/` | Publishing organisations | `/library/publishers/<slug>` |
| `library/publications/` | Channels (journals, podcasts, etc.) | `/library/publications/<slug>` |
| `wiki/` | Neutral, encyclopedic, open contribution | `/wiki/<slug>` |
| `essays/` | POV writing by any contributor; includes model write-ups | `/essays/<slug>` |
| `reports/` | Versioned formal compilations (lightpaper, whitepaper, position-paper, model-paper) | `/reports/<slug>` (latest); `/reports/<slug>/<version>` (specific) |
| `observations/` | External signals from the world (data points, trends, cases, field findings, interview notes) | `/observations/<slug>` |
| `insights/` | Atomic research findings synthesised from observations and/or library sources | `/insights/<slug>` |
| `hypotheses/` | Testable predictions in "if [condition], then [outcome]" form | `/hypotheses/<slug>` |
| `glossary/` | Dictionary-schema term entries | `/glossary/<slug>` |
| `blog/` | Chronological project narrative | `/blog/<slug>` (URL flattened from `blog/<year>/<month>/<slug>.md`) |
| `people/` | Unified profiles (authors, contributors, editors, designers, reviewers, external) | `/people/<slug>` |
| `tags/` | Operational labels | `/tags/<slug>` |

Plus auto-generated `/topics/<slug>` aggregation pages where a slug spans 2+ collections.

## Epistemic chain (observation → insight → hypothesis)

The repo models a simple chain for traceability:

```
observations → insights → hypotheses
```

- **Observations** capture external signals from the world. They ground in `sources` (library items) where evidence comes from.
- **Insights** synthesise from observations and/or library sources. **Every insight must have at least one upstream link** — either `observations:` (when synthesising signals) or `sources:` (when extending a published source). Both can be populated, neither can be empty.
- **Hypotheses** build on insights as testable predictions, with a `validation-status` lifecycle: `pending | validated | invalidated | revised`.
- **Decisions** are not a collection in this repo — they live in per-project files or in concept-canon docs elsewhere.

## File naming

- **Flat `.md` files everywhere** with the filename matching the slug (e.g. `library/olleros-antirival-goods.md`). No `SOURCE.md` / `AUTHOR.md` / `REPORT.md` generic-inside-file naming.
- **Reports** are the sole folder-based exception: `reports/<slug>/<version>/<slug>.md` with per-version subfolders.
- **Blog** uses `blog/<year>/<month>/<slug>.md` for human file-tree navigation; the URL is flat.

## Slug rules

- Kebab-case, lowercase, hyphen-separated. No underscores.
- The `slug:` frontmatter field is **always the bare form** — never includes serials.
- For library: `<lastname>-<2–3 headline words>` (e.g. `olleros-antirival-goods`). Keep slugs short.
- For people: `<firstname-lastname>` (e.g. `f-xavier-olleros`).
- For glossary: base form canonical (`co-goods`, not `co-goodsing`); grammatical variants live under `classes[type=verb].forms` per the dictionary schema.

## Serials

Serials live in YAML frontmatter, not in filenames or folder names.

| Prefix | Used by | Notes |
|---|---|---|
| `l-#####` | **library items only** | Every library item in the repo gets one. Rule: **in repo = has a serial.** Items kept externally but not promoted into the repo have no serial. |

Other content types (people, tags, insights, observations, hypotheses, wiki, essays, reports, glossary, blog posts) do **not** use serials.

`library/INDEX.md` is the registry of assigned serials.

## Universal frontmatter fields

Where relevant:

- `status: active | inactive` — is this on the website?
- `stage: draft | published` — if active, draft (with WIP banner) or polished?
- `example: false` (default) — opt-in flag for dummy/test content; set `true` to mark content that exercises website templates without claiming research-domain status. The build can filter `example: true` items from production renders. Example library items use the `x-#####` serial namespace instead of `l-#####`; this keeps `l-00001+` reserved for the first curated library entries.

`status: active, stage: draft` is the canonical "publish drafts so the community can engage with them" pattern. Never use `stage: final` — use `stage: published`.

## Type discriminators

- **Library items**: `type: book | paper | podcast-episode | article | post | video | course`
- **Reports**: `type: lightpaper | whitepaper | position-paper | model-paper`
- **People**: `type: person`
- **Glossary**: `type: word | term | comparison`
- **Observations**: `type: observation`
- **Hypotheses**: `type: hypothesis` (with `validation-status: pending | validated | invalidated | revised`)
- **Tags / insights / wiki / essays / blog posts**: `type:` matches the collection name

## Wikilinks

Wikilinks use **qualified paths** (Obsidian-native slash syntax).

- `[[library/olleros-antirival-goods]]` → `/library/olleros-antirival-goods`
- `[[people/f-xavier-olleros|F. Xavier Olleros]]` → `/people/f-xavier-olleros` with custom display text
- `[[tags/antirival]]` → `/tags/antirival`
- `[[observations/...]]`, `[[hypotheses/...]]`, `[[insights/...]]`, `[[wiki/...]]`, `[[essays/...]]`, `[[glossary/...]]` — same pattern
- `[[topics/antirival]]` → `/topics/antirival` (an aggregation page)

**Bare wikilinks** (no slash):
- `[[antirival]]` → `/topics/antirival` **if a topic-aggregation page exists** (slug appears in 2+ collections).
- `[[antirival]]` with no topic page → **build error** (forces qualification).

**Frontmatter arrays** stay bare — collection is implicit from the field name:

```yaml
sources: [olleros-antirival-goods]              # implicit: library
observations: [observed-trend-slug]              # implicit: observations
authors: [pontus-karlsson]                       # implicit: people
tags: [antirival, network-effects]               # implicit: tags
```

## Current tag definitions

Brief definitions of tags currently in use:

- **antirival** — Goods that become more valuable with shared use
- **network-effects** — Value increases with user adoption
- **sharing-economy** — Platform-mediated resource sharing
- **commons** — Collectively managed shared resources
- **goods-theory** — Economic classification frameworks
- **nonrival** — Goods that can be consumed by multiple people simultaneously without depletion
- **co-goods** — The Co-Goods framework

(Tag categorisation/taxonomy is deferred for now — revisit if filtering needs emerge.)

## Templates

See `templates/` for per-collection schemas. Each v1 template includes an inline `<!-- schema notes -->` block documenting required and optional frontmatter fields and file location conventions.

## License and contributing

See `LICENSE` (CC BY-SA 4.0) and `CONTRIBUTING.md` (PR-based contribution flow; inbound = outbound license; asset handling).
