---
template: doc
template_version: 1.0.0
collection: ""
slug: ""
title: ""
description: ""
order: 10
status: active
created: "{{date}}"
updated: "{{date}}"
---

# {{title}}

{{description}}

## ...sections...

<!--
Doc article schema (template: doc, v1.0.0).

- File location: `docs/<collection>/<slug>.md` (or `docs/<collection>/<sub-collection>/<slug>.md` for sub-collections)
- `collection`: the collection's path within docs — e.g. `conventions`, `conventions/naming`, `schemas`. Required; matches a registered collection in the website registry.
- `slug`: bare kebab-case (filename minus `.md`)
- `description`: one-line summary used in sidebar entries and listing pages
- `order`: sort position among siblings in the collection (in 10s, leaving room to insert)

A doc article can live directly in a collection (`docs/conventions/<slug>.md`)
or in a sub-collection (`docs/conventions/naming/<slug>.md`). Sub-collections
share the parent's template; items declare the full collection path.

The website derives sidebar trees and prev/next navigation from folder
structure + `order:`. No `parent:`, `chapter:`, or `sidebar:` field — the
position in the structure is the relationship.
-->
