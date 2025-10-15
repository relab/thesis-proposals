# Integrate Multiparty Support in Gorums using Interceptors

## Administrative

- Supervisors: Hein Meling
- Master thesis

## Prerequisites

- DAT515 Cloud Computing Technologies is recommended
- DAT520 Distributed systems is recommended
- Have a strong interest in software design with a focus on distributed systems and networking
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

Gorums is a framework for group-RPCs (quorum-calls) developed at UiS.
A quorum-call allows a client to invoke a remote procedure on multiple servers and collect and combine the replies, resulting in a point-to-multipoint-to-point communication pattern.
Gorums relies on [gRPC](https://grpc.io/) to perform the individual remote procedure calls in a quorum-call.
Gorums is used in several research prototypes, including the [HotStuff BFT framework][5] and as a teaching tool the DAT520 Distributed Systems course at UiS.

While the "production" version of Gorums supports point-to-multipoint-to-point communication, we now have a prototype of multiparty, all-to-all communication implemented by [Aleksander Vedvik][9].
The prototype shows that Gorums can support protocols that send prepare and commit messages directly among participants in an all-to-all pattern.
Examples include classical Paxos learns and Byzantine Fault Tolerant (BFT) protocols.
See also the multiparty prototype pull request [PR #176](https://github.com/relab/gorums/pull/176).

## Project Description

This project will redesign the existing multiparty prototype to use [gRPC interceptors][3], which are a more standard way of extending gRPC functionality.
Interceptors are a well-known mechanism in gRPC to add functionality to RPC calls, both on the client and server side.
Using interceptors will make the multiparty functionality more modular and easier to maintain.
It will also make it easier to integrate with other gRPC-based systems.

While this project focuses on redesigning the multiparty support in Gorums, the ultimate goal is to enable the implementation of BFT protocols using Gorums.
As such, the project should also implement all-to-all Paxos and [PBFT][4] using multiparty communication.
These implementations will serve as case studies to evaluate the redesigned multiparty support and to compare with the existing prototype.
The project should also include comprehensive tests to ensure the correctness and reliability of the implementation.

While this project does not have a strong research component, it requires a **significant engineering effort**, a good understanding of distributed systems, and software engineering and design practices.
Contributions to general Gorums design discussions and improvements, and maintenance, such as those discussed on the [issue tracker][8] and in Asbjørn Salhus's [thesis on Gorums redesign][10] is also expected.

The goal is to produce a solid implementation of multiparty support in Gorums using gRPC interceptors that can serve as the foundation for a joint paper with Vedvik and others.

## Tasks

- Review background on [Gorums][1], [gRPC interceptors][3], [PBFT][4], [DepFast][2], all-to-all Paxos learns, and prior theses ([Mæland][11], [Vedvik][9], [Salhus][10]).
  - Write a background section summarizing the state of the art and requirements for multiparty/all-to-all RPC.
- Study the current [relab/gorums][8] codebase and the multiparty prototype (see [PR #176](https://github.com/relab/gorums/pull/176)) to identify gaps and reusable components.
- Design a multiparty architecture using gRPC interceptors.
  - Define client- and server-side interceptor responsibilities and the metadata/routing format.
  - Specify the public API and any code-generation hooks needed by applications.
- Implement the redesigned multiparty support in Gorums using interceptors.
- Implement case studies using the new multiparty support.
  - All-to-all Paxos learns.
  - PBFT (minimal end-to-end pipeline).
- Add comprehensive tests to ensure correctness and reliability.
  - Unit tests for interceptors, metadata handling, and routing logic.
  - Integration tests for Paxos and PBFT, including fault injection.
- Evaluate performance of the redesigned multiparty support.
  - Microbenchmarks and end-to-end benchmarks; compare against the existing prototype implementation.
- Document and disseminate results.
  - Developer docs, usage examples, and a short migration guide.
  - Participate in Gorums design discussions and maintenance (e.g., via the [issue tracker][8]).

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://www.usenix.org/conference/atc22/presentation/luo
[3]: https://grpc.io/docs/guides/interceptors/
[4]: http://pmg.csail.mit.edu/papers/osdi99.pdf
[5]: https://github.com/relab/hotstuff
[8]: https://github.com/relab/gorums
[9]: https://uis.brage.unit.no/uis-xmlui/handle/11250/3145172
[10]: https://uis.brage.unit.no/uis-xmlui/handle/11250/3214502
[11]: https://uis.brage.unit.no/uis-xmlui/handle/11250/2455424
