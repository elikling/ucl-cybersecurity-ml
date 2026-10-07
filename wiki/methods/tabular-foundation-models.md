---
title: Tabular foundation models
type: method
aliases: [pretrained tabular prediction]
created: 2026-10-07
updated: 2026-10-07
dimensions: [generative-and-foundation-models, supervised-and-semi-supervised-learning]
sources: [../sources/tabpfn-project.md, ../sources/ember-project.md]
---

## Summary

Pretrained tabular models such as TabPFN use prior training to produce predictions conditioned on a new dataset. Their possible value for cyber telemetry and PE features must be established experimentally, not inferred from generic tabular results.

## Key points

- Inputs: cleaned tabular features and labelled training examples; pin checkpoint, feature count, sample count and weight licence.
- Baseline: matched tree ensemble or logistic regression, with identical temporal split, prevalence and tuning budget.
- TabPFN's current code and weights have distinct licences; first-download and hosted inference can affect data governance.

## Details

### Evaluation

On a permissible subset of [EMBER](../data/ember.md) or [CIC-IDS2017](../data/cic-ids2017.md), compare recall at a fixed false-positive rate, calibration, runtime and RAM against the baseline. Respect model input limits, avoid leakage through feature engineering, and report whether features shift across time. The TabPFN project's claimed broad-domain results do not establish malware or intrusion performance.

## Related

- [Prior Labs](../providers/prior-labs.md).
- [Malware detection](../challenges/malware-detection.md).

## References

- [TabPFN source record](../sources/tabpfn-project.md).
- [EMBER source record](../sources/ember-project.md).
