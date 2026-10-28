---
title: EMBER2024 paper and repository
type: source
aliases: [EMBER2024 documentation]
created: 2026-10-07
updated: 2026-10-07
source_class: peer-reviewed conference paper and official project documentation
publisher: ACM SIGKDD and EMBER2024 maintainers
published: 2025
accessed: 2026-10-07
dimensions: [malware-and-malicious-code, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: []
---

## Summary

Joyce et al., [EMBER2024](https://arxiv.org/abs/2506.05074), describe a multi-format static-feature malware benchmark; the [official repository](https://github.com/FutureComputing4AI/EMBER2024/) documents downloads, baseline code and dataset partitions. The arXiv record links the conference DOI; the repository cites the 2025 ACM SIGKDD proceedings.

## Key points

- The authors report features, hashes, metadata and labels for more than 3.2 million files across Win32, Win64, .NET, APK, PDF and ELF formats, with seven label and tag types.
- The repository specifies 2,626,000 training and 606,000 test files from consecutive weeks between September 2023 and December 2024. It also describes a separate set of 6,315 malicious files initially missed by antivirus products.
- File-type and split-specific downloads permit smaller feature-only experiments; the listed PDF and ELF training feature archives are about 197 MB and 100 MB respectively. The code repository declares Apache-2.0, but dataset redistribution rights and current download terms require a separate check.

## Details

### Evaluation and limits

The chronological split is better suited to measuring within-source time shift than random rows, but a VirusTotal-derived sample and antivirus-informed labels do not represent deployment prevalence or independent ground truth. The challenge set was selected on an antivirus failure criterion and is not a random test set. Record the downloaded subset, hashes, feature version, label mapping, split and baseline settings before claiming reproduction. No dataset was downloaded or malware handled for this wiki update.

## Related

- [Malware detection](../challenges/malware-detection.md).
- [EMBER](../data/ember.md), the distinct older 2017/2018 benchmark lineage.

## References

- Joyce et al., [EMBER2024: A Benchmark Dataset for Holistic Evaluation of Malware Classifiers](https://arxiv.org/abs/2506.05074), submitted 2025-06-05; linked [ACM DOI](https://doi.org/10.1145/3711896.3737431), 2025; accessed 2026-10-07.
- EMBER2024 maintainers, [project README](https://github.com/FutureComputing4AI/EMBER2024/), accessed 2026-10-07.