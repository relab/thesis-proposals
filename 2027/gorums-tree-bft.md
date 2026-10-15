# Master's Thesis: Tree-based BFT using Gorums

## Administrative

- Supervisor: Hein Meling
- Master's thesis

### Prerequisites

- DAT520 Distributed Systems or equivalent knowledge.
- Good Go programming skills and an interest in distributed protocols and networking.
- Willingness to reason carefully about safety, concurrency, and failure handling.

### AI Tools

AI tools may be used, but students remain responsible for the code, reasoning, measurements, and citations.
Verify generated code and claims, and briefly document significant AI assistance.

## Research Question

> How well do Gorums' communication abstractions support tree-based Byzantine fault-tolerant protocols, including reconfiguration of the communication tree?

The thesis will investigate whether tree dissemination, aggregation, and changes to the tree can be expressed naturally using Gorums, and where additional support may be needed.
Reproducing published results provides a basis for evaluating both protocol behavior and the suitability of the framework.

## Background and Motivation

Leader-centered Byzantine fault-tolerant (BFT) protocols can make proposal dissemination and vote collection a bottleneck.
[Kauri][4] distributes this work through a tree, reducing the communication load on the leader.
However, the benefits depend on network conditions and on the behavior of internal nodes, which relay messages for other replicas.
[OptiLog][5] uses a sensor–monitor architecture for measurement collection and logging to support measurement-driven role assignment.
OptiTree uses these mechanisms to adapt the communication tree to the network.

[Gorums][2] is a quorum-based communication framework for Go.
Tree-based protocols challenge its abstractions because communication involves intermediate nodes and aggregation rather than only direct requests and replies.
Changing the tree also raises questions about how communication structures are represented and how ongoing protocol instances are handled.
Relevant concerns in Gorums and its underlying gRPC communication include error handling, timeout management, context cancellation, and support for reconfiguration.
Here, tree reconfiguration means changing communication paths and roles, not changing consensus membership.

A Gorums-based implementation offers an opportunity to revisit these protocols and their experimental results with a focus on implementation rigor and reproducibility.
Wide-area network emulation using Kollaps can help investigate how their behavior depends on network conditions.


## Scope

The thesis will implement and evaluate a selected tree-based BFT protocol using Gorums, taking Kauri and the OptiLog/OptiTree work as starting points.
The specific protocol, reproduction target, and any extension will be agreed with the supervisor to form a coherent, manageable study.


The work should result in a well-tested implementation, reproducible experiments, and a critical assessment of the existing abstractions.
Proposed changes to Gorums should be motivated by limitations encountered in the implementation, rather than assumed necessary in advance.
The evaluation should relate the findings to the selected protocol's published results and explain the assumptions and limitations of the comparison.

## References

1. [Gorums paper][2], [source code][3], and [user guide][11].
2. [The Quest for Scaling BFT Consensus through Tree-Based Vote Aggregation (Kauri)][4].
3. [OptiLog: Assigning Roles in Byzantine Consensus][5] and [source code][6].
4. [HotStuff: BFT Consensus in the Lens of Blockchain][7] and the [Relab HotStuff framework][8].

[2]: https://ieeexplore.ieee.org/document/7980198
[3]: https://github.com/relab/gorums
[4]: https://arxiv.org/abs/2103.12112
[5]: https://arxiv.org/abs/2502.15428
[6]: https://github.com/relab/optilog
[7]: https://arxiv.org/abs/1803.05069
[8]: https://github.com/relab/hotstuff
[11]: https://github.com/relab/gorums/blob/master/doc/user-guide.md
