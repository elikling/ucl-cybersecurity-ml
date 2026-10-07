---
name: cybersecurity-evidence-synthesis
description: 'Compare cybersecurity challenges, statistical models, machine-learning methods, datasets, benchmarks, tools, and providers across curated sources. Use when drafting a research landscape, evidence map, trend, gap, or project-question synthesis.'
---

# Cybersecurity evidence synthesis

Follow [the wiki blueprint](../../../wiki/README.md) and [the wiki content instructions](../../instructions/cybersecurity-wiki.instructions.md). Base conclusions on curated wiki source pages; perform additional source research only when the user asks for it, and curate new evidence through the source-curation workflow.

## Procedure

1. Define the question and scope: cybersecurity problem, population/system, defensive or analytical goal, time window, and relevant data conditions.
2. Find the relevant source, challenge, method, dataset, tool, provider, and prior synthesis pages. Note missing coverage before drawing conclusions.
3. Compare at least two independent sources for a cross-source synthesis. Identify source type and evidence strength; two pages that repeat the same underlying result are not independent confirmation.
4. Compare methods in context: threat model, data provenance, labels, splits, baselines, metrics, operational constraints, and external-validity limits. Separate statistical modelling assumptions from ML implementation choices.
5. State agreement, disagreement, evidence gaps, and time sensitivity explicitly. Distinguish detection performance from operational security impact and benchmark results from real-world effectiveness.
6. Create or update a synthesis page with linked evidence for each substantive claim, a dated scope, implications for research, and testable open questions. Do not present hypotheses as established findings.
7. Link the synthesis to the relevant controlled dimensions and existing entities. Update the index and change log if present.
8. Check that each conclusion can be traced to cited pages and that dual-use, privacy, licensing, and reproducibility concerns are represented where relevant.

## Research-question quality

Prefer questions that specify a threat or defensive task, a measurable outcome, a plausible baseline, an available and lawful dataset, and a feasible evaluation. Flag label leakage, temporal leakage, distribution shift, class imbalance, weak ground truth, and unrealistic attacker/defender assumptions before recommending a study.
