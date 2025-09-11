# Co-Goods Whitepaper

Research content and documentation for the Co-Goods protocol - a system for co-created and networked physical products.

## Structure

- **insights/** - Research findings categorized by methodology (empirical, theoretical, practical, etc.)
- **sources/** - Academic papers, books, reports, and other research sources
- **authors/** - Profiles of researchers and experts whose work informs our research
- **contributors/** - Team members and project contributors
- **tags/** - Organized taxonomy for content categorization
- **templates/** - Versioned Obsidian templates for creating structured content
- **about.md** - Project overview and methodology (renders on website)
- **taxonomy.md** - Content categorization system and quality standards

## Content Workflow

1. Use templates in `templates/` to create new content in Obsidian
2. Save files in appropriate directories (insights/, sources/, authors/, tags/)
3. Set `status: "active"` when ready for website display
4. Content automatically appears on the website at `localhost:3000`

## Obsidian Integration

### Wikilinks Support
Write naturally using Obsidian `[[wikilinks]]` - they automatically convert to proper website links:

```markdown
The [[antirival]] concept by [[F. Xavier Olleros]] exhibits [[network-effects]].
```

### Structured References
Use YAML frontmatter for programmatic cross-references:

```yaml
sources: ["olleros-antirival-goods-2018"]
authors: ["f-xavier-olleros"]
tags: ["antirival", "network-effects", "sharing-economy"]
```

## Current Content

### Sample Content Created
- **1 Source**: Olleros paper on antirival goods (2018)
- **1 Author**: F. Xavier Olleros profile  
- **5 Tags**: antirival, network-effects, sharing-economy, commons, goods-theory
- **1 Contributor**: Pontus Karlsson (project lead)

### Ready for Expansion
- **insights/** - Empty, ready for research findings
- **sources/** - Ready for additional academic papers
- **authors/** - Ready for more researcher profiles

## Template Versioning

Templates use simple version numbers (v1, v2, v3, etc.) with older versions archived in `templates/archive/`. All templates updated to use consistent `status: "active"` values.

## Quality Standards

See `taxonomy.md` for complete quality standards including:
- Required YAML frontmatter fields
- Content-specific requirements
- File naming conventions  
- Linking best practices

## License

All rights reserved. This work is currently proprietary and confidential.

**Future Licensing**: We plan to release this research under a Creative Commons license once the whitepaper is complete, allowing broader access while maintaining appropriate attribution and use guidelines.