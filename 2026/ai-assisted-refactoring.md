# Bachelor: AI assisted refactoring

## Administrative

- Supervisor: Leander Jehl
- Group Composition: 1-3 students (the scope can be adjusted based to the number of students)
- Bachelor thesis

## Prerequisites

- Proficiency or strong willingness to learn the Go programming language
- Proficiency in use of AI tools (e.g., ChatGPT, GitHub Copilot)
- Willingness to learn about Distributed Systems

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

The goal of this project is to use AI tools to find potential for clarification, and code improvement in the project.
You should systematically submit the existing code for review by AI, filter and sort the resulting recommendations and submit pull requests for useful recommendations.

While we hope to do real improvements to the code a partial goal for this project is also to better understand the capabilities and proposal that can be received from the AI.

### Steps in the project

1. **Exploration**: Explore the capabilities and usefulness of AI review on individual parts of the code. Also explore related work on the topic.

2. **Workflow design**: Design a workflow to systematically submit large parts of the codebase for AI review and collect results.

3. **Review, filtering and application**: Manually filter and AI suggestions, and submit suitable suggestions for peer review.
This step may also include categorization of results for the sake of analysis.

4. **Analysis**: Analyze and evaluate process and results. 


[3]: https://github.com/relab/hotstuff
[4]: https://arxiv.org/abs/1803.05069
[5]: https://malkhi.com/posts/2020/04/making-BFT-systems-robust/
