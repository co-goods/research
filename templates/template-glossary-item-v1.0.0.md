---
template: glossary-item
template_version: 1.0.0
slug: ""
name: ""
classes: []
relationships:
  related_terms: []
links: []
sources: []
status: active
created: "{{date}}"
updated: "{{date}}"
---

# {{name}}

<!--
Glossary item schema (template: glossary-item, v1.0.0).

Co-Goods adopts the DePalma Workshop Dictionary Schema (CC BY-SA 4.0) as the
contract for glossary entries. Start with this minimal subset; grow into
richer fields (comparisons, multiple grammatical classes, aliases, acronyms)
as content matures.

Required (MVP subset):
- File location: `resources/glossary/<slug>.md`
- `slug`: bare kebab-case, **base form** (e.g. `co-goods`, not `co-goodsing`)
- `name`: display form
- `classes`: list of grammatical classes with definitions. Example:

    classes:
      - type: noun
        definitions:
          - "A class of goods designed for shared use that ..."
      - type: verb
        forms:
          present: co-goodsing
          past: co-goodsed
        definitions:
          - "To do ..."

  The inner `classes[].type` is the grammatical class (noun / verb / adjective / …).

- `relationships.related_terms`: slugs of related glossary items

Optional (richer dictionary fields — see schema reference):
- `aliases`, `acronyms`, `comparisons`, `usage`, `register`

Reference: DePalma Workshop Dictionary Schema (Google Drive). Base form is
canonical; grammatical variants live under `classes[type=verb].forms`.
Cross-enterprise compatibility (the future MCC Supabase glossary uses the
same schema) is the reason we adopt it now even though many fields are
unused at MVP.
-->
