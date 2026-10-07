---
title: SoReL-20M project documentation
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: official software and dataset documentation
publisher: Sophos and ReversingLabs
published: 2020
accessed: 2026-10-07
dimensions: [malware-and-malicious-code, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: []
---

## Summary

The [SoReL-20M repository](https://github.com/sophos/SOREL-20M) describes a large PE malware-detection dataset with metadata, features, disarmed malware samples, and code for feed-forward-network and LightGBM baselines.

## Key points

- The README estimates about 8 TB for the full dataset and about 78 GB for the minimal files used to retrain its neural baseline; do not clone the data into this wiki.
- Benign executables are not freely available, and labels use partly non-public information; access and label provenance must be treated as constraints.
- The repository's Apache-2.0 code licence is separate from the dataset terms of use, which readers must inspect before access.

## Details

### Evaluation and limits

The project documents temporal train/validation/test splits, but reproducing the full experiment may require substantial storage and memory. An undergraduate project should first check feasible feature-only access, dataset terms, and whether the available representation supports a fair comparison. Do not retrieve or execute malware samples as part of this wiki work.

## Related

- [Malware detection](../challenges/malware-detection.md).
- [EMBER](../data/ember.md).

## References

- Sophos and ReversingLabs, [SoReL-20M repository](https://github.com/sophos/SOREL-20M), 2020 project and linked [preprint](https://arxiv.org/abs/2012.07634); accessed 2026-10-07.
