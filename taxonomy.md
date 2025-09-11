# Co-Goods Project Taxonomy

Based on analysis of The Library of Economic Possibility structure and our implementation.

## Insight Categories

Research insights are categorized by their methodological approach and evidence type:

- **Anecdotal** - Based on individual experiences or case studies
- **Econometric** - Using statistical/mathematical economic models
- **Empirical** - Based on observed data and experimental evidence
- **Fact** - Established factual information
- **Practical** - Applied, real-world implementation insights
- **Theoretical** - Conceptual frameworks and theoretical models

## Source Types

Research sources are categorized by format and publication type:

- **Journal Article** - Peer-reviewed research papers in academic journals
- **Academic Paper** - Other peer-reviewed research papers
- **Article** - Magazine articles, blog posts, news articles
- **Book** - Published books and monographs
- **Poll** - Survey data and polling results
- **Report** - Research reports, white papers, institutional publications
- **Visualization** - Charts, graphs, infographics, data visualizations

## Content Status Values

All content types use these status values:

- **active** - Published and displayed on website
- **inactive** - Not displayed on website
- **deprecated** - Superseded by newer content (for tags)
- **merged** - Combined into other content (for tags)
- **alumni** - Former team members (for contributors)

*Note: Website displays only content with `status: "active"`*

## Relevance Scoring

For sources and insights:

- **high** - Directly applicable to protocol design
- **medium** - Supporting context or background
- **low** - Tangential relevance

## Tag Categories

Tags are organized into these high-level categories:

- **topic** - Subject matter areas (e.g., "cooperative-economics", "tokenomics")
- **methodology** - Research methods (e.g., "case-study", "quantitative")
- **protocol_aspect** - Parts of the protocol (e.g., "governance", "incentives")
- **economic_theory** - Economic frameworks (e.g., "antirival", "network-effects", "commons")
- **technology** - Technical aspects (e.g., "blockchain", "smart-contracts")
- **other** - Miscellaneous categorizations

## Current Tag Definitions

### Economic Theory Tags
- **antirival** - Goods that become more valuable with shared use
- **network-effects** - Value increases with user adoption
- **sharing-economy** - Platform-mediated resource sharing
- **commons** - Collectively managed shared resources
- **goods-theory** - Economic classification frameworks

## File Naming Conventions

- **Sources**: `author-title-year.md` (e.g., `olleros-antirival-goods-2018.md`)
- **Authors**: `firstname-lastname.md` (e.g., `f-xavier-olleros.md`)
- **Tags**: `concept-name.md` (e.g., `antirival.md`, `network-effects.md`)
- **Contributors**: `firstname-lastname.md` (e.g., `pontus-karlsson.md`)
- **Insights**: `descriptive-title.md` (e.g., `antirival-manufacturing-analysis.md`)

## Obsidian Integration

### Wikilink Support
The system supports Obsidian `[[wikilinks]]` which automatically convert to proper website links:

- `[[antirival]]` → `/tags/antirival`
- `[[f-xavier-olleros]]` → `/authors/f-xavier-olleros`
- `[[network-effects]]` → `/tags/network-effects`

### Structured References
Use YAML frontmatter arrays for programmatic linking:

```yaml
sources: ["olleros-antirival-goods-2018"]
authors: ["f-xavier-olleros"]
tags: ["antirival", "network-effects", "sharing-economy"]
```

## Quality Standards

### Required for All Content
- Use appropriate template from `templates/`
- Complete all YAML frontmatter fields
- Set `status: "active"` for published content
- Use consistent slug naming (matches filename)
- Set proper `created` and `updated` dates (YYYY-MM-DD format)

### Content-Specific Requirements
- **Sources**: Include `key_points`, `relevance_to_project`, DOI when available
- **Authors**: Include `relevance_to_project`, link to their sources
- **Tags**: Include `description`, `usage_guidelines`, `related_tags`
- **Insights**: Reference supporting `sources` and `authors`