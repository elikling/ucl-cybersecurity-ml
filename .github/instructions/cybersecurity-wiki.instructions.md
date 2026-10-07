---
name: Cybersecurity Wiki Content
description: "Use when creating, editing, reviewing, or linking cybersecurity research wiki pages. Covers page structure, evidence, datasets, methods, tools, provenance, and dual-use handling."
applyTo: "wiki/**/*.md"
---

# Cybersecurity wiki content rules

Use [wiki/README.md](../../wiki/README.md) as the canonical taxonomy and page-schema reference. Keep pages concise enough to scan but detailed enough that a student can understand what was studied, how, with which evidence, and what remains uncertain.

- Use one canonical page per source or entity. Prefer descriptive lowercase kebab-case filenames, aliases for alternate names, and relative Markdown links. Do not invent entities to fill a category.
- Start pages with YAML frontmatter containing, at minimum, `title`, `type`, `created`, and `updated`. Add aliases, source links, dimensions, and type-specific metadata where relevant. Use ISO dates (`YYYY-MM-DD`) and mark unknown values as unknown rather than guessing.
- Use the common sections `## Summary`, `## Key points`, `## Details`, `## Related`, and `## References`. A page may add type-specific subsections under `## Details`.
- Keep evidence attached to claims. Link claims to a source page or a direct authoritative URL; distinguish a source's reported result from the wiki's interpretation.
- For methods, record the threat model, task, statistical or ML method, data inputs, baselines, metrics, results, assumptions, limitations, and reproducibility details when the source provides them.
- For datasets, record provenance, collection period, task/labels, access route, licence or terms, privacy constraints, known bias, representativeness, leakage risks, and benchmark/version details when available.
- For software and providers, record maintainer, official URL, licence, version or checked date, deployment model, availability/pricing constraints, and security/privacy implications. Treat vendor statements as vendor claims.
- Preserve disagreement and uncertainty. Do not turn correlation into causation, benchmark performance into deployment effectiveness, or a preprint into an established finding.
- Do not put credentials, private user data, exploit payloads, or unnecessary copyrighted text in wiki pages. Describe dual-use risks and defensive relevance at an appropriate level.
- Before finishing, check frontmatter, required sections, references, local links, canonical naming, dates, and any affected index/timeline/log entries. Report issues that cannot be resolved from available evidence.
