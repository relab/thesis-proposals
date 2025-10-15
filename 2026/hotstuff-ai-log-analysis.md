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

Besides completely automated analysis it may also be relevant to analyze how AI can support individual steps in log analysis.
This may include grouping of log statements into larger logical units, labeling those units and highlighting causal and temporal dependencies between units.
Another related question is how AI based log analysis can profit from access to code files.

### Objectives

1. **Review research** on AI-assisted log analysis based on system logs, in particular for distributed systems.

2. **Plan AI usage and documentation**: Define how to document prompts, context (logs, code, AGENTS.md etc.), agent roles, provenance (human vs. AI), and evaluation criteria.

3. **Develop a log analysis pipeline for HotStuff logs**: May include these and other steps:
   - Reduction phase to limit context: summarize key events from raw logs.
   - Prepare plan (AGENTS.md)
   - Support high-value queries (what/where/why/causality/consistency/regression/comparison) against reduced logs.

4. **Evaluate** the approach on real HotStuff/Twins logs, measuring accuracy, robustness to log drift, and usefulness for debugging and regression detection.

<!-- What types of questions are relevant?
Can you prepare a list of relevant questions?

Can we answer questions like:

- Where does event X happen?
- Why did replica Y timeout?
- Why did the leader fail?
- Does event X always lead to event Y?
- Does a timeout always lead to a view change?
- In what context did event Z occur?
- Which events causally preceded it?
- Which events are relevant that led to X?
- Is this a regression compared to run Y?
- Is this the context in all runs where X occurs? -->

[3]: https://github.com/relab/hotstuff
[4]: https://arxiv.org/abs/1803.05069
[5]: https://malkhi.com/posts/2020/04/making-BFT-systems-robust/
