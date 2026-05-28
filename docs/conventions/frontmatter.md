---
template: doc
template_version: 1.0.0
collection: conventions
slug: frontmatter
title: "Frontmatter contract"
description: "The universal frontmatter contract every authored file carries."
order: 20
status: active
stage: draft
---

# Frontmatter contract

Every authored file in the Co-Goods content repo (and the website's `pages/` and `overlays/` folders) carries a YAML frontmatter block. This doc defines the **universal contract** — the fields every item must have — and points to where per-template schemas are defined.

## Universal fields

Every content item (file in a collection) declares at minimum:

```yaml
---
template: <entity name>           # the schema this item follows
template_version: 1.0.0           # semver matching the template
collection: <collection name>     # which collection this item belongs to
title: "..."                      # human-readable title
---
```

That's the universal contract. Every item, in every collection, carries these four fields.

### `template:`

The name of the schema/template this item follows. Singular entity name:

- `essay`, `wiki-article`, `glossary-item`, `book`, `paper`, `publisher`, `publication`, `observation`, `insight`, `hypothesis`, `person`, `tag`, `blog-post`, `doc`, `lightpaper`, `whitepaper`, …

Matches the template filename `templates/template-<entity>-v<version>.md`.

### `template_version:`

The semver version of the template the item was authored against. Matches the version in the template's filename and frontmatter (e.g., `1.0.0`).

This is a back-reference — the renderer uses it to dispatch on version; migration scans grep for it; humans use it to know what schema applies.

### `collection:`

The collection this item belongs to. Matches a registered collection in the website's registry.

For flat collections, just the leaf: `essays`, `books`, `papers`, `wiki`, `people`, `tags`, …

For sub-collections of a nested collection, the full path: `conventions/naming`, `conventions/frontmatter`, …

URL navigation prefixes (`resources/`, `docs/`, etc.) don't appear here — they're presentation, not identity.

See `taxonomy.md` for the model.

### `title:`

Human-readable title. Required by most templates. A few use `name:` instead (glossary items, people, tags, organisations) — see the template's schema notes.

## Per-template fields

Each template defines additional required and optional fields specific to its content type. The authoritative reference for those is each template's own schema-notes block at `templates/template-<entity>-v<version>.md`.

Examples of per-template fields:

- **Essay**: `authors`, `summary`, `tags`, `publishedAt`, `status`, `stage`, …
- **Book**: `authors`, `year`, `publisher`, `isbn`, `language`, …
- **Person**: `name`, `affiliation`, `bio`, `github`, `email`, `expertise`, …
- **Insight**: `authors`, `observations`, `sources`, `tags`, `key_findings`, `implications`, …
- **Doc**: `description`, `order`, …

When starting a new item, copy the latest template — it documents its own schema inline.

## Common patterns across templates

Several optional patterns appear in multiple templates:

### `tags:`

Many content types accept tags — a list of bare slugs referring to entries in the `tags` collection:

```yaml
tags:
  - antirival
  - network-effects
  - sharing-economy
```

### `summary:`

A one- or two-sentence summary used in listings, search results, and as a meta description. Common on essays, insights, observations, hypotheses, wiki articles, library entries.

### `status:` and `stage:`

For draft / work-in-progress content:

```yaml
status: active
stage: draft       # or "polished" / "published"
```

The website renders a WIP banner on items with `stage: draft`. Cross-collection convention; check each template's notes for specifics.

### `example: true`

For placeholder content used to exercise the website's templates without claiming research-domain status:

```yaml
example: true
```

The website may filter `example: true` content from production renders.

### `created:` and `updated:`

ISO date strings for the item's creation and last update. Optional but recommended:

```yaml
created: 2026-05-21
updated: 2026-05-27
```

## Cross-cutting templates

Composed pages, overlays, and plain pages declare `template:` + `template_version:` but no `collection:` (they're not items in a content collection):

A composed page (home, about, custom collection page):

````markdown
---
template: composed-page
template_version: 1.0.0
title: "About Co-Goods"
---

```hero
variant: gradient
title: About Co-Goods
subtitle: …
```

```prose
```
## Project overview

…body…
````

An overlay (splice fragment):

````markdown
---
template: overlay
template_version: 1.0.0
title: "Overlay — On Collaboration"   # optional; for human reference
---

```callout
name: editor-note
region: top
position: top
type: info
title: Editor's note
```
This essay is an early placeholder — shared so the community can engage as the thinking develops.
````

A plain-markdown standalone (manifesto, contributing):

```yaml
---
template: plain-page
template_version: 1.0.0
title: "Co-Goods Manifesto"
---

# {{title}}

Body content as plain markdown.
```

## Examples — full items

A wiki article:

```yaml
---
template: wiki-article
template_version: 1.0.0
collection: wiki
title: "Network Coordination"
summary: "Patterns and mechanisms by which distributed participants align their actions across a network without central direction."
tags:
  - coordination
  - network-effects
status: active
stage: draft
---

# Network Coordination

Body content as plain markdown.
```

An insight:

```yaml
---
template: insight
template_version: 1.0.0
collection: insights
title: "Engagement Density Predicts Coordination Quality in Asynchronous Networks"
summary: "When participation is asynchronous, engagement DENSITY (concentration per unit time) matters more than total engagement volume for coordination quality."
authors:
  - jane-doe
observations:
  - expert-interview-pattern
  - weekend-readership-spike
sources:
  - smith-network-coordination-2022
tags:
  - coordination
  - network-effects
status: active
stage: draft
---

# {{title}}

…body…
```

A doc article in a sub-collection:

```yaml
---
template: doc
template_version: 1.0.0
collection: conventions/naming
title: "Slug rules"
description: "How content slugs are formed and validated."
order: 20
---

# Slug rules

…body…
```

A book (in the `books` flat collection, presented under `/resources/library/books/`):

```yaml
---
template: book
template_version: 1.0.0
collection: books
title: "Systems Thinking for the Curious"
authors:
  - jane-doe
year: 2019
publisher: example-press
isbn: "978-0-12345-678-9"
language: en
tags:
  - coordination
  - sharing-economy
---

# Notes / annotations on the book

…body…
```

## Related conventions

- **Taxonomy** (collections, items, templates): see `taxonomy.md`.
- **Templates and versioning** (semver, archive workflow): see `templates-and-versioning.md`.
- **Slug rules and file naming**: see `file-naming.md`.
