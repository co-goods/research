---
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-21T22:19
---

# Glossary Schema

Glossary entries use the DePalma Workshop Dictionary Schema as their YAML frontmatter contract — a shared dictionary shape used across enterprises.

## Why a shared schema

The dictionary schema handles linguistic complexity that simple "term + definition" structures miss: acronyms, aliases, multiple grammatical classes, definitions per sense, related terms, comparisons. Sharing the schema across enterprises means a glossary entry written here is structurally compatible with a future cross-enterprise dictionary surface (Supabase-backed or otherwise) without rewrites.

The schema is open-licensed (CC BY-SA 4.0), which matches Co-Goods's own licensing.

## Base form canonical

The entry filename and `slug` use the base form of the term. Grammatical variants (verb forms, plurals, adjective forms) live inside the entry, not as separate files.

- `glossary/co-goods.md` — base form
- `co-goodsing` (verb), `co-goodser` (noun-agent), etc. — declared inside the entry's `classes[type=verb].forms` block, **not** as separate glossary entries.

## Minimum frontmatter

```yaml
---
slug: <kebab-case-base-form>
status: active
stage: draft
type: word | term | comparison
name: <human-readable form>
classes:
  - type: noun | verb | adjective | adverb
    definitions:
      - <definition text>
related_terms:
  - <other-glossary-slug>
created: <YYYY-MM-DD>
updated: <YYYY-MM-DD>
---
```

## Richer fields

As entries mature, additional fields from the dictionary schema become useful — acronym expansion, aliases, per-sense definitions, etymology, comparison-target slugs (for entries that explicitly contrast two terms), example sentences.

Start minimal; grow the entry as the term's usage pattern stabilises.

## Body conventions

The markdown body below the frontmatter is for prose discussion — context, history, why the term matters to Co-Goods, references to library items via wikilinks. Treat the frontmatter as the structured contract and the body as the human-readable elaboration.
