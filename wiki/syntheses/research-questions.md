---
title: Study designs and open questions
type: synthesis
aliases: []
created: 2026-10-07
updated: 2026-10-07
dimensions: [statistical-inference-and-experimental-design, research-gaps-and-opportunities, evaluation-benchmarks-and-reproducibility]
sources: [../sources/cic-ids2017-documentation.md, ../sources/unsw-nb15-documentation.md, ../sources/ember-project.md, ../sources/tabpfn-project.md, ../sources/cyberseceval-repository.md, ../sources/data-science-agents-survey.md]
---

## Summary

Three bounded, defensive studies separate performance on public benchmarks from claims about analyst effectiveness. All proposed outcomes below are hypotheses, not findings; test only with authorised data and currently permitted models.

## Key points

- Prefer a temporal or environment-level split, a frozen test set, explicit prevalence and predeclared decision threshold to a random-row leaderboard.
- The available sources support baselines and evaluation designs, not a promise that newer models outperform established methods.
- Allocate a separate effort to verify dataset download terms, exact checkpoint rights, compute and ethics review before experiments.

## Details

### Candidate A: intrusion drift and alert burden

Question: does an [anomaly detector](../methods/anomaly-detection.md) or pinned tabular model improve recall at a fixed false-alert budget relative to a simple supervised baseline when training precedes test traffic? Use [CIC-IDS2017](../sources/cic-ids2017-documentation.md) for a time-based proof of method; repeat within [UNSW-NB15](../sources/unsw-nb15-documentation.md) if access and comparable task definitions are confirmed. Record per-class results, bootstrapped uncertainty grouped by capture period (not independent flows), and feature leakage checks. Even positive results cannot establish operational performance.

### Candidate B: static malware model shift

Question: can a model improve recall at low false-positive rates on a versioned [EMBER](../sources/ember-project.md) feature representation without unacceptable memory, latency or calibration change? Pin the archived extraction code and release; avoid claims of recent-threat coverage. [SoReL-20M](../sources/sorel-20m-project.md) is a possible scale check only after terms, storage and label provenance are approved. In particular do not mix training on the held-out period.

### Candidate C: grounded analyst assistance

Question: does a bounded [agent](../methods/agent-assisted-analytics.md) reduce time to a correctly evidenced answer on authorised defensive questions compared with fixed search and an analyst-only baseline? Start by auditing the defensive subset described in the [CyberSecEval repository](../sources/cyberseceval-repository.md); avoid assuming it measures real SOC impact. Blind-score correctness, cited evidence, unsupported conclusions, benign refusals, time, leakage and cost. The [cross-domain agent survey](../sources/data-science-agents-survey.md) motivates lifecycle coverage checks but does not supply cyber outcomes.

## Related

- [Cybersecurity ML research landscape](research-landscape.md).
- [AI-assisted security analysis](../challenges/ai-assisted-security-analysis.md).

## References

- [CIC](../sources/cic-ids2017-documentation.md), [UNSW](../sources/unsw-nb15-documentation.md), [EMBER](../sources/ember-project.md) and [SoReL](../sources/sorel-20m-project.md), dataset/project documentation.
- [TabPFN](../sources/tabpfn-project.md) and [CybersecurityBenchmarks](../sources/cyberseceval-repository.md), project documentation; [agent survey](../sources/data-science-agents-survey.md), preprint (2025).
