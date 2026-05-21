---
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-21T22:18
---

# File Naming

Filenames in `co-goods/research` follow a small set of conventions so paths stay greppable, editor tabs stay self-describing, and URLs derive cleanly from the filesystem.

## Slugs

Slugs are the canonical identifier for any content item.

- **Kebab-case, lowercase, hyphen-separated.** No underscores.
- **No serial prefixes in the filename.** Serials live in YAML frontmatter (`serial: l-00001`).
- **Slug field is always the bare form.** Never embed serials, version numbers, or category prefixes in the `slug:` frontmatter value.

### Slug shape per collection

- **Library:** `<lastname>-<2–3 headline words>` — e.g. `olleros-antirival-goods`. Short, citation-flavoured.
- **People:** `<firstname-lastname>` — e.g. `f-xavier-olleros`. Hyphens between all name parts.
- **Glossary:** base form canonical (`co-goods`, not `co-goodsing`). Grammatical variants live inside the entry's classes block.
- **Other collections** (wiki, essays, observations, insights, hypotheses, blog, tags): topic-descriptive slug, 1–5 words.

## Flat files, with one exception

Every content item is a flat `.md` file whose filename matches its slug. **No** `SOURCE.md` / `AUTHOR.md` / `REPORT.md` generic-inside-file pattern.

### Reports — folder per version

Reports are the sole collection using folders:

```
reports/<slug>/
├── INDEX.md
├── v0.1/
│   ├── <slug>.md
│   └── assets/
└── v1.0/
    ├── <slug>.md
    └── assets/
```

Each version's `assets/` folder contains only assets new or updated at that version; the build's cascading resolver walks backward through prior versions for anything not local.

### Blog — folder-based for file-tree navigation

Blog uses `blog/<year>/<month>/<slug>.md` for human navigation when the file tree gets long. The URL flattens to `/blog/<slug>`.

## Ordering with numeric prefixes

Folders and files inside this `docs/` collection use a leading `NN-` prefix to control sidebar order. The URL strips the prefix:

- `docs/01-conventions/02-frontmatter.md` → `/docs/conventions/frontmatter`

Other collections do not use ordering prefixes. Sidebar / index ordering for them is alphabetic, chronological, or explicit (e.g. `library/INDEX.md`).
