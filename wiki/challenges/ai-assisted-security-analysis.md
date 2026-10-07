---
title: AI-assisted security analysis
type: challenge
aliases: [security analytics agents]
created: 2026-10-07
updated: 2026-10-07
dimensions: [adversarial-machine-learning-and-ai-security, agents-and-tool-using-systems, security-operations-and-risk-governance]
sources: [../sources/nist-adversarial-ml-taxonomy.md, ../sources/cyberseceval-2-preprint.md, ../sources/cyberseceval-repository.md, ../sources/data-science-agents-survey.md]
---

## Summary

Assist an analyst in making defensible decisions from logs, code, indicators or benchmark data without granting an automated system unchecked access to sensitive material or operational actions.

## Key points

- Defender task: summarise evidence, propose hypotheses and prioritise review, with cited artefacts and explicit uncertainty.
- Adversarial and accidental failure modes include tainted input, prompt injection, unsupported conclusions and false refusals; [NIST's taxonomy](../sources/nist-adversarial-ml-taxonomy.md) supplies threat-model terminology.
- [CyberSecEval 2](../sources/cyberseceval-2-preprint.md) studies model security behaviour; later [CyberSOCEval documentation](../sources/cyberseceval-repository.md) includes defensive knowledge tasks. Neither directly measures reduction in analyst workload.

## Details

### Measurement

In an authorised, offline evaluation, give agent and human baseline the same redacted evidence. Check answer correctness, source traceability, unsupported claims, unnecessary refusals, privacy leakage, time and cost. Keep retrieval and tool access constrained and approvals for real-world actions human-owned. The cross-domain [agent survey](../sources/data-science-agents-survey.md) highlights lifecycle coverage gaps; testing whether those carry into a SOC is a research question, not an established result.

## Related

- [Agent-assisted analytics](../methods/agent-assisted-analytics.md).
- [Sigma](../tools/sigma.md).

## References

- [NIST AI 100-2 E2025](../sources/nist-adversarial-ml-taxonomy.md).
- [CyberSecEval 2](../sources/cyberseceval-2-preprint.md).
- [CybersecurityBenchmarks repository](../sources/cyberseceval-repository.md).
- [Data-science agents survey](../sources/data-science-agents-survey.md).
