---
slug: ""
title: ""
type: wiki
summary: ""
tags: []
related: []
status: active
stage: draft
created: "{{date}}"
updated: 2026-05-19T22:03
---

# {{title}}

## Summary
One- or two-sentence summary of the topic.

## Overview
Background and scope.

## ...content sections as the article matures...

## Related
- `[[resources/wiki/...]]` — related wiki articles
- `[[thinking/essays/...]]` — relevant essays
- `[[resources/library/...]]` — library entries

<!--
Wiki article schema (v1) — per p-002 architecture review ADR-008 / ADR-014.

- File location: `resources/wiki/<slug>.md`
- Voice: **neutral, encyclopedic**. Open contribution via PR.
- Distinct from essays (which are POV / authored).
- Living document — updates in place; git history is the version log.
- `stage: draft` shows a WIP banner on the website; `stage: published`
  removes it. URL stays stable across the transition.
-->
