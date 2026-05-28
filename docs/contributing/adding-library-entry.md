---
template: doc
template_version: 1.0.0
collection: contributing
slug: adding-library-entry
title: "Adding a library entry"
description: "How to add a book or paper to the library, with its publisher and publication."
order: 20
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-28
---

# Adding a library entry

You want to add a book or paper to the library — either because you're going to cite it in research, or because you want to recommend it on the public library page. This is the how-to; for the field-by-field shapes see `schemas/library-entry`.

## Decide whether it belongs in the repo

The library has a hard rule: **in the repo = has a serial**. So every book or paper you add commits to the `l-#####` namespace and to the `resources/library/INDEX.md` registry. Items that live only on an external shelf — your reading list, a Zotero collection, a private file share — don't need to be promoted.

Promote an item when:

- It's about to be cited in an observation, insight, or essay.
- It's an editorial pick for the public library page.
- It's a foundational reference you want to preserve in the canon, even before citation.

## Pick the right template

There's no single library template. Pick by entity:

- A **book** → `templates/template-book-v1.0.0.md`, lands in `resources/library/books/<slug>.md`.
- A **paper** → `templates/template-paper-v1.0.0.md`, lands in `resources/library/papers/<slug>.md`.

Copy the latest template for that entity — it documents its own fields inline. The item declares `template: book` (or `paper`), `template_version`, and `collection: books` (or `papers`); there is no `type:` field. See `conventions/frontmatter` for the universal contract.

## Pick the next serial

Open `resources/library/INDEX.md`, find the highest assigned `l-#####`, and use the next number. Add a row to the index for your new entry — serial, title, slug, entity, authors — before writing the entry itself. Placeholder or example content uses the `x-#####` namespace instead, so the curated numbering stays clean.

## Add the carriers and authors

Books and papers reference other entries by slug, and those entries should exist:

- **Authors** → `people/<slug>.md`. If the entry references authors not yet in `people/`, add their profiles first, or in the same PR.
- **Publisher** (books) → `resources/library/publishers/<slug>.md`, using `templates/template-publisher-v1.0.0.md`. Reference it as `publisher: <slug>`.
- **Publication** (papers) → `resources/library/publications/<slug>.md`, using `templates/template-publication-v1.0.0.md`. Reference it as `publication: <slug>`.

Publishers and publications are first-class entries with their own pages — adding them once lets every book or paper that cites them backlink automatically.

## Set the role flags

Set `is-cited` and `is-featured` thoughtfully:

- `is-cited: true` — set when at least one observation, insight, or essay references this entry in its `sources:` field.
- `is-featured: true` — set when this entry should appear on the public library page as recommended reading. Independent of citation status.

It's fine to add an entry with both flags `false` — it sits in the registry, ready to be cited or featured later.

## Submitting

Open a PR with the new entry, the updated `resources/library/INDEX.md`, and any supporting people, publisher, or publication entries. The preview deploy lets you check the rendering before merging.

## Other library entities

Only books and papers (plus their publishers and publications) have templates today. Podcasts, podcast episodes, articles, videos, courses, and posts are planned but not yet built — each gets its template and collection when the first real item lands. If you're adding one of those, that's a template-authoring step first; flag it rather than forcing the content into a book or paper shape.
