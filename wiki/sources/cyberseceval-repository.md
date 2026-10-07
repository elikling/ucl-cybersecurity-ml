---
title: CyberSecEval benchmark repository
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: project documentation
publisher: Meta Purple Llama
published: unknown
accessed: 2026-10-07
dimensions: [adversarial-machine-learning-and-ai-security, evaluation-benchmarks-and-reproducibility, security-operations-and-risk-governance]
sources: []
---

## Summary

The [CybersecurityBenchmarks repository](https://github.com/meta-llama/PurpleLlama/tree/main/CybersecurityBenchmarks) documents an evolving CyberSecEval suite. Its current README describes defensive CyberSOCEval questions on malware analysis and threat-intelligence reasoning as well as AI security assessments.

## Key points

- The defensive tasks use multiple-choice questions and report metrics such as exact-set correctness and partial-credit similarity. They assess answers to benchmark questions, not production SOC efficiency.
- The README flags data dependencies and model/API requirements; some other tracks concern offensive capabilities and are outside this wiki's experimental scope.
- The repository says its security-code-generation benchmarks are temporarily excluded from the default run, so version and enabled tracks must be pinned before comparing results.

## Details

### Research use and limits

For a defensive study, choose only the malware-analysis or threat-intelligence reasoning subset, verify terms, report data provenance and question contamination risk, and keep a human analyst in the evaluation loop. No benchmark run was performed in this task. Avoid distributing potentially sensitive prompts, transcripts or report content without checking terms.

## Related

- [AI-assisted security analysis](../challenges/ai-assisted-security-analysis.md).
- [Agent-assisted analytics](../methods/agent-assisted-analytics.md).

## References

- Meta Purple Llama, [CybersecurityBenchmarks README](https://github.com/meta-llama/PurpleLlama/tree/main/CybersecurityBenchmarks), versioned project documentation; accessed 2026-10-07.
