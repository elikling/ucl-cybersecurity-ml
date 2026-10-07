---
title: Anomaly detection
type: method
aliases: [outlier detection]
created: 2026-10-07
updated: 2026-10-07
dimensions: [anomaly-detection-and-change-point-methods, network-intrusion-and-anomaly-detection]
sources: [../sources/pyod-project.md, ../sources/cic-ids2017-documentation.md]
---

## Summary

Assign a score to observations that deviate from an assumed reference population. In security, an outlier score supports triage; unusual is not synonymous with malicious.

## Key points

- Inputs: numerical or encoded flow, host or event features with a documented training period and treatment of missing values.
- Baselines: isolation forest and local outlier factor are available in [PyOD](../tools/pyod.md); compare with a simple supervised classifier when labels are reliable.
- Training on contaminated or shifting "normal" traffic and choosing a threshold against test labels will bias results.

## Details

### Evaluation

Define a historical training window, later validation window and untouched test window. Estimate a threshold at a specified alert budget; report precision-recall, detection delay and false alerts per unit of traffic under explicit prevalence. Retraining and score drift need monitoring. Performance and runtime must be measured for the chosen features; the PyOD catalogue is not a cybersecurity benchmark.

## Related

- [Network intrusion detection](../challenges/network-intrusion-detection.md).
- [CIC-IDS2017](../data/cic-ids2017.md).

## References

- [PyOD project documentation](../sources/pyod-project.md).
- [CIC-IDS2017 documentation](../sources/cic-ids2017-documentation.md).
