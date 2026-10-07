---
title: CIC-IDS2017
type: data
aliases: [CICIDS2017]
created: 2026-10-07
updated: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: [../sources/cic-ids2017-documentation.md]
---

## Summary

Five days of labelled lab network traffic (3-7 July 2017) with PCAP and derived bidirectional flow CSV files. Owner: Canadian Institute for Cybersecurity, University of New Brunswick.

## Key points

- Population: a controlled office-like testbed, not a sampled enterprise network; Monday is described as normal traffic, with scheduled attacks later in the week.
- Schema: more than 80 flow features, traffic labels and scenario timings; distinguish flow-level from packet-level analysis.
- Access: [official dataset page](https://www.unb.ca/cic/datasets/ids-2017.html); distribution rights and downloaded-file integrity need checking before use. No data is stored here.

## Details

### Study design

Record the exact file set, preprocessing, label mapping, flow extractor and missing-value handling. Split by day or scenario where possible; using a random row split risks time, host or scenario leakage. Compare label-aware baselines with an unsupervised detector, assess class imbalance and report false alerts at an operationally plausible threshold. Even a held-out day from this testbed is not an independent site. Individual labels, privacy posture, and licence terms have not been audited here.

## Related

- [Network intrusion detection](../challenges/network-intrusion-detection.md).
- [Anomaly detection](../methods/anomaly-detection.md).

## References

- [CIC-IDS2017 source record](../sources/cic-ids2017-documentation.md), accessed 2026-10-07.
