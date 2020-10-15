# Master Title: Implement the HotStuff Protocol used in Libra using Gorums

# Bachelor Title: Implement the Consensus Protocol used in Facebook's Libra Cryptocurrency using Gorums

## Supervisor: Hein Meling and Leander Jehl

## Prerequisites

- Distributed systems (DAT520)
- Go programming language.

## Project description

Gorums is a framework for group-RPCs (quorum-calls) developed at UiS. A quorum-call allows to invoke a remote procedure simultaneously on multiple hosts and collect and combine the replies. The current version of Gorums relies on gRPC to perform the individual remote procedure calls in a quorum-call.

A recent paper describes a really neat Byzantine tolerant replication protocol called HotStuff (from VMware research) that we believe matches well with the features and messaging pattern supported by Gorums. In this project, the goal is to implement HotStuff using Gorums, and to evaluate it. HotStuff is envisioned to be suitable for blockchain implementations, and in fact HotStuff is used by the Libra cryptocurrency promoted by Facebook.

## Milestones

- Learn to develop with Gorums
- Carefully read and analyze the HotStuff paper to understand how it can be implemented with Gorums.
- Implement HotStuff with Gorums.
- Evaluate the HotStuff implementation using microbenchmarks.
- Evaluate the implementation with system workloads, e.g. a key-value storage system, with different read-write ratios.
- Compare with the existing HotStuff implementation and other protocols. 

## Background

Gorums is a novel framework for building fault tolerant distributed systems. Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses. Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies. These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed. Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls. Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

## Reading material

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums source code](https://github.com/relab/gorums)
- [HotStuff paper](https://arxiv.org/pdf/1803.05069.pdf)
