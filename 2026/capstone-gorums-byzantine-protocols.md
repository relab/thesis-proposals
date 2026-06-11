# Capstone Project Family: Byzantine Protocols using Gorums

## Overview

These 10 ECTS capstone projects explore how Byzantine fault-tolerant protocols can be implemented using [Gorums][1], a UiS framework for group-RPCs and quorum-calls.
Each student chooses one project option and implements a focused protocol component or small protocol variant in Go.

The four project options are:

- [Clean HotStuff Implementation using Gorums](capstone-hotstuff-gorums.md)
- [Byzantine Reliable Broadcast using Gorums](capstone-byz-reliable-broadcast-gorums.md)
- [DAG-based Byzantine Protocols using Gorums](capstone-dag-bft-gorums.md)
- [Tree-based Byzantine Protocols using Gorums](capstone-tree-bft-gorums.md)

The projects have a shared theme: use one concrete Byzantine protocol to evaluate what Gorums supports well, where additional mechanisms are needed, and which improvements would make Gorums better for distributed protocol implementation.

## Prerequisites

- DAT520 Distributed Systems is recommended
- Good Go programming skills
- Interest in distributed systems, networking, and software design
- Willingness to use AI tools critically, for example ChatGPT or GitHub Copilot

## AI Tools

AI tools may be used during the project.
You remain responsible for the correctness and quality of the code and report.
Verify AI-generated code and claims with tests, measurements, and citations.
Document significant AI assistance briefly, for example in a usage log.

## Scope for a 10 ECTS Capstone

The project is intentionally smaller than a master's thesis.
A good result is a clean prototype with tests, a small evaluation, and a clear discussion of limitations.
The project can be organized in stages:

1. **Understand and scope**: read the main protocol material and define a minimal baseline.
2. **Build the core**: implement the smallest useful version of the protocol or component.
3. **Test faults**: add tests for normal behavior and a few relevant faulty cases.
4. **Measure**: run a compact benchmark or comparison.
5. **Reflect**: document what worked well with Gorums and what was difficult.

Optional extensions are only for projects that progress quickly.

## Typical Questions

Each project option specializes these questions:

- How naturally does the selected protocol fit Gorums quorum-calls and group communication?
- Which parts need extra mechanisms such as timers, streams, callbacks, routing, storage, or an event loop?
- What Gorums limitations become visible during implementation?
- What are the basic latency, throughput, bandwidth, CPU, memory, or message-count costs?
- Which concrete Gorums improvements are suggested by the experience?

## Possible Master's Thesis Continuation

A capstone can become the first step toward a master's thesis.
The capstone identifies a promising direction; the thesis can then go deeper.
Examples include:

- Extending the prototype into a more complete protocol implementation.
- Comparing several protocol variants under the same experimental framework.
- Designing new Gorums abstractions for BFT protocols, such as event loops, server-side quorum logic, streams, or routed quorum-calls.
- Studying robustness under Byzantine faults, delays, reconfiguration, or adversarial scheduling.
- Integrating the component into a larger BFT stack or application.

## Shared Reading Materials

- [Gorums paper][1]
- [Gorums source code][2]
- [Integrate Multiparty Support in Gorums using Interceptors][3]
- [HotStuff: BFT Consensus in the Lens of Blockchain][4]
- [Relab HotStuff framework][5]

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://github.com/relab/gorums
[3]: gorums-multiparty.md
[4]: https://arxiv.org/abs/1803.05069
[5]: https://github.com/relab/hotstuff
