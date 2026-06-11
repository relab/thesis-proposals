# Capstone: Byzantine Reliable Broadcast using Gorums

- Supervisor: Hein Meling
- Fall capstone project, 10 ECTS
- Part of the [Byzantine Protocols using Gorums](capstone-gorums-byzantine-protocols.md) project family

## Motivation

Byzantine reliable broadcast (BRB) lets a sender broadcast a message so that correct replicas agree on what is delivered, even when some replicas behave maliciously.
BRB is a basic building block in many Byzantine fault-tolerant protocols, including asynchronous and DAG-based systems.

Classic protocols such as Bracha's reliable broadcast use all-to-all communication and quorum thresholds for echo and ready messages.
This makes BRB small enough for a capstone project, while still exposing important challenges: duplicate messages, equivocation, server-side quorum detection, and event-driven protocol transitions.

## Goal

Implement a Bracha-style Byzantine reliable broadcast prototype in Go using Gorums.
The prototype supports multiple replicas, concurrent broadcast instances, duplicate handling, and a few Byzantine sender/receiver scenarios.

## Suggested Stages

1. Read the main BRB material and Gorums multiparty communication material.
2. Define the broadcast API and message identifiers.
3. Implement the send, echo, ready, and deliver logic.
4. Add duplicate detection and basic equivocation handling.
5. Test honest broadcasts, missing messages, duplicates, Byzantine sender equivocation, and concurrent broadcasts.
6. Run a small benchmark for latency, message count, and throughput.
7. Document where Gorums helps and where extra server-side event handling is needed.

Optional extensions include a scalable BRB variant, an erasure-coded variant, or comparison with a simple direct gRPC all-to-all implementation.

## Questions to Explore

- How naturally can BRB be implemented using Gorums quorum-calls and multiparty communication?
- Where is server-side quorum detection needed?
- Does an event-loop-oriented design simplify duplicate handling and concurrent instances?
- Which parts require mechanisms outside standard Gorums calls?
- What are the basic latency, throughput, and message-count costs?

## Master's Thesis Continuation

This capstone can lead to a thesis on Byzantine broadcast abstractions.
Possible directions include comparing BRB variants, designing Gorums support for server-side quorum logic, integrating BRB into a DAG-based protocol, or developing a reusable Byzantine broadcast test framework.
See also the umbrella [proposal](capstone-gorums-byzantine-protocols.md).

## Reading Materials

- [Gorums paper][1]
- [Gorums source code][2]
- [Integrate Multiparty Support in Gorums using Interceptors][3]
- [Scalable Byzantine Reliable Broadcast][4]
- [Reliable Broadcast in Practical Networks][5]
- [Byzantine Reliable Broadcast with Low Communication and Time Complexity][6]

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://github.com/relab/gorums
[3]: gorums-multiparty.md
[4]: https://arxiv.org/abs/1908.01738
[5]: https://arxiv.org/abs/2007.14990
[6]: https://arxiv.org/abs/2404.08070
