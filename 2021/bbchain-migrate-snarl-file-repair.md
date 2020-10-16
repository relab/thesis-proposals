# Evaluate Snarl File Repair Component in Distributed Storage Systems

## Administrative

- Supervisor: Hein Meling and Racin Nygaard

## Prerequisites
- DAT200 Algorithms and Data Structures
- DAT520 Distributed Systems
- Proficient in the Go programming language

## Project Description

A large number of Distributed Storage Systems use a hierarchical data structure, such as the Merkle Tree, for both the transport and persistence layer.
Protecting this data structures with redundancy schemes is challenging as we can not modify the Merkle Tree in any way, without changing the root hash. Including adding, removing, editing, re-arranging both entire blocks and single bits.

Snarl is a novel component developed at the University of Stavanger that can be used by end-users to protect their data stored in Distributed Storage Systems, without requiring changes to the underlying storage system.
Currently Snarl has been evaluated on top of the [Swarm network](https://swarm.ethereum.org/), however the design of Snarl is agnostic to the properties of the underlying storage system.

The main task of this project will be to implement and evaluate Snarl on multiple different Distributed Storage Systems.
Evaluations will be carried out on the BBChain cluster with approximately 1000 peers.
The evaluations should consider metrics such as storage- and lookup-overhead.

This research is highly relevant, so successful implementations might see real-life adoptions.

## Tasks / Milestones

- Study the data structures of distributed storage systems
- Implement Snarl on a selection of distributed storage systems, using the existing implementation as reference.
- Evaluate the implementations on the BBChain cluster
- Compare the evaluation to the existing implementation
- Report on findings and lessons learned from the implementations

## Background on Distributed Storage Systems

A few videos to get an overview of the technology
- [Etherem Swarm](https://www.youtube.com/watch?v=VgTZV471WFM)
- [Filecoin](https://www.youtube.com/watch?v=P28aNAdZDi4)

## Reading Material

- [Ethereum Swarm Doc](https://swarm-guide.readthedocs.io/en/latest/introduction.html)
- [Etherum Swarm](https://swarm.ethereum.org/)
- [Etherum Swarm Bee](https://github.com/ethersphere/bee)
- [Filecoin](https://filecoin.io/)
- [Alpha Entanglement Codes](https://arxiv.org/abs/1810.02974)
- [DAT](https://dat.foundation/)
- [StorJ](https://storj.io/)
