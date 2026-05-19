---
slug: ""
name: ""
type: person
affiliation: ""
institution: ""
bio: ""
expertise: []
email: ""
website: ""
github: ""
orcid: ""
aliases: []
key_publications: []
tags: []
sources_by_author: []
status: active
relevance_to_project: ""
created: "{{date}}"
updated: 2026-05-19T22:03
---

# {{name}}

## Bio
Brief biography and background.

## Relevance to Co-Goods
How this person's work relates to the co-goods project.

## Notes
Additional notes.

<!--
Person schema (v1) — per p-002 architecture review ADR-011.

Required:
- File location: `people/<slug>.md` (flat)
- `slug`: `firstname-lastname` (e.g. `f-xavier-olleros`, `pontus-karlsson`)
- `name`: display name
- `affiliation`: enum — `co-goods-team | depalma-pilot | external-author | unclaimed`
- `bio`: brief biography

Optional (add when relevant):
- `institution`: free-text employer / academic institution
- `expertise`, `aliases`, `key_publications`, `tags`, `sources_by_author[]`
- `account-status`: for the future Clerk/Supabase "claim profile" integration
- `relevance_to_project`

Profiles aggregate the ways a person shows up across the repo. Roles
(`authors:`, `contributors:`, `editors:`, `designers:`, `reviewers:`) are
expressed on the content that references the person, not on the profile itself.
-->
