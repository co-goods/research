---
template: doc
template_version: 1.0.0
collection: conventions
slug: epistemic-chain
title: "The epistemic chain"
description: "Observation → insight → hypothesis: the upstream-reference rules."
order: 60
status: active
stage: draft
---

# The epistemic chain

The research content in the Co-Goods repo follows a simple chain — **observation → insight → hypothesis** — that traces where claims come from. This page describes each link in the chain and the upstream-reference rules that keep it traceable.

## The chain

```
observations  →  insights  →  hypotheses
```

- **Observations** capture external signals from the world.
- **Insights** synthesise from observations and/or published sources.
- **Hypotheses** are testable predictions built on insights.

Each link references the upstream evidence so any claim can be walked back to its grounding.

## Observations

Observations record external signals — data points, trends, cases, field findings, interview notes, anything noticed in the world.

```yaml
template: observation
collection: observations
authors: [jane-doe]
sources: [smith-network-coordination-2022]    # required: ground in published sources
```

Observations **ground in `sources:`** — bare slugs referring to library items. An observation that doesn't ground in any source is a hunch, not an observation.

## Insights

Insights synthesise observations and/or sources into atomic findings. Every insight must declare at least one upstream link:

```yaml
template: insight
collection: insights
authors: [jane-doe]
observations: [weekend-readership-spike, expert-interview-pattern]   # upstream observations
sources: [smith-network-coordination-2022]                            # and/or upstream sources
```

The rule: **`observations:` or `sources:` (or both) must be populated. Neither can be empty.** An insight without upstream evidence is a claim, not an insight.

- Use `observations:` when synthesising signals across multiple observations.
- Use `sources:` when extending a published source's argument.
- Use both when the insight emerges at the intersection.

## Hypotheses

Hypotheses are testable predictions in "if [condition], then [outcome]" form, built on insights:

```yaml
template: hypothesis
collection: hypotheses
authors: [jane-doe]
insights: [asynchronous-coordination-density]   # upstream insights this hypothesis builds on
validation-status: pending                       # lifecycle below
```

Validation status follows a simple lifecycle:

| Status | Meaning |
|---|---|
| `pending` | Not yet tested |
| `validated` | Test outcome supports the prediction |
| `invalidated` | Test outcome contradicts the prediction |
| `revised` | Original hypothesis was changed mid-test; new statement, link to predecessor |

A hypothesis without `insights:` is also a claim, not a hypothesis. Every hypothesis traces back through insights → observations → sources.

## Decisions are out of repo

The chain stops at hypotheses. **Decisions** — what to actually do, ship, prioritise — are not a collection in this repo. They live in:

- Per-project working files in whichever project owns the decision.
- Concept-canon docs elsewhere (the Co-Goods enterprise / DePalma Workshop spaces).

This keeps the research repo focused on understanding, not on action.

## Why this matters

- **Traceability** — any insight or hypothesis can be walked back to its grounding observations and sources.
- **Updateable beliefs** — when an upstream source is retracted or revised, downstream insights and hypotheses are findable by `grep`-ing the source slug.
- **Distinguishes evidence from claim** — content with no upstream link is a claim and labelled as such; content with upstream links can be assessed by inspecting the chain.

## Related conventions

- **Taxonomy** (collections, items, templates): see `taxonomy.md`.
- **Frontmatter contract** (universal + per-template fields): see `frontmatter.md`.
- **Wikilinks** (qualified-path syntax used in frontmatter and prose): see `wikilinks.md`.
