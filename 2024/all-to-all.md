# All-to-all Communication for Multiparty RPC

## Administrative

- Supervisor: Hein Meling
- Prof Meling is currently on sabbatical, but will be available for physical meetings from November 27, 2023.
- Before that I will be happy to answer questions by email, or set up a Zoom call to discuss the project with prospective students.
- Contact: <hein.meling@uis.no>

## Prerequisites

- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Project Description

Gorums is a framework for group-RPCs (quorum-calls) developed at UiS.
A quorum-call allows to invoke a remote procedure simultaneously on multiple hosts and collect and combine the replies.
The current version of Gorums relies on [gRPC](https://grpc.io/) to perform the individual remote procedure calls in a quorum-call.

However, the current version of Gorums is only suitable for point-to-multipoint-to-point communication; that is, invocation from a client to multiple servers, and each of which replies back to the client.
This limitation prevents us from using Gorums to implement important replication protocols, including classical Paxos (with all-to-all learns) and BFT protocols, that send prepare and commit messages directly to each of the other participants in the protocol in an all-to-all pattern.

The goal in this project is to design a novel Gorums architecture that facilitates such all-to-all communication patterns, enabling us to implement BFT protocols.

Being able to implement BFT protocols will greatly benefit prototyping and possibly even production quality protocol implementations, and could possibly have a significant impact on experimentation and evaluation of a variety of blockchain protocols.

To the best of our knowledge, there is no other RPC framework that supports the all-to-all pattern.
The supervisors for this project have been thinking about this problem for several years, and we have recently made a few realizations that makes us confident that this can be done.

The core ideas are: (i) clients invoke all-to-all RPC; (ii) servers need to process such requests in a quorum function and be able to return a value that can be used by Gorums's server-side runtime to determine to which servers and what message to send to those servers.
The individual RPCs need to attach meta-data in the RPC.
There is support for metadata in gRPC (if this is used for the implementation).
The Gorums server-side runtime needs to be implemented (and may need to be generated by extending the Gorums code generator to support server-side code generation.)
The protocol developer will need to implement a server-side quorum function that takes multiple "input" messages and determines if enough such messages have been received to constitute a quorum, followed by returning a single "input" message to be used by the Gorums runtime (as described above.)

### Tasks / Milestones

- Analyze different design alternatives
- Implement (hardcode) a protocol like Paxos or PBFT that requires all-to-all communication.
- Implementation of a code generator to generalize the Gorums framework to support all-to-all communication.
  This involves server-side code generation as well, typically built from a protobuf description.
  The developer still needs to implement a server-side quorum function.
- Evaluate new implementation using microbenchmarks.
- Evaluate new implementation using a system implemented for the previous version of Gorums.
- Compare with existing PBFT implementations and other protocols.

<!-- - This will involve implementing Gorums runtime code that interacts with a developer implementation of a server-side quorum function. -->
<!-- - Analyze, test, and evaluate this protocol implementation -->
<!-- - Testing may involve implementing several prototype protocols that require all-to-all. -->

A successful project will be publishable at a reputable conference.

### Gorums Background

[Gorums](https://github.com/relab/gorums) is a novel framework for building fault tolerant distributed systems. Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses. Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies. These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed. Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls. Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

### Reading material

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums Source code](https://github.com/relab/gorums)
