# Contributing to Co-Goods Research

Welcome! Co-Goods is an open-innovation research project. Anyone is welcome to contribute — drafts, refinements, citations, new wiki articles, essays, glossary entries, library items, fixes.

This document covers *how* to contribute. For the *what* — collections, schemas, conventions — see [`docs/taxonomy.md`](./docs/taxonomy.md) and the `templates/` directory.

## Quick start

1. **Fork** this repository on GitHub.
2. **Create a branch** for your change (`feature/add-wiki-antirival`, `docs/fix-typo`, etc.).
3. **Make your edits** using the appropriate template from `templates/`.
4. For new or in-progress content, set frontmatter `status: active, stage: draft`. The website will render it with a "Draft — work in progress" banner.
5. **Open a pull request** to `main`. Describe your change briefly and link any relevant Discord discussion.
6. The Co-Goods core team reviews. When ready, the maintainer flips `stage: draft` → `stage: published` and merges.

## Where things go

| Content | Location | Template |
|---|---|---|
| Library item (book / paper / podcast / etc.) | `resources/library/<slug>.md` | `template-library-v1.md` |
| Wiki article (neutral encyclopedic) | `resources/wiki/<slug>.md` | `template-wiki-v1.md` |
| Essay / model write-up (POV) | `thinking/essays/<slug>.md` | `template-essay-v1.md` |
| Report (versioned formal compilation) | `research/reports/<slug>/v0.1/<slug>.md` | `template-report-v1.md` |
| Glossary entry | `resources/glossary/<slug>.md` | `template-glossary-v1.md` |
| Blog post | `blog/<year>/<month>/<slug>.md` | `template-blog-post-v1.md` |
| Person profile | `people/<slug>.md` | `template-people-v1.md` |
| Tag | `tags/<slug>.md` | `template-tags-v1.md` |
| Insight (atomic research finding) | `research/insights/<slug>.md` | `template-insights-v1.md` |

For library items, the maintainer assigns the next `l-#####` serial on merge and updates `resources/library/INDEX.md`.

See [`docs/taxonomy.md`](./docs/taxonomy.md) for the full conventions.

## Frontmatter

Every content file starts with a YAML frontmatter block. The template for each collection documents the required and optional fields inline (`<!-- schema notes -->`).

Universal fields where relevant:
- `slug` — bare kebab-case; matches filename
- `status: active | inactive` — visible on website?
- `stage: draft | published` — WIP banner or polished?
- `created`, `updated` — ISO dates (`YYYY-MM-DD`)

## Wikilinks

Use qualified-path Obsidian-style wikilinks:

```markdown
The [[tags/coordination]] concept by [[people/jane-doe|Jane Doe]],
introduced in [[resources/library/smith-network-coordination-2022|Smith (2022)]], shows how
[[tags/network-effects|network effects]] can drive open systems.
```

Bare wikilinks (no slash) default to `/topics/<slug>` if a topic-aggregation page exists; otherwise they cause a build error. When in doubt, qualify.

## Assets (images and files)

- **Small images or files** — include them in your PR. Drop into the same folder as your `.md` file or attach in the PR description. The maintainer will place them correctly at merge.
- **Larger or many files** — include a download link in the PR description (Dropbox share, Google Drive, WeTransfer — whatever you have). The maintainer downloads and places at merge.

All images must come with attribution and license metadata compatible with CC BY-SA 4.0.

## Discussion

- **Discord** — community discussion and async chat: [Discord — link TBD]
- **PR comments** — issue-specific discussion lives in the PR itself.

For substantial changes (new schema fields, new collection types, structural changes), please open a Discord thread first — these touch the architecture-review log and need broader alignment.

## Review process

A Co-Goods core-team maintainer reviews each PR. Typical timeline:

1. Acknowledgement within a few days.
2. Comments / requests for changes if needed.
3. Merge once aligned.
4. The maintainer may flip `stage: draft` → `stage: published` at merge time if the content is mature, or leave it as a draft for further iteration.

## License

This repository is licensed under the **Creative Commons Attribution-ShareAlike 4.0 International License** (CC BY-SA 4.0) — see [`LICENSE`](./LICENSE).

**By submitting a contribution, you agree it is licensed under the same terms as the project (CC BY-SA 4.0).** Inbound license matches outbound — no separate Contributor License Agreement (CLA). This matches the license of the DePalma Workshop Dictionary Schema (used by our glossary) and is the standard for open-innovation knowledge projects.

If you're including external content (quotes, figures, etc.), ensure it's compatible with CC BY-SA 4.0 (public domain, CC-compatible, or fair-use citation). When in doubt, ask in the PR or on Discord.

---

Thanks for contributing!
