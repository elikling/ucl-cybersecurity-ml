---
title: UNSW-NB15
type: data
aliases: []
created: 2026-10-07
updated: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: [../sources/unsw-nb15-documentation.md]
---

## Summary

UNSW Canberra cyber-range capture with normal and synthetic malicious traffic, packet records, engineered network features and attack labels; intended as an intrusion benchmark.

## Key points

- The owner reports 2,540,044 records, 49 features, nine attack categories and a smaller provided train/test partition.
- Use the [official project page](https://research.unsw.edu.au/projects/unsw-nb15-dataset) for downloads and conditions: academic use is permitted with citation; commercial use needs author agreement.
- Older laboratory traffic and synthetic attacks limit the inference one can make about today's production networks.

## Details

### Study design

Record whether the provided split or a new chronological/environmental split was used, the precise CSV/PCAP version and preprocessing. Report each attack family and false-positive burden, not only aggregate accuracy. If comparing to CIC-IDS2017, train and test within each corpus first; different feature definitions and label taxonomies do not support a naive pooled result. Availability, privacy properties and label reliability need checking before analysis.

## Related

- [CIC-IDS2017](cic-ids2017.md).
- [Network intrusion detection](../challenges/network-intrusion-detection.md).

## References

- [UNSW-NB15 source record](../sources/unsw-nb15-documentation.md), accessed 2026-10-07.
