---
title: UNSW-NB15 dataset documentation
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
source_class: official dataset documentation
publisher: UNSW Canberra
published: unknown
accessed: 2026-10-07
dimensions: [network-intrusion-and-anomaly-detection, datasets-labels-and-provenance]
sources: []
---

## Summary

The [UNSW project page](https://research.unsw.edu.au/projects/unsw-nb15-dataset) describes a laboratory network-intrusion benchmark generated with normal and synthetic attack traffic. It offers packets, Bro/Zeek and Argus outputs, CSV features, labels, and predefined training and test partitions.

## Key points

- The authors report 2,540,044 records, 49 features, nine attack categories, and a provided subset of 175,341 training and 82,332 test records.
- UNSW grants free academic research use, requires citation, and asks users to agree commercial use with the authors; availability of linked external downloads was not checked.
- This dataset is a useful second environment for testing whether results on CIC-IDS2017 are specific to one capture, not evidence of production generalisation.

## Details

### Evaluation and limits

Record which of the full or provided partitions is used; harmonise only semantically comparable features across datasets. The source says attack traffic is synthetic in a cyber range. This page does not verify the sampling strategy, temporal split properties, or label quality independently. The project page lists a last-updated date of 2021-06-02, but the dataset publication it cites is from 2015.

## Related

- [UNSW-NB15](../data/unsw-nb15.md).
- [Network intrusion detection](../challenges/network-intrusion-detection.md).

## References

- UNSW Canberra, [The UNSW-NB15 Dataset](https://research.unsw.edu.au/projects/unsw-nb15-dataset), page last updated 2021-06-02; accessed 2026-10-07.
