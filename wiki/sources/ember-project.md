---
title: EMBER project documentation
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: official software and dataset documentation
publisher: Elastic
published: unknown
accessed: 2026-10-07
dimensions: [malware-and-malicious-code, datasets-labels-and-provenance, evaluation-benchmarks-and-reproducibility]
sources: []
---

## Summary

The [EMBER repository](https://github.com/elastic/ember) describes features extracted from Windows portable executable (PE) files, dataset releases for 2017 and 2018, and code for reproducible static malware classification baselines.

## Key points

- The project reports 1.1 million samples for EMBER2017 and one million for EMBER2018. These are features, not a complete openly distributed collection of original binaries.
- Feature extraction depends on a versioned LIEF library; the README warns that comparing features generated with different versions can produce unpredictable results.
- The GitHub repository was archived on 2026-04-13. Treat its code as a historical benchmark rather than an actively maintained dependency.

## Details

### Evaluation and limits

The README warns that selection criteria differ between 2017 and 2018; a naive pooled longitudinal study is not controlled. Use temporal holdouts, document feature version and label assumptions, and compare against the repository's LightGBM baseline. Dataset download links and redistribution terms were not independently tested here.

## Related

- [EMBER](../data/ember.md).
- [Malware detection](../challenges/malware-detection.md).

## References

- Elastic, [EMBER repository and dataset README](https://github.com/elastic/ember), publication date not stated; accessed 2026-10-07. The README cites Anderson and Roth, *EMBER: An Open Dataset for Training Static PE Malware Machine Learning Models* (2018).
