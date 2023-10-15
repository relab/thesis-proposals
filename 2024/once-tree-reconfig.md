# Reconfiguration of OnceTree

## Administrative

- Supervisor: Hein Meling
- Co-supervisor: Conor Power (University of California, Berkeley)
- Prof Meling is currently on sabbatical, but will be available for physical meetings from November 27, 2023.
- Before that I will be happy to answer questions by email, or set up a Zoom call to discuss the project with prospective students.
- Contact: <hein.meling@uis.no>

## Prerequisites

- DAT520 Distributed systems
- Proficient in the Go programming language

## Background

The following is copied from the [OnceTree paper's abstract][1], which is under submission and cannot yet be shared publicly.
(I will share the paper with the student working on this project.)

A critical challenge in modern geo-distributed systems is to allow multiple readers and writers to share replicated state in a coordination-free fashion.
Data structures like CRDTs offer solutions for types with naturally idempotent operations, such as sets.
But many applications rely on non-idempotent types, including fundamental types like counters and multisets.
For these types, additional coordination-free mechanisms are needed to enforce idempotence.
Prior schemes require space linear in the number of replicas, which is impractical for widespread use cases like social networks and recommender systems.
In this paper, we present OnceTree, a replication protocol that enables coordination-free idempotence enforcement in constant memory.
OnceTree combines semi-lattice merges with distributed aggregation trees and controlled network flooding to enable the replication of any data type with an associative and commutative aggregation function.
We evaluate OnceTree against existing replicated data types on cloud infrastructure and validate scalability trends for memory usage and propagation latency.

## Project Description

In this project you will implement and evaluate the OnceTree CRDT algorithm using our [Gorums][2] framework ([Gorums code][3]).
The OnceTree paper briefly discusses a few reconfiguration strategies, but does not provide a detailed discussion or evaluation.

The main goal in this project is therefore to implement and evaluate the proposed reconfiguration mechanisms for OnceTree.
The proposed mechanisms should be relatively easy to implement using Gorums, since it already supports easy-to-use configuration objects, and allows RPC-style communication with a defined number of replicas in the configuration.
We also have a draft PR for supporting Tree-based configurations.
However, we may also draw on Hanish's recent experience with implementing tree-structures in [relab/hotstuff][5].

One proposed reconfiguration mechanism in particular, rely on a hierarchical composition of overlapping groups.
This requires solving the group membership problem, which is equivalent to the consensus problem.
However, it is likely that a more light-weight group membership can be used, since the replicas communication is CRDT-based.

It is an open question whether or not OnceTree's CRDT-based design can be expanded to support reconfiguration in a coordination-free fashion.
Hence, this project may also explore this potential research direction.
For example, it may be possible to use a CRDT-like reconfiguration strategy based on lattice agreement, such as [SmartMerge][4], developed by Leander Jehl in his PhD thesis.

## Tasks

- Review literature on reconfiguration of trees
  - Write background section discussing the state of the art
- Review Gorums and HotStuff code for the tree-structures
- Implement OnceTree's basic functionality in Gorums
  - The implementation should include suitable test cases to verify correctness
- Implement the reconfiguration algorithms in Gorums
  - Each algorithm must include suitable test cases to verify correctness
- Evaluate performance and test correctness properties
- Report on findings and lesson learned from the implementations

[1]: https://link.to.paper/once-tree
[2]: https://ieeexplore.ieee.org/document/7980198/
[3]: https://github.com/relab/gorums
[4]: https://link.springer.com/chapter/10.1007/978-3-662-48653-5_11
[5]: https://github.com/relab/hotstuff
