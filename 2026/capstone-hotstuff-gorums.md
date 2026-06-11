# Capstone: Clean HotStuff Implementation using Gorums

- Supervisor: Hein Meling
- Fall capstone project, 10 ECTS
- Part of the [Byzantine Protocols using Gorums](capstone-gorums-byzantine-protocols.md) project family

## Motivation

HotStuff is a Byzantine fault-tolerant state machine replication protocol used as a foundation for many permissioned blockchain systems.
It is leader-based, uses quorum certificates, and has a relatively clean protocol structure.
This makes it a good target for studying how well Gorums supports quorum-based BFT protocols.

Relab already has HotStuff-related code, but this project focuses on a small implementation from first principles using current Gorums ideas.
The goal is clarity, testability, and a useful evaluation of the programming model, not a production-ready consensus library.

## Goal

Implement a minimal Chained HotStuff prototype in Go using Gorums.
The prototype covers proposal, voting, quorum certificate construction, block commitment, and a simple timeout/view-change path.

## Suggested Stages

1. Read the HotStuff paper and relevant Gorums material.
2. Define a minimal protocol scope and data model: blocks, votes, quorum certificates, views, and replica roles.
3. Implement the normal-case protocol path.
4. Add simple timeout and view-change handling.
5. Test safety-related behavior with several replicas and selected faults.
6. Run a small benchmark and compare with a simple baseline or existing Relab code if feasible.
7. Document where Gorums fits naturally and where extra mechanisms are needed.

Optional extensions include pipelining improvements, alternative leader selection, a small key-value application, or Twins-style testing.

## Questions to Explore

- How naturally can Chained HotStuff be expressed using Gorums quorum-calls?
- Which events are best handled as quorum-calls, timers, asynchronous messages, or event-loop events?
- Does an event-loop structure make the implementation easier to test and reason about?
- What Gorums API or runtime limitations appear during the implementation?
- How does the prototype perform in a small experimental setup?

## Master's Thesis Continuation

This capstone can lead to a thesis on Gorums-based BFT consensus.
Possible directions include comparing HotStuff variants, building a Gorums-native event-loop runtime, studying view-change robustness, or integrating the prototype with a replicated application.
See also the umbrella [proposal](capstone-gorums-byzantine-protocols.md).

## Reading Materials

- [Gorums paper][1]
- [HotStuff: BFT Consensus in the Lens of Blockchain][2]
- [Relab HotStuff framework][3]
- [Gorums source code][4]
- [Making BFT Protocols Really Robust with Twins][5]

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://arxiv.org/abs/1803.05069
[3]: https://github.com/relab/hotstuff
[4]: https://github.com/relab/gorums
[5]: https://malkhi.com/posts/2020/04/making-BFT-systems-robust/
