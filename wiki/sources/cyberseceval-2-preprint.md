---
title: CyberSecEval 2 preprint
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: preprint
publisher: arXiv
published: 2024-04-19
accessed: 2026-10-07
dimensions: [adversarial-machine-learning-and-ai-security, evaluation-benchmarks-and-reproducibility]
sources: []
---

## Summary

The [CyberSecEval 2 preprint](https://arxiv.org/abs/2404.13161) introduces tests for LLM cybersecurity risks and capabilities, including prompt injection and code-interpreter abuse, and discusses the trade-off between refusing unsafe requests and wrongly refusing benign ones.

## Key points

- The abstract reports a 26-41% prompt-injection success range for the models and test cases studied; this is not a general failure rate for deployed systems.
- It proposes a false refusal rate for borderline benign requests alongside harmful-request measures.
- It also examines model performance on vulnerability-related tasks; this wiki does not reproduce or operationalise those tests.

## Details

### Evaluation and limits

The accessible abstract gives a high-level account but not a complete independently checked protocol, uncertainty interval, or dataset audit. Treat its conclusions as authors' reported preprint findings. The later repository's versioned benchmarks should be evaluated on their own terms rather than retroactively attributed to this 2024 paper.

## Related

- [AI-assisted security analysis](../challenges/ai-assisted-security-analysis.md).

## References

- Bhatt et al., [CyberSecEval 2: A Wide-Ranging Cybersecurity Evaluation Suite for Large Language Models](https://arxiv.org/abs/2404.13161), preprint, 2024-04-19; accessed 2026-10-07.
