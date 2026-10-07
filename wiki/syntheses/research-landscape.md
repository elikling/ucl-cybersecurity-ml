---
title: Cybersecurity ML research landscape
type: synthesis
aliases: [first-edition landscape]
created: 2026-10-07
updated: 2026-10-07
dimensions: [evaluation-benchmarks-and-reproducibility, research-gaps-and-opportunities, generative-and-foundation-models]
sources: [../sources/cic-ids2017-documentation.md, ../sources/unsw-nb15-documentation.md, ../sources/ember-project.md, ../sources/sorel-20m-project.md, ../sources/nist-adversarial-ml-taxonomy.md, ../sources/cyberseceval-2-preprint.md, ../sources/cyberseceval-repository.md, ../sources/data-science-agents-survey.md, ../sources/tabpfn-project.md, ../sources/enisa-threat-landscape-2026.md, ../sources/verizon-dbir-2026.md, ../sources/mitre-attack-overview.md, ../sources/sigma-project.md, ../sources/zeek-project.md, ../sources/suricata-project.md]
---

## Summary

As of 7 October 2026, the most tractable starting point for this team is a **defensive, reproducible comparison on permitted tabular data**, followed by a carefully bounded analyst-assistance study. Public intrusion and malware benchmarks provide baselines, but their capture environments, label processes and time periods constrain claims about real operations. Tabular foundation models and agents are distinct research interventions: one predicts from structured features, the other assists with analysis and decision-making. No model was trained and no performance result was replicated for this overview.

The comparison spans a narrow, verified selection of primary sources; it is **not an exhaustive 2024-26 systematic review**. [ENISA's 2026 EU threat report](../sources/enisa-threat-landscape-2026.md) and [Verizon's 2026 DBIR page](../sources/verizon-dbir-2026.md) provide current problem context, not ML efficacy evidence. [NIST's 2025 taxonomy](../sources/nist-adversarial-ml-taxonomy.md) supplies adversarial-ML vocabulary, not effectiveness results. [CyberSecEval 2](../sources/cyberseceval-2-preprint.md) and the [2025 agent survey](../sources/data-science-agents-survey.md) are preprints; authors' findings are not established field performance.

## Key points

- Controlled benchmarks permit reproducible comparisons, but [CIC-IDS2017](../sources/cic-ids2017-documentation.md) and [UNSW-NB15](../sources/unsw-nb15-documentation.md) share a limitation: lab traffic with scheduled/synthetic scenarios. Cross-corpus agreement would strengthen a limited claim, not settle deployment generalisation.
- [EMBER](../sources/ember-project.md) offers manageable static-feature baselines, whereas [SoReL-20M](../sources/sorel-20m-project.md) is much larger with dataset terms and incomplete benign-binary access. Their labels and selection processes are not interchangeable.
- [TabPFN](../sources/tabpfn-project.md) supplies a tabular-model candidate, not evidence of cyber-specific benefit; the exact checkpoint and weights licence matter. The [agent survey](../sources/data-science-agents-survey.md) highlights workflow and governance gaps, while the [CyberSecEval repository](../sources/cyberseceval-repository.md) offers defensive question tasks but not end-to-end SOC outcome evidence.

## Details

### Comparison

| Cybersecurity problem area | Challenge | Methods to test | Evidence and limitations | Research gap | Data or benchmark |
| --- | --- | --- | --- | --- | --- |
| [Network intrusion](../challenges/network-intrusion-detection.md) | High-volume flow triage with changing benign behaviour and low alert budgets | [Anomaly scores](../methods/anomaly-detection.md) versus supervised trees and, separately, a [tabular foundation model](../methods/tabular-foundation-models.md) | 2017 CIC capture has a scheduled attack calendar; UNSW lab traffic includes synthetic attacks. Neither owner documentation establishes contemporary operational validity ([CIC](../sources/cic-ids2017-documentation.md), [UNSW](../sources/unsw-nb15-documentation.md)). | Does a temporal or cross-environment split reverse the ranking seen with a random split? | [CIC-IDS2017](../data/cic-ids2017.md); [UNSW-NB15](../data/unsw-nb15.md) |
| [Malware detection](../challenges/malware-detection.md) | Classification under label noise, changing samples and expensive false blocks | Static-feature tree baseline versus calibrated alternative or tabular pretrained model | [EMBER](../sources/ember-project.md) ships feature baselines but is archived; [SoReL](../sources/sorel-20m-project.md) has more scale yet substantial storage and access constraints. Neither demonstrates robustness to present threats. | At what false-positive budget does a newer model improve on a pinned baseline under a held-out period? | [EMBER](../data/ember.md); [SoReL-20M](../sources/sorel-20m-project.md) (terms and capacity check required) |
| [AI-assisted security analysis](../challenges/ai-assisted-security-analysis.md) | Correct, source-traceable defensive reasoning while avoiding unsafe disclosure and unsupported conclusions | [Agent-assisted analytics](../methods/agent-assisted-analytics.md) versus fixed retrieval and human-only review | [CyberSecEval 2](../sources/cyberseceval-2-preprint.md) is a 2024 model-safety preprint; current [CyberSOCEval documentation](../sources/cyberseceval-repository.md) describes defensive knowledge questions, not real incident outcomes. [NIST](../sources/nist-adversarial-ml-taxonomy.md) gives threat terminology. | Does an audited assistant improve groundedness and analyst time on authorised, redacted cases without increasing unsupported claims? | Defensive CyberSOCEval subset, subject to current terms and benchmark-version check |
| Threat detection engineering | Reconcile transparent detection rules with data-driven alerts | [Sigma](../tools/sigma.md) rule baseline plus [Zeek](../tools/zeek.md) telemetry or [Suricata](../tools/suricata.md) alerts | Maintainer documentation describes available tools ([Sigma](../sources/sigma-project.md), [Zeek](../sources/zeek-project.md), [Suricata](../sources/suricata-project.md)); no independently measured comparison is available in this curation. | Can a model add actionable detections at the same review budget as pinned rules? | Authorised logs or replay; corpus, permissions and labels not yet identified |
| Phishing and social engineering | Detect deceptive messages without penalising legitimate communication | Text classification versus analyst/rule baseline, with optional constrained LLM triage | [Verizon's 2026 landing page](../sources/verizon-dbir-2026.md) flags mobile social engineering, but gives no independently audited model evaluation here; [MITRE ATT&CK](../sources/mitre-attack-overview.md) describes adversary behaviours, not task labels. | Can a system generalise across channel and language while preserving privacy and limiting false blocks? | No corpus, access terms or privacy approvals verified for this task |
| Vulnerability management and supply chain | Prioritise exposure with incomplete asset context and changing exploitation | Calibrated ranking versus rule-based prioritisation; assess time-to-remediation and recall at fixed workload | [Verizon's 2026 page](../sources/verizon-dbir-2026.md) highlights vulnerability exploitation; [ATT&CK](../sources/mitre-attack-overview.md) offers behaviour vocabulary. Neither supports a prevalence estimate or benchmark model comparison here. | Does context-aware ranking outperform a simple baseline using only information available at decision time? | No vetted exploit, asset or vulnerability corpus selected; CISA KEV page could not be retrieved in this research |
| Identity, cloud and platform security | Interpret changing authentication and platform activity with limited labels | Temporal anomaly and rule baselines before complex models | [ENISA](../sources/enisa-threat-landscape-2026.md) reports EU incident context; [ATT&CK](../sources/mitre-attack-overview.md) gives adversary vocabulary. Neither verifies a representative cloud or identity dataset. | Which telemetry and split can measure false-alert workload without exporting sensitive identifiers? | Access-controlled local or approved public logs needed; no corpus verified |

### Generative-Data Science strands

1. **Generative AI supporting data-science work:** language-model help with exploratory analysis, code and explanations; assess correctness, provenance and human review. The [cross-domain survey](../sources/data-science-agents-survey.md) motivates this, but a cyber-specific experiment remains necessary.
2. **AI acting as statistical analyst:** tool-using agents span planning through monitoring; test bounded, logged actions on redacted datasets against a fixed scripted analysis. The survey authors report weak deployment and governance coverage in systems they reviewed, not proof that agents are unsuitable.
3. **Tabular foundation models:** pretrained prediction on structured telemetry or PE features is a model-comparison question, not an agentic workflow. The [TabPFN project](../sources/tabpfn-project.md) gives access and licensing information. Fine-tuning a cyber-specific model is a **hypothesis** for a later stage; no verified cyber fine-tuning result or eligible checkpoint was found in this curation.

### Evidence boundaries and next research

The defensible first experiment is a preregistered temporal-split intrusion study, with a conventional baseline, an anomaly baseline, optional licence-compliant TabPFN checkpoint, fixed alert budget and a second-dataset replication. Report preprocessing, compute, confidence intervals and data permissions. A separate study can compare analyst decision support against fixed retrieval with blinded review. Do not pool benchmark leaderboards across different labels and populations. More recent representative datasets, independent peer-reviewed evaluations, OT-specific methods, regulatory privacy constraints and practitioner discourse still require targeted, source-verified curation.

## Related

- [Study designs and open questions](research-questions.md).
- [Taxonomy](../taxonomy.md).
- [Timeline](../timeline.md).

## References

- [CIC-IDS2017](../sources/cic-ids2017-documentation.md); [UNSW-NB15](../sources/unsw-nb15-documentation.md); [EMBER](../sources/ember-project.md); [SoReL-20M](../sources/sorel-20m-project.md), official documentation; consulted 2026-10-07.
- [NIST AI 100-2 E2025](../sources/nist-adversarial-ml-taxonomy.md), final report (2025); [CyberSecEval 2](../sources/cyberseceval-2-preprint.md) (2024) and [LLM-based data science agents](../sources/data-science-agents-survey.md) (2025), preprints.
- [TabPFN](../sources/tabpfn-project.md) and [CybersecurityBenchmarks](../sources/cyberseceval-repository.md), versioned project documentation; consulted 2026-10-07.
- [ENISA Threat Landscape 2026](../sources/enisa-threat-landscape-2026.md), EU agency report (2026); [Verizon DBIR 2026](../sources/verizon-dbir-2026.md), vendor report page (2026); [MITRE ATT&CK](../sources/mitre-attack-overview.md), living knowledge base.
