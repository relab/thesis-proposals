# Capstone: DAG-based Byzantine Protocols using Gorums

- Supervisor: Hein Meling
- Fall capstone project, 10 ECTS
- Part of the [Byzantine Protocols using Gorums](capstone-gorums-byzantine-protocols.md) project family

## Motivation

Recent Byzantine fault-tolerant protocols often use a directed acyclic graph (DAG) to separate transaction dissemination from ordering.
Protocols such as Narwhal, Tusk, DAG-Rider, and Bullshark build certified vertices and then derive an order from the DAG.

DAG-based protocols are interesting for Gorums because they combine repeated all-to-all communication, quorum certificates, causal dependencies, storage, and event-driven processing.
For a 10 ECTS capstone, the focus is the DAG construction layer rather than a full consensus protocol.

## Goal

Implement a small Narwhal-style DAG dissemination prototype in Go using Gorums.
The prototype creates certified vertices, tracks parent links between rounds, handles missing or duplicate vertices, and exposes enough structure for testing and measurement.

## Suggested Stages

1. Read the main Narwhal/Tusk material and selected DAG-BFT background.
2. Define the DAG data model: vertices, rounds, batches, parent links, certificates, and storage.
3. Implement vertex dissemination and certificate construction.
4. Add dependency checks, duplicate handling, and basic Byzantine equivocation tests.
5. Test several replicas over multiple rounds.
6. Run a small benchmark for throughput, latency, bandwidth, and storage overhead.
7. Document which parts fit Gorums and which parts need streams, storage, or event-loop support.

Optional extensions include a simple Bullshark-style ordering rule or comparison with a direct gRPC all-to-all baseline.

## Questions to Explore

- How naturally can a Narwhal-style DAG layer be expressed using Gorums?
- Which steps are best represented as quorum-calls, streams, background tasks, or event-loop events?
- What support is needed for repeated all-to-all dissemination and dependency tracking?
- How does the prototype behave with delayed, missing, duplicate, or conflicting vertices?
- What are the basic throughput, latency, bandwidth, and storage costs?

## Master's Thesis Continuation

This capstone can lead to a thesis on high-throughput BFT protocols in Gorums.
Possible directions include extending the DAG layer with ordering, comparing DAG-based and leader-based protocols, designing Gorums support for continuous dissemination, or studying storage and garbage collection for long-running DAGs.
See also the umbrella [proposal](capstone-gorums-byzantine-protocols.md).

## Reading Materials

- [Gorums paper][1]
- [Gorums source code][2]
- [Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus][3]
- [All You Need is DAG][4]
- [Bullshark: DAG BFT Protocols Made Practical][5]
- [Relab HotStuff framework][6]

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://github.com/relab/gorums
[3]: https://arxiv.org/abs/2105.11827
[4]: https://arxiv.org/abs/2102.08325
[5]: https://arxiv.org/abs/2201.05677
[6]: https://github.com/relab/hotstuff
