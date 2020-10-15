# Implement Reconfiguration for the Gorums/HotStuff Protocol

## Administrative

- Supervisor: Hein Meling and Leander Jehl

## Prerequisites

- DAT520 Distributed Systems or DAT650 Blockchain Technology
- Proficient in the Go programming language

## Background on Gorums

Gorums is a novel framework for building fault tolerant distributed systems via group-RPCs (quorum calls) developed at UiS.
Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses.
Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies.
These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed.
Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls.
Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

## Project description

A recent paper from VMware research describes a really neat Byzantine tolerant replication protocol called HotStuff.
HotStuff is envisioned to be suitable for blockchain implementations, and in fact HotStuff is used by the Libra cryptocurrency promoted by Facebook.

Recent work at UiS has implemented and evaluated the basic HotStuff protocol in the Gorums framework.
In this project, the goal is to implement reconfiguration for our Gorums/HotStuff implementation, and to evaluate it.

## Tasks / Milestones

- Learn to develop with Gorums
- Carefully read and analyze the HotStuff paper to understand how it is implemented with Gorums
- Review literature about reconfiguration
- Study how reconfiguration is handled in existing HotStuff implementations, including Libra's implementation
- Implement a selected set of reconfiguration policies for HotStuff with Gorums
- Evaluate the reconfiguration policies using microbenchmarks
- Evaluate the reconfiguration policies under various system workloads, e.g. a key-value storage system, with different read-write ratios
- Evaluate the reconfiguration policies under various failure and attack scenarios
- Compare with the existing HotStuff implementation and other protocols

## Reading material

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums source code](https://github.com/relab/gorums)
- [Gorums/HotStuff source code](https://github.com/relab/hotstuff)
- [HotStuff paper](https://arxiv.org/pdf/1803.05069.pdf)
- [HotStuff thesis](https://www.dropbox.com/s/n3no6zvsbrugf28/hotstuff-thesis.pdf?dl=0)
- [Gorums Reconfiguration thesis](https://www.dropbox.com/s/l8bn5dbgb3zlmyd/GorumsReconfiguration-223841_29568658_1.pdf?dl=0)
- [Raft thesis](https://www.dropbox.com/s/uff20f2oyqbae64/Pedersen_Sebastian.pdf?dl=0)
- [(PhD thesis) Reconfiguration for Fault Tolerant Asynchronous Systems](https://www.dropbox.com/s/yqpyez0rpq2mp0e/thesis.pdf?dl=0)
