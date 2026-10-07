# Cybersecurity research wiki

This wiki is the project's linked, source-grounded map of statistical modelling and machine learning for cybersecurity. It supports the UCL student research project by connecting security challenges to methods, data, software, providers, evidence, and research gaps. It is a curated evidence base, not a substitute for the original sources.

Start with the [research index](index.md) or the [comparison-led landscape](syntheses/research-landscape.md).

## Structure

```text
wiki/
|-- README.md
|-- index.md
|-- taxonomy.md
|-- timeline.md
|-- log.md
|-- sources/
|-- challenges/
|-- methods/
|-- data/
|-- tools/
|-- providers/
|-- concepts/
|-- people/
|-- organisations/
|-- developments/
`-- syntheses/

raw/
|-- papers/
|-- reports/
|-- standards/
|-- datasets/
|-- software/
`-- web/
```

Keep source captures immutable. Store only material that may lawfully be retained; for large datasets and restricted publications, keep provenance, metadata, access instructions, and research notes rather than the full artefact. A source selected by the user may still have licensing or privacy constraints that prevent local copying.

## Knowledge dimensions

Pages may carry multiple dimensions. Use the controlled labels below and add a new label only when it fills a durable, distinct gap; record taxonomy changes in `taxonomy.md`.

### Cybersecurity challenges

- `network-intrusion-and-anomaly-detection`
- `malware-and-malicious-code`
- `phishing-and-social-engineering`
- `identity-authentication-and-fraud`
- `vulnerability-discovery-and-management`
- `threat-intelligence-and-attribution`
- `incident-response-and-forensics`
- `cloud-container-and-platform-security`
- `iot-ot-and-cyber-physical-security`
- `software-supply-chain-security`
- `privacy-and-data-protection`
- `adversarial-machine-learning-and-ai-security`
- `security-operations-and-risk-governance`

### Statistical and machine-learning approaches

- `statistical-inference-and-experimental-design`
- `anomaly-detection-and-change-point-methods`
- `supervised-and-semi-supervised-learning`
- `unsupervised-and-self-supervised-learning`
- `time-series-and-sequence-modelling`
- `graph-and-relational-learning`
- `natural-language-and-code-modelling`
- `deep-learning-and-representation-learning`
- `generative-and-foundation-models`
- `agents-and-tool-using-systems`
- `causal-modelling-and-intervention`
- `federated-and-privacy-preserving-learning`
- `interpretability-and-explainability`
- `robustness-uncertainty-and-distribution-shift`

### Cross-cutting evidence and practice

- `datasets-labels-and-provenance`
- `evaluation-benchmarks-and-reproducibility`
- `deployment-systems-and-cost`
- `privacy-law-and-data-governance`
- `dual-use-safety-and-responsible-disclosure`
- `open-source-ecosystem-and-maintenance`
- `research-gaps-and-opportunities`

## Page types

- `source`: one paper, preprint, standard, technical report, official documentation page, dataset page, software project, or other selected source.
- `challenge`: a security problem, threat model, attacker capability, defender objective, or operational constraint.
- `method`: a statistical model, ML technique, evaluation procedure, or analysis workflow.
- `data`: a dataset or benchmark with provenance, access, licensing, and limitations.
- `tool`: an open-source library, repository, benchmark implementation, or research utility.
- `provider`: a service or vendor offering models, data, platforms, or security capabilities.
- `concept`: a reusable idea not better represented by another page type, such as calibration or concept drift.
- `person`, `organisation`, `development`: named researchers, institutions, and dated releases, findings, or events.
- `synthesis`: a comparison, trend, evidence gap, or research question supported by at least two independent sources.

Do not create a page simply to populate a type. Prefer separate records for a source and the reusable method, dataset, or tool it discusses. Avoid duplicating the same entity across categories.

## Common page format

Use this frontmatter and section structure for every page. Add type-specific fields and subsections as needed.

```yaml
---
title: Canonical page title
type: source
aliases: []
created: 2026-10-07
updated: 2026-10-07
dimensions: []
sources: []
---
```

```markdown
## Summary

## Key points

## Details

## Related

## References
```

Use ISO dates. Use relative Markdown links to canonical pages. Record `checked` or `verified_on` dates for facts that change, such as software versions, provider availability, data access, and standards status. Do not replace an unknown value with a guess.

## Type-specific evidence

Source pages should record authors, source class, venue or publisher, publication/version date, original URL, access date, and any lawful raw capture. Under Details, cover the question, threat model, method, data, evaluation, results, limitations, reproducibility, and defensive or dual-use implications where evidence is available.

Challenge pages should describe assets, adversary capabilities, assumptions, defender objective, operational context, impact, and how success is measured. Method pages should describe inputs, assumptions, training/inference, baselines, metrics, compute/deployment needs, and failure modes. Do not conflate a research method with the tool that implements it.

Data pages should record owner/provenance, collection period, population, schema and labels, access route, licence/terms, privacy constraints, known biases, representativeness, split strategy, leakage risks, benchmark version, and known limitations. Never add a full dataset to this repository by default.

Tool and provider pages should record maintainer, official URL, licence, supported versions, maintenance/status check date, deployment model, costs or access constraints, dependencies, security/privacy considerations, and known limitations. Mark vendor statements as vendor-provided claims.

Synthesis pages should state scope and date, compare evidence rather than merely list sources, identify agreement and conflict, distinguish established findings from hypotheses, expose evidence gaps, and propose testable research questions. Link each material conclusion to its supporting source pages.

## Curation and maintenance

1. Curate only sources selected by the user. Preserve permitted raw captures unchanged; use metadata and links where copying is restricted.
2. Search canonical titles and aliases before creating pages. Update existing pages when a source adds evidence; do not create near-duplicate entities.
3. Connect each source to supported challenges, methods, data, tools/providers, concepts, people, organisations, and developments. Omit unsupported relationships rather than infer them.
4. Update `index.md`, `taxonomy.md`, `timeline.md`, and `log.md` whenever those generated or navigation files are present. Keep indexes and timelines consistent with canonical pages.
5. On maintenance, review software/provider/data-access details older than 180 days and standards/regulatory guidance older than 365 days. These thresholds trigger a check; they do not establish that information is obsolete.
6. Check structure, provenance, links, duplicate candidates, orphans, stale records, and synthesis evidence. Make clear additive fixes; ask before destructive consolidation.

The repeatable workflows are described in `.github/skills/cybersecurity-source-curation/`, `.github/skills/cybersecurity-evidence-synthesis/`, and `.github/skills/cybersecurity-wiki-maintenance/`.
