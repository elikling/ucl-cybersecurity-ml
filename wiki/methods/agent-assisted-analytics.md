---
title: Agent-assisted analytics
type: method
aliases: [generative data science agents]
created: 2026-10-07
updated: 2026-10-07
dimensions: [agents-and-tool-using-systems, generative-and-foundation-models, evaluation-benchmarks-and-reproducibility]
sources: [../sources/data-science-agents-survey.md, ../sources/cyberseceval-repository.md]
---

## Summary

An agent combines language-model planning with controlled retrieval or tools to analyse a dataset or incident. For cybersecurity research, useful outputs are reproducible queries, evidence-backed summaries and proposals requiring analyst review.

## Key points

- Inputs: authorised, minimised telemetry or benchmark questions; tools should have bounded permissions and logged outputs.
- Baseline: the same analyst task using a fixed script, search procedure or human-only workflow, with the same evidence.
- Prompt injection, answer contamination, false confidence and sensitive-data disclosure are relevant failure modes.

## Details

### Evaluation

Pin model, prompt, tool versions and retrieval corpus. Score grounded correctness, omissions, harmful or unsupported recommendations, refusal of benign tasks, time, token cost and reproducibility across runs. Avoid accepting a benchmark answer as proof of field effectiveness. The [agent survey](../sources/data-science-agents-survey.md) is cross-domain and under review; [CyberSOCEval](../sources/cyberseceval-repository.md) uses defensive questions rather than end-to-end incident handling. No agent runs were performed here.

## Related

- [AI-assisted security analysis](../challenges/ai-assisted-security-analysis.md).
- [Sigma](../tools/sigma.md).

## References

- [LLM-based data science agents survey](../sources/data-science-agents-survey.md).
- [CybersecurityBenchmarks repository](../sources/cyberseceval-repository.md).
