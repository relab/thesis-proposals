# Capstone: Tree-based Byzantine Protocols using Gorums

- Supervisor: Hein Meling
- Fall capstone project, 10 ECTS
- Part of the [Byzantine Protocols using Gorums](capstone-gorums-byzantine-protocols.md) project family

## Motivation

Leader-based BFT protocols often ask one leader to broadcast proposals and collect votes from all replicas.
This can become a bottleneck as the number of replicas grows.
Tree-based communication reduces leader load by forwarding messages and aggregating votes through a tree overlay.

Tree overlays also introduce new problems.
A slow or faulty internal node can delay an entire subtree, and the system may need recovery or reconfiguration.
This project studies whether Gorums can express routed communication and server-side aggregation in a clean way.

## Goal

Implement a small tree-based BFT communication prototype in Go using Gorums.
The baseline is proposal dissemination and vote aggregation over a tree, inspired by Kauri-style aggregation for HotStuff-like protocols.
A standalone benchmark comparing tree-based and star-based communication is enough for the capstone.

## Suggested Stages

1. Read background on HotStuff, tree-based aggregation, and Gorums.
2. Define the tree abstraction: parent/child relationships, routing metadata, aggregation thresholds, and timeouts.
3. Implement proposal forwarding and vote aggregation.
4. Add tests for aggregation correctness, missing children, duplicate votes, and faulty internal nodes.
5. Run experiments with a few tree shapes and replica counts.
6. Compare against ordinary star-based broadcast and vote collection.
7. Document what Gorums supports well and what requires routing, aggregation, reconfiguration, or event-loop mechanisms.

Optional extensions include multiple trees, redundant parents, simple tree reconfiguration, or integration with a minimal HotStuff prototype.

## Questions to Explore

- How naturally can tree-based dissemination and vote aggregation be expressed using Gorums?
- What support is needed for routed communication through intermediate replicas?
- Does an event-loop structure help with failures, timeouts, and reconfiguration?
- How robust is aggregation under slow, crashed, or Byzantine internal nodes?
- How do tree-based and star-based communication compare in small experiments?

## Master's Thesis Continuation

This capstone can lead to a thesis on scalable BFT communication in Gorums.
Possible directions include comparing several aggregation topologies, designing routed quorum-calls, studying robustness under faulty internal nodes, or integrating tree aggregation into a complete HotStuff implementation.
See also the umbrella [proposal](capstone-gorums-byzantine-protocols.md).

## Reading Materials

- [Gorums paper][1]
- [Gorums source code][2]
- [HotStuff: BFT Consensus in the Lens of Blockchain][3]
- [The Quest for Scaling BFT Consensus through Tree-Based Vote Aggregation][4]
- [SoK: Scalability Techniques for BFT Consensus][5]
- [Relab HotStuff framework][6]

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://github.com/relab/gorums
[3]: https://arxiv.org/abs/1803.05069
[4]: https://arxiv.org/abs/2103.12112
[5]: https://arxiv.org/abs/2303.11045
[6]: https://github.com/relab/hotstuff
