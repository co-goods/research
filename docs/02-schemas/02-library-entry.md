---
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-21T22:19
---

# Library Entry Shape

Library entries describe bibliographic items — books, papers, podcasts, articles, videos, courses, posts. The shape is unified across all types; a `type:` discriminator handles per-type fields.

## When to add a library entry

Add a library item when it should be available to cite, recommend, or feature on the site. The rule is **in the repo = has a serial**: every item in `resources/library/` carries an `l-#####` serial assigned at the moment it's promoted from any external shelf into the repo. Items kept externally but not yet promoted do not have a serial.

The `resources/library/INDEX.md` file is the registry of assigned serials. Pick the next unused one when adding a new entry, then update the index.

## Type discriminator

```yaml
type: book | paper | podcast-episode | article | post | video | course
```

The type determines which subset of bibliographic fields is meaningful. A paper carries `journal`, `volume`, `issue`, `doi`; a book carries `publisher`, `isbn`, `edition`; a podcast-episode carries `podcast`, `episode-number`, `host`; etc.

## Role flags

Two universal flags describe the item's role within the project:

- `is-cited: true` — the item appears as a source on at least one observation, insight, or other research artifact.
- `is-featured: true` — the item is promoted on the public library page as recommended reading.

Both, either, or neither can be true. The role is independent of whether the item has a serial (every repo entry has one).

## Authors and publishers

- `authors:` references slugs in `people/` (bare slugs in the array; the `people/` prefix is implicit).
- `publisher:` references a slug in `resources/library/publishers/`.
- `publication:` references a slug in `resources/library/publications/` (the journal, podcast, magazine, etc.).

People, publishers, and publications are themselves first-class entries — they have their own pages and can backlink to every library item that references them.

## Minimum frontmatter

```yaml
---
slug: <lastname-headline-words>
serial: l-#####
status: active
stage: published
type: paper
title: <full title>
authors: [<person-slug>]
publication-date: <YYYY-MM-DD>
publication: <publication-slug>
publisher: <publisher-slug>
is-cited: false
is-featured: false
created: <YYYY-MM-DD>
updated: <YYYY-MM-DD>
---
```

## Body conventions

The body is for human-readable summary, key claims, relevance to Co-Goods, and quoted excerpts where useful. Wikilink to other library items, people, and topics where the connections matter.
