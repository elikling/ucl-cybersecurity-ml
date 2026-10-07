---
title: Zeek
type: tool
aliases: [Bro]
created: 2026-10-07
updated: 2026-10-07
checked: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, open-source-ecosystem-and-maintenance]
sources: [../sources/zeek-project.md]
---

## Summary

Community-developed, BSD-licensed network traffic analysis and security-monitoring framework; see the [official repository](https://github.com/zeek/zeek).

## Key points

- Produces protocol and connection observations useful for feature engineering and investigation; scripting supports local monitoring policy.
- A sensor must be deployed with appropriate traffic visibility and retention controls. No hosted-service price or release-specific compatibility was assessed.

## Details

### Suitability

For a local experiment, select a stable release, document packet capture permission, collection point, parser options, log schema and compute needs. Test whether encrypted or dropped traffic makes critical fields unavailable. Do not assume Zeek outputs automatically supply correct attack labels or the same fields as another benchmark.

## Related

- [Network intrusion detection](../challenges/network-intrusion-detection.md).
- [Suricata](suricata.md).

## References

- [Zeek project source record](../sources/zeek-project.md), checked 2026-10-07.
