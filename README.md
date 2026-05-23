# Co-Goods — Research

Research content and documentation for the Co-Goods protocol — a system for co-created and networked physical products.

This repository is the content store; the website (`co-goods/website`) renders it via a submodule.

## Collections

- **resources/library/** — bibliographic records (books, papers, podcasts, articles, videos, courses, posts). Includes nested `resources/library/publishers/` and `resources/library/publications/`.
- **resources/wiki/** — neutral encyclopedic articles, open contribution.
- **thinking/essays/** — POV writing by any contributor; includes model write-ups.
- **research/reports/** — versioned formal compilations (lightpaper, whitepaper, position paper, model paper). Folder-per-version (`research/reports/<slug>/<version>/<slug>.md`).
- **research/observations/** — external signals from the world (data points, trends, cases, field findings, interview notes).
- **research/insights/** — atomic research findings synthesised from observations and/or library sources.
- **research/hypotheses/** — testable predictions in "if [condition], then [outcome]" form, with a validation-status lifecycle.
- **resources/glossary/** — dictionary-schema term entries.
- **blog/** — chronological project narrative.
- **people/** — unified profiles (authors, contributors, editors, designers, reviewers, external).
- **tags/** — operational labels.
- **templates/** — versioned templates for each collection.
- **docs/** — meta documentation about the repo (`taxonomy.md` lives here).
- **about.md** — project overview (renders on website).

## Content workflow

1. Use templates in `templates/` to create new content.
2. Save files in the appropriate collection (e.g. `resources/library/olleros-antirival-goods.md`).
3. For drafts, set `status: active, stage: draft` — the website shows a WIP banner.
4. When polished, set `stage: published`.
5. Content arrives on the website via the submodule.

See **CONTRIBUTING.md** for the PR-based contribution flow.

## Obsidian wikilinks

Write Obsidian-native qualified-path wikilinks:

```markdown
The [[tags/antirival]] concept by [[people/f-xavier-olleros|F. Xavier Olleros]],
introduced in [[resources/library/olleros-antirival-goods|Olleros (2018)]], shows how
[[tags/network-effects|network effects]] can drive open systems.
```

In frontmatter arrays, use bare slugs (collection is implicit from the field name):

```yaml
sources: [olleros-antirival-goods]
authors: [pontus-karlsson]
tags: [antirival, network-effects, sharing-economy]
```

## Current content

**Curated:**
- **1 person (co-goods-team):** Pontus Karlsson (project lead)
- **7 tags:** antirival, network-effects, sharing-economy, commons, goods-theory, nonrival, co-goods

**Example content** (`example: true`; placeholder data used to exercise the website's templates, filtered from production renders, easy to remove in bulk):
- **2 library items** (serials `x-00001`, `x-00002`) + 1 publisher + 1 publication
- **1 person** (external author placeholder)
- **2 observations**, **1 insight**, **1 hypothesis** (exercises the epistemic chain)
- **1 wiki article**, **1 essay**, **1 blog post**, **1 glossary entry**, **1 tag**

The `research/reports/` collection is scaffolded empty. The first curated library entry will receive serial `l-00001`.

## Templates

See `templates/`. Active set (v1):

- `template-library-v1.md`
- `template-people-v1.md`
- `template-wiki-v1.md`, `template-essay-v1.md`, `template-report-v1.md`, `template-blog-post-v1.md`, `template-glossary-v1.md`
- `template-insights-v1.md`, `template-observation-v1.md`, `template-hypothesis-v1.md`, `template-tags-v1.md`

Each template carries an inline `<!-- schema notes -->` block describing its frontmatter contract.

## Quality standards

See [`docs/taxonomy.md`](./docs/taxonomy.md) for conventions (collections, file naming, slug rules, serials, universal frontmatter, wikilinks, the epistemic chain).

## License

© 2025–2026 DePalma Workwear Limited. This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/). See [`LICENSE`](./LICENSE).

Contributions are accepted under the same license (inbound = outbound). See [`CONTRIBUTING.md`](./CONTRIBUTING.md).
