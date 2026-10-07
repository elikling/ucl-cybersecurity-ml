---
title: CIC-IDS2017 dataset documentation
type: source
aliases: [CICIDS2017 documentation]
created: 2026-10-07
updated: 2026-10-07
source_class: official dataset documentation
publisher: Canadian Institute for Cybersecurity, University of New Brunswick
published: unknown
accessed: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: []
---

## Summary

The [University of New Brunswick dataset page](https://www.unb.ca/cic/datasets/ids-2017.html) documents CIC-IDS2017, a five-day labelled network-traffic collection from 3-7 July 2017. It provides packet captures and derived flow features for intrusion-detection experiments.

## Key points

- The authors describe Monday as benign traffic and Tuesday-Friday as benign traffic mixed with scheduled attack scenarios; this schedule can introduce shortcut features if splits are not designed carefully.
- The page lists more than 80 extracted flow features and documents the capture environment and attack timing.
- Public research access is described on the source page; recheck its terms and download location before obtaining data.

## Details

### Research use

Compare classical statistical anomaly detection and supervised baselines with modern tabular methods on labelled flows. Report false-positive rate, precision/recall or precision-recall area, class balance, and results on held-out days or environments; random row splits alone cannot establish deployment generalisation.

### Evidence limits

The source describes a controlled 2017 lab network with scheduled scenarios. Its claims about realism are the dataset authors' assessment, not evidence that current production traffic has the same distribution. This page does not claim that the download, licence for redistribution, or individual labels have been independently audited.

## Related

- [Network intrusion detection](../challenges/network-intrusion-detection.md).
- [CIC-IDS2017](../data/cic-ids2017.md).

## References

- Canadian Institute for Cybersecurity, University of New Brunswick, [Intrusion detection evaluation dataset (CIC-IDS2017)](https://www.unb.ca/cic/datasets/ids-2017.html), publication date not stated; accessed 2026-10-07.