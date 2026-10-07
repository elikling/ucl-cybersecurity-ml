---
title: EMBER
type: data
aliases: [EMBER2017, EMBER2018]
created: 2026-10-07
updated: 2026-10-07
dimensions: [malware-and-malicious-code, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: [../sources/ember-project.md]
---

## Summary

Elastic's static-feature Windows PE malware classification benchmark includes distinct 2017 and 2018 releases and baseline code. It is not itself a collection of downloadable executable samples.

## Key points

- Owner-reported scale: 1.1 million samples (2017) and one million (2018); versions differ in selection criteria.
- Use the [official repository](https://github.com/elastic/ember) for data access, code and project terms; the project was archived on 2026-04-13.
- Licence for dataset reuse, underlying sample privacy and individual label reliability have not been independently established here.

## Details

### Study design

Pin release, feature schema, LIEF version, label handling and split. Compare a LightGBM baseline with a calibrated alternative; report recall at low false-positive rates and distribution shift rather than accuracy alone. Do not treat a held-out slice of EMBER as proof of resilience to current malware, and do not merge the releases without accounting for selection changes. No malware binaries are stored in this wiki.

## Related

- [Malware detection](../challenges/malware-detection.md).
- [Tabular foundation models](../methods/tabular-foundation-models.md).

## References

- [EMBER source record](../sources/ember-project.md), accessed 2026-10-07.
