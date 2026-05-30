---
template: doc
template_version: 1.0.0
collection: conventions
slug: licensing
title: "Licensing"
description: "How content here is licensed, how to set a different license on an item or media, and how we treat works we only reference."
order: 80
status: active
stage: draft
created: 2026-05-30
updated: 2026-05-30
---

# Licensing

How content on this site is licensed, how to declare a different license on a specific item, and how we handle material that isn't ours.

Licensing here isn't one-size-fits-all — different kinds of material carry different licenses, on purpose:

- **The knowledge we write** — wiki, glossary, essays, research — is a shared commons, licensed so it stays open.
- **Media** (images, video) carries its own license, independent of the text around it.
- **Works we only reference** (books, papers, and so on in the library) keep their own rights — we don't relicense them.
- **Code** is licensed separately from content.

## The default: CC BY-SA 4.0

Original first-party content — the prose we author: wiki articles, glossary entries, essays, research — defaults to the **Creative Commons Attribution-ShareAlike 4.0 International** license (CC BY-SA 4.0).

The default is stated once — in the repository's [`LICENSE`](../../LICENSE), the site footer, and [`CONTRIBUTING.md`](../../CONTRIBUTING.md) — so you don't repeat it on every file. Share-alike means anyone may reuse and adapt the work, including commercially, as long as they credit it and license their adaptation under the same terms. That's what keeps the commons a commons.

## Per-collection notes

- **Wiki, glossary, research** — CC BY-SA 4.0. These are the shared reference layer; share-alike is the point.
- **Essays / thinking** — default to CC BY-SA 4.0, but because these are points of view (sometimes from guest authors), an individual essay may carry its own license via the override below.

## Overriding the default on one item

To license a single item differently, set `license:` (and optionally `license_url:`) in its frontmatter. Absent = the item inherits the default. This is for the occasional piece under a different, compatible license, or content with a specific provenance. See [`frontmatter.md`](./frontmatter.md) for the field — the value is an SPDX identifier (e.g. `CC-BY-4.0`).

## Media carries its own license

Images and video are licensed **independently** of the item they appear in — an embedded video carries the platform's or creator's terms; a photo carries its own. Declare a media license on the `image` / `video` block, not in the item frontmatter — see [`media.md`](./media.md). Media you didn't create must carry a credit and a license that permits the use.

## Works we reference (the library)

A library entry describes a book, paper, or other work. Two things stay separate:

- **Our record and commentary** — the entry we write *about* the work — is first-party content under the default license.
- **The work itself is untouched.** Cataloguing, summarising, citing, or featuring a work asserts no license over it. Quoted excerpts are fair-use citation, not relicensing.

### Redistributing a referenced work

- **Linking is always fine** — a link is a reference, not a copy.
- **Hosting or redistributing the work itself** is only OK when the work is **openly licensed** (e.g. Creative Commons, public domain) and you follow its terms.
- "Freely readable on someone's site" is **not** the same as "openly licensed" — check the actual license before re-hosting anything.
- When in doubt: **link, don't host.**

## Code is separate

CC BY-SA 4.0 governs *content*. The website's code carries its own license — see that repository. Content licensing and code licensing are independent.

## Contributing your own work

When you contribute, the contribution terms are in [`CONTRIBUTING.md`](../../CONTRIBUTING.md). In short: contribute work that is yours to contribute, make sure any media or third-party material you include is properly licensed for the use, and credit sources.

## Not legal advice

This describes how we license and reuse material on this site; it is not legal advice. For anything load-bearing, check with a qualified professional.
