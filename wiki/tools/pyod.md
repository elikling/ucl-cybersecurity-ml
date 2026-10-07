---
title: PyOD
type: tool
aliases: []
created: 2026-10-07
updated: 2026-10-07
checked: 2026-10-07
dimensions: [anomaly-detection-and-change-point-methods, open-source-ecosystem-and-maintenance]
sources: [../sources/pyod-project.md]
---

## Summary

Python outlier-detection library maintained by the PyOD project, with a common fit/score workflow across many detectors; [official repository](https://github.com/yzhao062/pyod).

## Key points

- BSD-2-Clause code licence according to the maintainers; package and dependency versions should be pinned for a reproducible study.
- Local model training is possible without sending telemetry to a hosted provider; memory and runtime depend on detector and dataset size.

## Details

### Suitability

Start with isolation forest or local outlier factor on suitably scaled flow features; document any detector-specific preprocessing. Thresholds require a separate validation period. The optional agent-facing features are not needed for a statistical baseline and should not be confused with the core anomaly API. No version-specific installation test was performed.

## Related

- [Anomaly detection](../methods/anomaly-detection.md).
- [CIC-IDS2017](../data/cic-ids2017.md).

## References

- [PyOD project source record](../sources/pyod-project.md), checked 2026-10-07.
