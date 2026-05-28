---
template: doc
template_version: 1.0.0
collection: schemas
slug: library-entry
title: "Library entry shapes"
description: "The per-entity library templates (book, paper, publisher, publication) and the fields they share."
order: 20
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-28
---

# Library entry shapes

The library at `/resources/library/` collects bibliographic items — books, papers, and the publishers and publications that carry them. There is no single "library entry" shape: each entity has its own template, because a book and a paper and a publisher describe genuinely different things.

`library` is a **URL grouping**, not a collection. Underneath it are independent flat collections — `books`, `papers`, `publishers`, `publications` — each with its own template. See `conventions/taxonomy` for why this is a grouping of flat collections rather than one nested collection.

## The entity templates

| Collection | Template | Folder | Authoring scaffold |
|---|---|---|---|
| `books` | `book` | `resources/library/books/` | `templates/template-book-v1.0.0.md` |
| `papers` | `paper` | `resources/library/papers/` | `templates/template-paper-v1.0.0.md` |
| `publishers` | `publisher` | `resources/library/publishers/` | `templates/template-publisher-v1.0.0.md` |
| `publications` | `publication` | `resources/library/publications/` | `templates/template-publication-v1.0.0.md` |

Each template documents its own schema inline, in a comment block at the foot of the file. Copy the latest template when adding an item; this doc is the map, the template is the authoritative field list.

There is no `type:` discriminator. The template *is* the type — an item declares `template: book`, `template: paper`, and so on. See `conventions/frontmatter` for the universal contract every item carries (`template` + `template_version` + `collection`).

## Books and papers — the cited and featured items

Books and papers are the items you cite, recommend, or feature. They share most of their bibliographic shape and differ where the medium differs.

**Shared fields:** `slug`, `serial`, `title`, `authors`, `year`, `url`, `language`, `summary`, `our_take`, `key_points`, `methodology`, `relevance_to_project`, `is-cited`, `is-featured`, `added-by`, `tags`.

**Book-specific:** `publisher` (slug in `publishers/`), `isbn`.

**Paper-specific:** `publication` (slug in `publications/`), `volume`, `issue`, `doi`, `peer_reviewed`, `open_access`.

### Serials

Books and papers carry an `l-#####` serial. The rule is **in the repo = has a serial**: every book or paper promoted into the repo gets one, assigned from `resources/library/INDEX.md`. Items kept only on an external shelf — a reading list, a Zotero collection — have no serial until promoted. Example and placeholder items use the `x-#####` namespace so the curated `l-#####` numbering stays clean. See `conventions/file-naming` for serial rules.

### Role flags

Two universal flags describe an item's role in the project:

- `is-cited: true` — the item appears as a source on at least one observation, insight, or other research artifact.
- `is-featured: true` — the item is promoted on the public library page as recommended reading.

Both, either, or neither can be true. The role is independent of whether the item has a serial.

## Publishers and publications — the carriers

Publishers and publications are first-class entries, not just string fields on a book. They have their own pages and aggregate everything that references them.

- A **publisher** is an organisation — a press, a university press, an independent imprint. Books reference it by slug (`publisher: oxford-university-press`).
- A **publication** is a channel that carries items — a journal, magazine, podcast channel, newsletter. Papers reference it by slug (`publication: nature`). A publication can itself reference a `publisher`.

Both are lighter than books and papers: `slug`, `name`, a type field (`publisher_type` / `publication_type`, free text), `url`, `founded`, `description`, `status`. Neither carries a serial or role flags — those belong to the cited items, not the carriers.

## Authors

`authors:` on books and papers references slugs in `people/` — bare slugs in the array, the `people/` prefix implicit. People are first-class entries too: each person's page can backlink to every library item that references them. The same holds for publishers and publications — the relationship lives on the book or paper that cites them, and the carrier's page aggregates the backlinks.

## Future entities

The library will grow more entity templates as content lands. Each gets its own template and collection when first needed, following the same per-entity pattern: `podcast`, `podcast-episode`, `article`, `video`, `course`, `post`. They are deliberately not pre-built — the shape is easiest to get right against real content.

## Related conventions

- **Taxonomy** (why library is a grouping of flat collections): see `conventions/taxonomy`.
- **Frontmatter contract** (the universal fields): see `conventions/frontmatter`.
- **File naming and serials**: see `conventions/file-naming`.
- **Adding a library entry** (the how-to): see `contributing/adding-library-entry`.
