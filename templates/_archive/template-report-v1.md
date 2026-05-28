---
slug: ""
title: ""
type: ""
version: ""
version-date: ""
authors: []
abstract: ""
supersedes: ""
draws-from: []
tags: []
changelog: []
status: active
stage: draft
created: "{{date}}"
updated: "{{date}}"
---

# {{title}}

## Abstract
Brief abstract / executive summary.

## ...report sections...

## Changelog
- {{version}} ({{date}}): initial draft.

<!--
Report schema (v1) — superseded; the per-type split (lightpaper, whitepaper, position-paper, model-paper) lands when content does.

- File location: `research/reports/<slug>/<version>/<slug>.md`
  Each report is a folder; each version a sub-folder.
- `type`: `lightpaper | whitepaper | position-paper | model-paper`
- `version`: `MAJOR.MINOR` (skip PATCH). v0.x = pre-publication drafts;
  v1.0 = first formal release; v2.0 = substantial revision.
- `version-date`: ISO date this version was cut.
- `supersedes`: slug of the predecessor (e.g. when a graduated essay/model
  becomes a report).
- `draws-from`: slugs of essays / insights / wiki articles contributing to
  this report.

Assets live at `<version>/assets/<file>`. Markdown references them via
`./assets/<file>` regardless of version — the build's cascading resolver
walks backward through earlier versions to find unchanged assets. Each
version's `assets/` folder contains only what's new or changed in that
version.

Reports freeze on release; future versions live in new sibling folders.
URL `/research/reports/<slug>` routes to the latest published version; specific
versions reachable at `/research/reports/<slug>/<version>`.
-->
