---
status: active
stage: draft
created: 2026-05-21
updated: 2026-05-21T22:20
---

# Adding a Library Entry

When you want to add a book, paper, podcast, or other reference to the library — either because you're going to cite it in research, or because you want to recommend it on the public library page.

## Decide whether it belongs in the repo

The library has a hard rule: **in the repo = has a serial**. So every entry you add commits to the `l-#####` namespace and to the `library/INDEX.md` registry. Items that live only on an external shelf (your reading list, a Zotero collection, a private file share) do not need to be promoted.

Promote an item when:

- It's about to be cited in an observation, insight, or essay.
- It's an editorial pick for the public library page.
- It's a foundational reference you want to preserve in the canon, even before citation.

## Pick the next serial

Open `library/INDEX.md`, find the highest assigned `l-#####`, and use the next number. Add a row to the index for your new entry (slug, serial, type, brief title) before writing the entry itself.

## Write the entry

Create `library/<slug>.md` using the template in `templates/template-library-v1.md`. Fill in the bibliographic fields appropriate to the type (paper, book, podcast-episode, etc.) — see `docs/schemas/library-entry` for the per-type field guide.

### People, publishers, publications

If the entry references authors not yet in `people/`, add their profiles first (or in the same PR). Same for publishers and publications. The library entry's frontmatter references those slugs.

## Role flags

Set `is-cited` and `is-featured` thoughtfully:

- `is-cited: true` — set when at least one observation / insight / essay references this entry in its `sources:` field.
- `is-featured: true` — set when this entry should appear on the public library page as recommended reading. Independent of citation status.

It's fine to add an entry with both flags `false` — it sits in the registry, ready to be cited or featured later.

## Submitting

Open a PR with the new entry, the updated `library/INDEX.md`, and any supporting people / publisher / publication entries. The Vercel preview deploy lets you check the rendering before merging.
