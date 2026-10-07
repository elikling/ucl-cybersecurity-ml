---
title: SigmaHQ rule repository documentation
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: open-source project documentation
publisher: SigmaHQ
published: unknown
accessed: 2026-10-07
dimensions: [security-operations-and-risk-governance, open-source-ecosystem-and-maintenance]
sources: []
---

## Summary

[SigmaHQ](https://github.com/SigmaHQ/sigma) publishes an open, shareable format and community-maintained detection rules for security log events, with converters for deployment to different analysis backends.

## Key points

- The repository distinguishes generic detection, hunting and emerging-threat rules; a match is an analytic signal, not proof of malicious intent.
- Rule content uses Detection Rule License 1.1, which should be checked separately from a converter's software licence.

## Details

### Research use and limits

Use rules as transparent baselines or to define analyst review tasks. Validate against the available log schema and record conversion, false positives and time-dependent coverage. No rule performance was measured during this research.

## Related

- [Sigma](../tools/sigma.md).
- [AI-assisted security analysis](../challenges/ai-assisted-security-analysis.md).

## References

- SigmaHQ, [Sigma rule repository](https://github.com/SigmaHQ/sigma), project documentation; accessed 2026-10-07.
