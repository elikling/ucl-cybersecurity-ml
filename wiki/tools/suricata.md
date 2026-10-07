---
title: Suricata
type: tool
aliases: []
created: 2026-10-07
updated: 2026-10-07
checked: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, open-source-ecosystem-and-maintenance]
sources: [../sources/suricata-project.md]
---

## Summary

OISF's GPL-2.0 network intrusion detection, prevention and monitoring engine; see the [official repository](https://github.com/OISF/suricata).

## Key points

- Rules and alert output can provide a transparent comparator in a network-detection experiment.
- Rule set, engine version and placement determine observed alerts; rule matches are not independent labels of ground truth.

## Details

### Suitability

For a replay or authorised capture, pin software, rules, configuration and traffic source and measure throughput and false alerts. Inline prevention carries availability risks that a passive benchmark does not model. Cost depends on sensor infrastructure and operational review, not only the licence. No local benchmark or deployment was run.

## Related

- [Network intrusion detection](../challenges/network-intrusion-detection.md).
- [Zeek](zeek.md).

## References

- [Suricata project source record](../sources/suricata-project.md), checked 2026-10-07.
