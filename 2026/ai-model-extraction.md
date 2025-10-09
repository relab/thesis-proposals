# AI for model extraction

## Administrative

- Supervisor: Leander Jehl and Hein Meling
- Master thesis

## Prerequisites

- DAT530 Discrete simulation is recommended
- DAT520 Distributed systems is recommended
- Interest in algorithms and implementation correctness is a plus
- Willingness to learn about formal tools
- Proficiency in use of AI tools (e.g., ChatGPT, GitHub Copilot)

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Inaccuracies, misleading content, or design and stylistic similarities that indicate significant reliance on AI without critical review may negatively affect the grade.
Briefly document significant AI assistance (usage log and citations) to make provenance clear.

## Background and Motivation

Complex software systems, and especially distributed systems running on multiple nodes are known for subtle bugs and vulnerabilities.
Abstract or formal models of software systems are a useful tool to discover or avoid bugs in complex systems as shown e.g. through the use of formal methods as AWS [AWS](https://assets.amazon.science/67/f9/92733d574c11ba1a11bd08bfb8ae/how-amazon-web-services-uses-formal-methods.pdf).
However, the formulation of an abstract model, especially, when working and maintaining existing and evolved systems, rather than during design poses significant challenges, both in understanding the models and relating models to real code.



## Project Description

[Recent](https://zfhuang99.github.io/github%20copilot/formal%20verification/tla+/2025/05/24/ai-revolution-in-distributed-systems.html#fn:disclaimer) [reports](https://zfhuang99.github.io/tla+/pluscal/chatgpt/2023/09/24/TLA-made-simple-with-chatgpt.html) suggest that AI may be of significant help when creating models.

The goal for this project is to investigate the capabilities of AI to generate abstract models from complex code. 
Towards this goal, you should perform a case study where you try to create models from an existing code project.
The idea is to document help received from AI and to develop suitable strategies and prompts.

The initial idea is to use a component (the synchronizer) of the [Golang HotStuff implementation](https://github.com/relab/hotstuff) maintained by the Relab research group as code example and to create models in [TLA+](https://www.learntla.com/index.html#).
However, the use of a different software source or a different modeling tool may be discussed. 
For example Petri-Nets may be a suitable alternative.

### Objectives

1. **Familiarize with formal tools**: While there exists a range of resources from tutorials to video lectures, formal tools differ significantly from existing programming tool and require some learning effort.

2. **Planning on AI strategy documentation**: Plan how you will document AI usage during the process of the development of a formal model and to document human vs. AI contribution.

3. **Modelling**: Develop abstract models with the help of AI. 

4. **Analysis**: Evaluate and analyze the documented AI usage.

