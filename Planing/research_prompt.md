# Generative Data Science for Cybersecurity

## Project purpose

This UCL student research project will investigate how innovations in generative AI, statistical modelling and machine learning could help Avanade shape a cybersecurity analyst value proposition focused on detecting and investigating potentially malicious behaviour. It will combine a focused evidence review, reproducible benchmarking and an agentic system that enhances and enriches the work of cybersecurity modellers, demonstrated in a context relevant to Avanade's Security Practice.

The aim is to establish where these approaches offer measurable value, where established methods remain preferable, and how the findings could shape an accelerator offering. The project will produce defensible findings and a practical recommendation, not assume that newer models outperform existing tools or deliver a production security system.

## Research focus and scope

For this project, **Generative Data Science** is a working umbrella for three related but distinct strands:

| Strand | Project interpretation | Proposed investigation |
| --- | --- | --- |
| Generative AI assistance | Tools that help an analyst formulate questions, write analysis code and explain results. | Explore useful assistance points and require evidence for generated conclusions. |
| Agentic modelling team/system (Agentic Meta-Statistician) | A coordinated set of AI roles, reusable skills and analytical tools that works with cybersecurity modellers across the modelling lifecycle, under human oversight. | Develop and evaluate a prototype that enriches problem formulation, data understanding, experimental design, model comparison and interpretation, including explicit meta-statistician skills for reviewing the reasoning behind an analysis. |
| Tabular foundation models | Pre-trained models for tabular prediction, considered separately from generative assistants. | Benchmark a suitable model, such as TabPFN, against established baselines and selected novel statistical and machine-learning approaches; investigate adaptation or fine-tuning only if justified and feasible. |

Begin with a broad review of cybersecurity problem areas, then select **one primary defensive detection task** by the end of Sprint 1. The preferred starting point is detecting anomalous or potentially malicious behaviour in structured security logs or network-flow records. Web-log analysis remains a candidate, subject to suitable data and labels; network-flow benchmarks must not be presented as web-log evidence.

The minimum experimental scope is one primary dataset, a small set of credible baselines, one suitable tabular foundation model and a prototype agentic modelling team supporting one end-to-end modelling workflow. Add a further novel comparator only where supported by the review and available resources. A second dataset or environment is a stretch goal for testing generalisation. Fine-tuning, unrestricted agent autonomy and production deployment are outside the minimum scope.

Existing [candidate study designs](../wiki/syntheses/research-questions.md) provide a starting point for selection, not evidence that a particular approach will succeed.

## Research questions

1. **Detection:** How does a tabular foundation model compare with established baselines and selected novel approaches in detection accuracy, sensitivity and recall at a fixed false-alert budget, within an agreed compute budget?
2. **Agentic modelling support:** Can an agentic team with meta-statistician skills and tools improve the quality, breadth and efficiency of cybersecurity modelling compared with a modeller using a fixed, non-agent workflow? Does it identify more material data or design problems, produce better-justified model comparisons and improve reproducibility without increasing analytical errors?
3. **Practical integration and value proposition:** What data preparation, governance, cost and human-review requirements would an Azure and Microsoft Fabric demonstrator expose, and how could the findings inform an Avanade accelerator offering and the decision to pursue an operational pilot?

Detection performance and support for cybersecurity modellers will be evaluated separately. A more fluent explanation is not evidence of better detection, and a benchmark improvement is not evidence of fewer real-world breaches. Any claimed downstream benefit to security analysts must be distinguished from benefits measured in the modelling workflow.

## Work programme

### 1. Security discovery and task selection

- Interview Avanade security practitioners, including cybersecurity modellers where available, to identify a concrete decision or investigation that the project could support, the current workflow and the consequences of false positives and missed threats.
- Map where modelling support could add value to Avanade's cybersecurity analyst offering, distinguishing the modeller's development workflow from the security analyst's operational workflow.
- Agree a task statement covering the intended user, unit of analysis, available data, prediction target or anomaly definition, and how results would be reviewed.
- Select the task using practitioner relevance, lawful data access, label quality, reproducibility and student-team capacity. Record rejected alternatives and the reasons for the choice.
- Confirm success criteria, project responsibilities, compute and cloud budgets, and access dependencies with the academic and practice sponsors.

### 2. Focused literature and evidence review

Prioritise sources published in the two years preceding the review date, recording the exact date window. Include older foundational work where needed. Use peer-reviewed papers and reputable technical reports for core evidence; distinguish preprints, official documentation, vendor claims and informal discussion. Practitioner blogs and social-media discussions may identify emerging issues, but their claims require corroboration before informing conclusions.

Map cybersecurity challenges, methods, strengths, limitations and open gaps. Identify public datasets and benchmarks, recording collection period, contents, labels, access conditions, licence, privacy concerns and comparability limitations. Public availability alone does not establish permission to use or redistribute data.

Produce a concise overview and a comparison table with columns for **cybersecurity problem area, challenge, methods, evidence and limitations, research gap, and relevant datasets or benchmarks**. Cite substantive claims with source links and publication dates, and distinguish findings from hypotheses. Build on the existing [research landscape](../wiki/syntheses/research-landscape.md) and record newly curated evidence in the research wiki.

### 3. Reproducible detection benchmark

- Confirm that each selected model supports the task, dataset size and permitted usage. Do not assume a predictive model provides anomaly detection without a justified scoring method.
- Use a compact baseline set appropriate to the labels and task, for example a simple statistical or linear model, a tree-based model and an established anomaly detector. Select any additional novel comparator from the literature review, documenting its rationale and giving methods comparable tuning and compute budgets.
- Freeze the evaluation protocol before inspecting test results: preprocessing, feature exclusions, training and validation splits, tuning budget, decision thresholds and primary metrics. Fit transformations on training data only, and use validation data to select thresholds.
- Prefer temporal or environment-level hold-outs where the dataset supports them. Check duplicate records, identifiers, target leakage, class imbalance and label provenance; document limitations when realistic splits are unavailable.
- Report recall at the agreed false-alert budget as the primary detection comparison, with accuracy, precision, precision-recall AUC, false-positive rate and per-class results where labels support them. Interpret detection "power" as sensitivity to the defined malicious class at a stated false-positive rate; distinguish this from statistical power for a hypothesis test. Do not use overall accuracy alone on imbalanced data. Report false-alert counts for a stated sample size and prevalence, not as an unqualified estimate of live SOC workload.
- Record uncertainty using a method appropriate to dependent records, repeat stochastic runs where feasible, and report training/inference time, memory, compute cost and calibration where relevant.
- Pin dataset releases, model versions, configurations and random seeds. Retain scripts and result artefacts that reproduce the comparison, including negative results.

### 4. Agentic modelling team with meta-statistician skills and tools

Develop a prototype agentic team/system that enhances and enriches the work of cybersecurity modellers, rather than simply generating analysis code or summarising results. Its working name is **Agentic Meta-Statistician**; this is a project label, not a claim that it is an established method. Use the detection study as a shared case through which the system can help formulate questions, challenge assumptions, execute approved analyses and improve the resulting evidence.

Unlike ad hoc generative AI assistance, the system should coordinate explicit roles, tool use and review steps around a shared experimental record. Keep the implementation small: roles may share a model or run sequentially, and do not require separate autonomous agents or a complex multi-agent platform.

| Role or capability | Contribution to the modeller's work | Example skills and tools |
| --- | --- | --- |
| Coordination and problem formulation | Translate the security question into a modelling objective, organise tasks and request human decisions. | Task planning, agreed success criteria, shared experiment record and approval checkpoints. |
| Data understanding | Assess whether the available data can support the question and identify problems before modelling. | Data profiling, label and provenance checks, missingness and imbalance diagnostics, duplicate and leakage checks. |
| Experimentation and model comparison | Execute approved experiments and compare credible alternatives consistently. | Versioned notebooks or scripts, statistical and ML libraries, experiment tracking, resource and cost measurement. |
| Meta-statistical review | Examine whether the modelling choices and conclusions are statistically justified, not merely whether code runs. | Assumption checking, split and validation design, metric and threshold selection, uncertainty and calibration assessment, robustness checks and critique of unsupported conclusions. |
| Interpretation and evidence synthesis | Explain findings in security terms, expose limitations and propose justified next steps. | Traceable result tables, evidence-linked reporting and clear separation of observations, hypotheses and recommendations. |

Define the skills as reusable analysis and review procedures with explicit inputs, outputs and checks, and connect them to executable tools where appropriate. Record role hand-offs, review findings and the modeller's decisions. Human approval is required for material changes to the experiment; agent suggestions must not alter the frozen test protocol without a documented revision and independent evaluation data.

Evaluate a modeller using the system against a modeller using a fixed scripted or notebook workflow on equivalent predefined tasks, with comparable data, resources and time limits. Agree a scoring rubric before evaluation: analytical correctness, material issues correctly identified, coverage and justification of modelling choices, reproducibility, evidence quality, unsupported claims, completion time, human corrections and cost. Assess whether useful additional insight is produced, not simply whether more output is generated. Where feasible, compare with meta-statistical review disabled to test the contribution of those skills specifically.

Use practitioner or supervisor review where available, with blinded scoring and counterbalanced task order where feasible. Report the participants and evaluation conditions; do not generalise student-only or automated results to professional modeller productivity. Treat this as a small exploratory study if the sample cannot support stronger conclusions.

Keep agent development separate from final assessment tasks. Treat log content as untrusted input, restrict tool and data access, and record model versions, prompts, tool calls and human corrections where permitted. Use approved services and authorised data only; do not send sensitive logs to external models without explicit approval.

### 5. Azure and Microsoft Fabric demonstrator

Show a traceable journey from an authorised dataset through preparation, scoring and an analyst-facing result, alongside the agentic team's support for the modeller. Demonstrate a meta-statistical review finding, the human decision it prompts and the resulting evidence trail. A candidate architecture is Microsoft Fabric for data preparation and reporting, with Azure-hosted compute or model services for scoring and controlled agent execution. Confirm service availability, licensing, model compatibility, permissions and cost before committing to this design.

The demo should make baseline and candidate results comparable, expose false positives and uncertainty, and show where human judgement remains necessary. Use public or approved sanitised data; do not connect to production security systems. If cloud access is delayed, use reproducible local execution and clearly label any recorded results or illustrative integration steps. Do not present a proposed integration as a working one.

## Deliverables and acceptance criteria

| Deliverable | Intended audience | Acceptance criteria |
| --- | --- | --- |
| Technical presentation and supporting report | Data scientists, statisticians and security specialists | A sourced literature comparison, explicit study design, benchmark results with uncertainty, separate agent evaluation, limitations and recommendations. |
| Reproducible benchmark package | Student team and future researchers | Documented data access, pinned dependencies and models, runnable analysis, recorded configurations and results; no restricted data or secrets committed. |
| Agentic Meta-Statistician prototype | Cybersecurity modellers and research supervisors | A coordinated modelling workflow with documented roles, reusable meta-statistician skills, executable tools, human review and a comparative evaluation of analytical quality and efficiency. |
| Engaging Azure/Fabric demonstrator | Security practitioners and technical stakeholders | A repeatable scenario showing the analysis journey and comparative results, with working and illustrative components clearly distinguished and a recorded fallback. |
| Executive pitch for a proposed accelerator | Avanade practice and business stakeholders | A defined cybersecurity analyst value proposition, evidence of benefits and limitations for modellers and analysts, proposed reusable components and service offering, indicative costs and risks, and a recommendation to proceed, revise or stop. |

Success means a credible answer to the research questions, not necessarily a performance improvement. An inconclusive or negative result is useful when it is reproducible and explains the conditions under which an approach is unsuitable.

## Sprint plan and decision gates

The intended teaching window is January to March, with three-week sprints. **Five such sprints require 15 weeks and therefore cannot fit wholly within January to March.** Confirm dates with UCL before committing: either extend the five-sprint schedule into April or retain January to March and shorten or combine sprints. The sequence below preserves the proposed five-sprint structure pending that decision.

| Sprint | Focus | Outputs and decision gate |
| --- | --- | --- |
| 1 | Practitioner interviews, discovery and initial planning | Agreed user problem, primary task and dataset; initial evidence map; responsibilities, budget and access checks. Gate: a feasible, authorised study. |
| 2 | Literature review, benchmark design and agentic prototype | Sourced review table, baseline implementation, frozen evaluation protocol, initial coordinated workflow and meta-statistical review skills, and modeller-support assessment rubric. Gate: data, model rights and evaluation design are adequate to proceed. |
| 3 | Benchmarking and agentic system evaluation | Reproducible model comparison, evaluated agentic modelling prototype and documented limitations. Gate: evidence is sufficient to support the demo narrative; freeze the experimental scope. |
| 4 | Demonstrator and technical presentation | Repeatable demo, integration notes, draft report and technical deck. Gate: findings are traceable and integration claims match what works. |
| 5 | Consolidation and executive pitch | Reviewed artefacts, final presentations, proposed accelerator and handover. Gate: a clear proceed, revise or stop recommendation with pilot prerequisites. |

At each sprint review, show working artefacts, record findings and uncertainties, update the risk log and agree the next sprint's scope with the supervisors and practice sponsor.

## Decisions to confirm at kick-off

- Exact dates, student availability, team size and division of responsibilities.
- Avanade practitioner and modeller contacts, academic supervisor and practice sponsor; review and sign-off arrangements.
- Primary security task, dataset permissions and any institutional ethics or data-protection review.
- Compute resources, Azure/Fabric access, approved AI services and spending limits.
- Agreed false-alert budget, agentic system roles and tools, modeller-support scoring rubric and minimum evidence needed to shape an accelerator offering or recommend a follow-on pilot.