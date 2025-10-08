# AI-based Log Analyzer for HotStuff

## Administrative

- Supervisors: Hein Meling and Leander Jehl

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

The Relab research group has implemented a modular and extensible [hotstuff framework][3] to design, implement, and analyze BFT protocols.
Currently, the framework supports several variants of the [HotStuff protocol][4], such as Chained HotStuff, Fast HotStuff, and Simple HotStuff.
We have also developed a test suite based on the [Twins approach][5].
Along with the test suite, we have developed a deployment tool to test the implementation on various configurations.

## Project Description

This project investigates AI-driven methods for analyzing HotStuff BFT protocol logs to recover protocol behavior, diagnose faults, and compare runs—even when logs are semi-structured, inconsistent across versions, or partially missing.
Rather than prescribing strict logging schemas and parsers, the study explores whether modern language models (LLMs) and complementary machine learning techniques can induce structure from noisy text, infer causal chains, and generate faithful explanations of observed behavior.

The research outcome should be a methodology and evidence for when and how AI can produce a robust and flexible log analysis pipeline that generalizes across HotStuff variants, configurations, and evolving logging styles.
Where helpful, a minimal proof-of-concept tool may be produced to demonstrate the approach, but the emphasis is on research questions, model design choices, and rigorous evaluation rather than on building a feature-complete product.

### Objectives

1. Research-oriented literature review
   - Survey AI for log mining (LLM-based extraction, anomaly detection, event classification), causal inference from logs, and analyses of BFT/SMR telemetry.
   - Identify gaps in handling un/semistructured logs, log drift, and cross-run comparisons.

2. Research questions (RQs)
   - RQ1: Structure induction — Can LLMs or lightweight fine-tuned models infer event types and fields (e.g., proposal, vote, QC, height, replica ID) from semi-structured or noisy HotStuff logs without a fixed schema? What few-shot prompts or constrained decoding improve precision/recall?
   - RQ2: Causal reconstruction — Can AI reliably reconstruct causal chains (e.g., proposal→vote→QC→commit) and timeline alignment across replicas to recover the 3-chain commit rule under clock skew and partial logs?
   - RQ3: Robustness to log drift — How well do AI methods generalize across protocol variants (Chained/Fast/Simple), code releases, and logging style changes (renamed fields, reordered tokens, added noise, missing lines)?
   - RQ4: Diffing and summarization — Can embeddings and LLM-based summarization produce faithful cross-run diffs and natural-language explanations of regressions, timeouts, or view changes? How to measure faithfulness vs. human-verified ground truth?
   - RQ5: Hybrid analysis — What is the best division of labor between lightweight rules (timestamps, replica IDs, known invariants) and AI components (schema induction, gap filling)? Does a hybrid approach outperform rule-only and AI-only baselines?
   - RQ6: Efficiency and cost — What are the latency and cost trade-offs of prompt-based vs. fine-tuned models for continuous integration (CI) workflows? Can we cache, batch, or distill models to meet CI time budgets?

3. Study design and evaluation
   - Data: Construct a corpus from the HotStuff framework and Twins-based tests, covering diverse configurations, failures, and protocol variants. Where possible, derive ground truth (e.g., committed heights, leader sequence, vote counts) from the test harness or instrumentation.
   - Baselines: Regex/state-machine parsers and schema-dependent tools that assume strictly structured logs.
   - Methods: Few-shot LLM extraction to a JSON event schema; constrained decoding or tool-calling to ensure type correctness; embedding-based clustering for event templates; optional light fine-tuning or adapters if justified.
   - Metrics: Event extraction F1; sequence/causal reconstruction accuracy (edit distance to ground-truth traces); anomaly/diff detection AUROC; faithfulness judged vs. protocol-derived facts; robustness under controlled perturbations (noise, dropped lines, renamed fields); runtime and token cost.

4. Expected outcomes
   - A validated methodology and reference implementation sufficient to reproduce experiments.
   - An ablation showing where AI helps most (e.g., schema induction, gap filling, summarization) and when rules suffice.
   - Recommendations for logging practices that maximize AI effectiveness without enforcing rigid schemas.

[3]: https://github.com/relab/hotstuff
[4]: https://arxiv.org/abs/1803.05069
[5]: https://malkhi.com/posts/2020/04/making-BFT-systems-robust/
