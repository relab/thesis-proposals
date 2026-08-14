# Guide to Writing a Master's Thesis Project Description

A project description is a short agreement between the student and supervisor about **what will be studied, why it matters, how it will be evaluated, and what can realistically be completed**. Aim for 2–4 pages unless your study program requires otherwise.

Use the [project description template](master-thesis-description-template.md) as a starting point.

## The Essential Questions

A good description answers:

1. **What is the problem?** Give only the background needed to understand it.
2. **What is missing?** Identify a limitation, uncertainty, or gap in existing work.
3. **What will the thesis contribute?** State what will be learned—not only what will be built.
4. **What are the research questions?** Prefer 2–4 focused, answerable questions.
5. **How will they be answered?** Describe the method, comparisons, and evidence.
6. **What is the scope?** Separate required work from optional extensions and non-goals.
7. **What will be delivered?** List the report and any code, data, tests, models, or documentation.

A useful summary sentence is:

> This thesis investigates **[problem or gap]** using **[method]** to determine **[expected knowledge or decision]**.

## From Project to Thesis

Implementation may be important, but effort alone does not make a master's thesis. The artifact should help produce knowledge—for example:

- a controlled comparison of alternatives;
- evidence about correctness, performance, robustness, or usability;
- a validated method, model, design, or abstraction;
- a reproducible experiment, dataset, benchmark, or case study.

A negative result can still be valuable. Do not assume the preferred solution will succeed.

## Research Questions and Evidence

Questions should follow from the gap and imply how they can be answered. Useful forms include:

- How does **X** affect **Y** under conditions **Z**?
- How does **A** compare with **B** using metric **M**?
- Which design satisfies requirements **R**, and what trade-offs does it introduce?
- How robust is method **M** to changes or faults **F**?

For each question, identify the method, evidence, and baseline:

| Question | Method | Evidence/metrics | Baseline |
| :--- | :--- | :--- | :--- |
| RQ1 | [Experiment, case study, proof, etc.] | [What is measured or observed] | [What it is compared with] |

Avoid undefined terms such as “better,” “efficient,” or “robust.” Say how they will be assessed.

## Scope and Evaluation

Define the **smallest complete thesis** that can answer the research questions. Put extra platforms, features, datasets, or experiments under optional work.

An evaluation should state:

- what is evaluated and compared;
- which data, workloads, cases, or fault scenarios are used;
- which correctness checks and metrics are used;
- how experiments or analyses can be reproduced;
- the main limitations or threats to validity.

“Evaluate the solution” is too vague. Name the baseline, conditions, and evidence.

## Final Check

Before approval, verify that:

- [ ] the problem and gap are clear and supported by references;
- [ ] the contribution says what will be learned;
- [ ] every research question has a method and evidence;
- [ ] the core scope is feasible without optional work;
- [ ] evaluation includes suitable baselines and success criteria;
- [ ] deliverables, important risks, and required resources are explicit;
- [ ] AI-generated claims and code will be verified, and significant AI use documented;
- [ ] the student and supervisor agree on the core scope.
