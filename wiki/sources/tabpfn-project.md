---
title: TabPFN project documentation
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: official software documentation
publisher: Prior Labs
published: unknown
accessed: 2026-10-07
dimensions: [generative-and-foundation-models, supervised-and-semi-supervised-learning, open-source-ecosystem-and-maintenance]
sources: []
---

## Summary

The [TabPFN repository](https://github.com/PriorLabs/TabPFN) describes pretrained tabular prediction models that condition on a dataset at inference time, together with local software for classification and regression.

## Key points

- The repository links a [published TabPFNv2 paper](https://doi.org/10.1038/s41586-024-08328-6) and separate reports for later checkpoints; the current software cannot be evaluated as if it were identical to the paper's model.
- The repository describes its code as Apache-2.0, while the current default model weights carry separate non-commercial terms. Check the exact checkpoint licence before a study or deployment.
- Local inference and a separately offered hosted client differ in data-handling implications; local work still downloads model weights on first use.

## Details

### Research use and limits

Test a pinned model/checkpoint and record hardware, sample count, features, inference time and licence. Compare against conventional baselines under identical temporal splits and prevalence; do not transfer general tabular benchmark claims to cybersecurity without an evaluation. The publication site for the linked Nature paper redirected to a login during this research, so this page does not assert detailed paper results.

## Related

- [Tabular foundation models](../methods/tabular-foundation-models.md).
- [Prior Labs](../providers/prior-labs.md).

## References

- Prior Labs, [TabPFN project README](https://github.com/PriorLabs/TabPFN), current project documentation; accessed 2026-10-07.
