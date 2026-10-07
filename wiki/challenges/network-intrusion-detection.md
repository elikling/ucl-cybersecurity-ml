---
title: Network intrusion detection
type: challenge
aliases: [network anomaly detection]
created: 2026-10-07
updated: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, anomaly-detection-and-change-point-methods]
sources: [../sources/cic-ids2017-documentation.md, ../sources/unsw-nb15-documentation.md]
---

## Summary

Identify suspicious network activity from packet, flow or protocol telemetry while limiting false alerts. The defender usually observes incomplete traffic, evolving benign behaviour and delayed or uncertain incident labels.

## Key points

- Asset and impact: service availability, confidentiality and analyst time; detection should support triage rather than imply an automatic attribution.
- Adversary may vary timing, traffic shape and protocol use; a lab benchmark only represents the scenarios captured by its creators.
- Decide first whether the question is known-attack classification, novelty detection or alert prioritisation: each needs different labels and metrics.

## Details

### Measurement

Report detection delay, recall by attack class, precision at expected prevalence, false alerts per day or traffic volume, and calibration where probabilities are used. Hold out hosts, days or collection environments; record label latency and leakage checks. On [CIC-IDS2017](../data/cic-ids2017.md) the attack schedule may be learnable without malicious behaviour; [UNSW-NB15](../data/unsw-nb15.md) provides a second, still synthetic, environment. Zeek telemetry and Suricata alerts are different observational inputs, not interchangeable labels.

## Related

- [Anomaly detection](../methods/anomaly-detection.md).
- [Zeek](../tools/zeek.md) and [Suricata](../tools/suricata.md).

## References

- [CIC-IDS2017 documentation](../sources/cic-ids2017-documentation.md).
- [UNSW-NB15 documentation](../sources/unsw-nb15-documentation.md).
