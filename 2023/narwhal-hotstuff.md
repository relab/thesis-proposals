# Implementation of the Narwhal Mempool

## Administrative

- Supervisor: Hanish Gogada, Hein Meling, Leander Jehl

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
In this project, the goal is to implement a mempool library based on the Narwhal mempool protocol, using our existing frameworks.

Clients submit their transactions to the mempool through validators and mempool nodes store these transactions reliably.
Participating nodes pick a part of transactions, dessiminate and commit them using a consensus protocol.
Narwhal proposed a improved mempool protocol to reliably distribute the transactions to the replicas apart from storing it.
With this kind of mempool, replicas don't have to dessiminate the transactions instead use small references to conduct consensus.
This improves the performance of the consensus protocol.
We aim to implement this mempool in our hotstuff framework to compare the benefits of the new design.

## Tasks

- Read Narwhal[1], HotStuff[2], BullShark[3] papers.
- Become familiar with [4] and [5] for the Go implementation of HotStuff and Gorums; see also [4] and [5] for additional reading material.
- Design and implement the Narwhal mempool within the existing framework.
- Evaluate the benefits of Narwhal mempool with different configurations.
- Analyze and verify the claims of the Narwhal-Hotstuff protocol.

## Reading materials

[1] [Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus](https://arxiv.org/pdf/2105.11827.pdf)
[2] [Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness.](https://dl.acm.org/doi/pdf/10.1145/3293611.3331591)
[3] [Bullshark: DAG BFT Protocols Made Practical](https://arxiv.org/abs/2201.05677)
[4] [relab/hotstuff](https://github.com/relab/hotstuff)
[5] [relab/gorums](https://github.com/relab/gorums)
