---
name: cybersecurity-wiki-maintenance
description: 'Audit, refresh, and organise the cybersecurity research wiki. Use when checking stale pages, broken links, duplicate entities, missing evidence, taxonomy coverage, index/timeline accuracy, or overall wiki health.'
---

# Cybersecurity wiki maintenance

Use [the wiki blueprint](../../../wiki/README.md) as the source of truth for page types and dimensions. Apply the wiki content instructions to all wiki edits.

## Procedure

1. Inventory the existing wiki pages and supporting raw-source metadata. Do not assume a script or index exists; inspect the repository before using a workflow.
2. Check required page structure, YAML frontmatter, canonical naming, aliases, source references, local links, dates, and whether claims retain provenance.
3. Check that each curated source is reflected in the source catalogue and relevant challenge/method/data/tool/provider pages. Check that dated developments appear on the timeline and that the index links to current category pages.
4. Flag stale or time-sensitive records. Use recorded `checked`/`updated` dates and these review prompts: software, providers, and dataset access details older than 180 days; standards and regulatory guidance older than 365 days. These are review thresholds, not proof that a page is wrong.
5. Review contradictions, duplicate candidates, orphan pages, missing taxonomy coverage, and synthesis claims that lack at least two independent sources. Report gaps separately from verified defects.
6. Make additive, evidence-backed corrections and update affected indexes, timeline, and change log. For ambiguous links, duplicates, or disputed content, report a proposed resolution instead of merging or deleting pages.
7. Re-run the same checks after edits. Summarise checked scope, fixes made, unresolved items, and any pages due for external verification.

## Safety boundary

Do not delete, rename, or merge pages or raw captures without explicit user approval. Do not mark software, providers, datasets, links, or standards as current unless their authoritative source was checked during this task. Never treat a date threshold alone as evidence of obsolescence.
