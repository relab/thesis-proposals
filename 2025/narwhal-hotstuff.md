# Implementation of the Narwhal Mempool

## Administrative

- Supervisors: Hanish Gogada, Hein Meling, Leander Jehl
- Contact: <hein.meling@uis.no>

## Prerequisites

- DAT520 Distributed systems
- Proficient in the Go programming language

## The Relab Research Group

The Relab research group at UiS is working on the design and implementation of distributed systems.
The group has developed several Go-based frameworks to simplify developing, validating, and evaluating new Byzantine fault tolerant protocols, a key ingredient in blockchains.
Our frameworks are being used by other research groups around the world.

## Project Description

Byzantine fault tolerant (BFT) protocols are often used to implement blockchains, but their lack of scalability is a challenge.
One approach to improve the scalability of BFT protocols is to separate the dissemination of transactions from the ordering of the transactions.
In this project, the goal is to implement a mempool library based on the [Narwhal][1] mempool protocol, using our existing frameworks.

### What is a mempool?

For applications that need to reliably disseminate transactions to a set of validator replicas, and order those transactions, a mempool can be used for the dissemination phase.
For such applications, clients submit their transactions to the mempool, which stores them reliably.
The validator replicas pick a subset of the transactions from the mempool, orders and commits the transactions using a consensus protocol.
Hence, a mempool is a component that stores the transactions until they are committed.
The mempool nodes are typically co-located with validators.

### Narwhal's mempool

[Narwhal][1] proposed an improved mempool protocol to reliably distribute the transactions to the replicas apart from storing it.
With this kind of mempool, replicas do not have to disseminate the transactions, and can instead use compact references to transactions in the mempool, for conducting consensus.
This improves the performance of the consensus protocol.
We aim to implement this mempool in our [hotstuff][4] framework to compare the benefits of the new design.

## Tasks

- Read [Narwhal][1], [HotStuff][2], [BullShark][3] papers
- Become familiar with [relab/hotstuff][4] and [relab/gorums][5] for the Go implementation of HotStuff and Gorums
- Design and implement the Narwhal mempool within the existing framework
- Evaluate the benefits of Narwhal mempool with different configurations
- Analyze and verify the claims of the Narwhal-Hotstuff protocol

## Reading materials

- [Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus][1]
- [Hotstuff: BFT consensus with linearity and responsiveness.][2]
- [Bullshark: DAG BFT Protocols Made Practical][3]
- [relab/hotstuff][4]
- [relab/gorums][5]

[1]: https://arxiv.org/pdf/2105.11827.pdf
[2]: https://dl.acm.org/doi/pdf/10.1145/3293611.3331591
[3]: https://arxiv.org/abs/2201.05677
[4]: https://github.com/relab/hotstuff
[5]: https://github.com/relab/gorums
