# AI-based Log Analyzer for HotStuff

## Administrative

- Supervisors: Hein Meling and Leander Jehl
- Master thesis

## Prerequisites

- DAT515 Cloud Computing Technologies is recommended
- DAT520 Distributed systems is recommended
- Willingness to learn about distributed systems
- Proficient in the Go programming language
- Proficiency in use of AI tools (e.g., ChatGPT, GitHub Copilot)

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Inaccuracies, misleading content, or design and stylistic similarities that indicate significant reliance on AI without critical review may negatively affect the grade.
Briefly document significant AI assistance (usage log and citations) to make provenance clear.

## Background and Motivation

Byzantine fault-tolerant (BFT) protocols are used to replicate arbitrary applications on multiple servers, called replicas, while tolerating arbitrary failures or even attacks from a subset of the replicas.
HotStuff is a popular BFT state machine replication protocol designed for permissioned blockchains.

The Relab research group has implemented a modular and extensible [HotStuff framework][3] to design, implement, and analyze BFT protocols.
Currently, the framework supports several variants of the [HotStuff protocol][4], such as Chained HotStuff, Fast HotStuff, and Simple HotStuff.
We have also developed a test suite based on the [Twins approach][5].
Along with the test suite, we have developed a deployment tool to test the implementation on various configurations.

The HotStuff framework is actively maintained.
When implementing new features, fixing bugs, or doing code reorganization for improved clarity, the analysis of log files from runs on both localhost and remote machines is a crucial tool.
However, such runs may show behavior and trigger bugs which are hard to reproduce in a more deterministic setting like unit tests.

One challenge, when analyzing logs, is that log statements may vary in their expressiveness and log statements attesting similar steps may be formulated differently in different code branches.
Additionally, log files typically contain a vast amount of information, making it hard to extract relevant differences.

## Project Description

This project investigates AI-driven methods for analyzing HotStuff BFT protocol logs to recover protocol behavior, diagnose faults, and compare runs—even when logs are semi-structured, inconsistent across versions, or partially missing.
Rather than prescribing strict logging schemas and parsers, the study explores whether modern language models (LLMs) and complementary machine learning techniques can induce structure from noisy text, infer causal chains, and generate faithful explanations of observed behavior.

The research outcome should be a methodology and evidence for when and how AI can produce a robust and flexible log analysis pipeline that generalizes across diverging branches, configurations, and evolving logging styles.
While a proof-of-concept tool should be produced to demonstrate the approach, the emphasis is on research questions, model design choices, and rigorous evaluation rather than on building a feature-complete product.

<!-- Usikker om denne skal være her eller som del av research questions. -->
Besides completely automated analysis it may also be relevant to analyze how AI can support individual steps in log analysis.
This may include grouping of log statements into larger logical units, labeling those units and highlighting causal and temporal dependencies between units.
Another related question is how AI based log analysis can profit from access to code files.

### Objectives

1. Research-oriented Literature Review
   - Survey AI for log mining (LLM-based extraction, anomaly detection, event classification), causal inference from logs, and analyses of BFT/SMR telemetry.
   - Identify gaps in handling unstructured/semi-structured logs, log drift, and cross-run comparisons.

2. Research Questions (RQs)
   - RQ1: Structure induction — Can LLMs or fine-tuned models infer event types and fields (e.g., proposal, vote, QC, height, replica ID) from semi-structured HotStuff logs without a fixed schema?
   - RQ2: Causal reconstruction — Can AI reliably reconstruct causal chains (e.g., proposal→vote→QC→commit) and timeline alignment across replicas?
   - RQ3: Robustness to changes — How robust is AI methods to protocol changes and logging style changes (renamed fields, reordered messages, missing fields/messages)?
   - RQ4: Diffing and summarization — Can LLM-based summarization produce accurate cross-run diffs?
   - RQ5: Explanations — Can AI provide natural-language explanations of regressions, timeouts, or view changes?

3. Study Design and Evaluation
   - Data: Construct a corpus from the HotStuff framework and Twins-based tests, covering diverse configurations, failures, and protocol variants. Where possible, derive ground truth (e.g., committed heights, leader sequence, vote counts) from the test harness or instrumentation.
   - Baselines: Regex/state-machine parsers and schema-dependent tools that assume strictly structured logs.
   - Methods: Few-shot LLM extraction to a JSON event schema; constrained decoding or tool-calling to ensure type correctness; embedding-based clustering for event templates; optional light fine-tuning or adapters if justified.
   - Metrics: Event extraction F1; sequence/causal reconstruction accuracy (edit distance to ground-truth traces); anomaly/diff detection AUROC; faithfulness judged vs. protocol-derived facts; robustness under controlled perturbations (noise, dropped lines, renamed fields); runtime and token cost.

4. Expected Outcomes
   - A validated methodology and reference implementation sufficient to reproduce experiments.
   - An ablation showing where AI helps most (e.g., schema induction, gap filling, summarization) and when rules suffice.
   - Recommendations for logging practices that maximize AI effectiveness without enforcing rigid schemas.

[3]: https://github.com/relab/hotstuff
[4]: https://arxiv.org/abs/1803.05069
[5]: https://malkhi.com/posts/2020/04/making-BFT-systems-robust/
