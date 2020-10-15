# State Machine Replication in the Gorums Framework

### Supervisors: Hein Meling and Leander Jehl

### Prerequisites:

- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Project Description:

Gorums is a framework for group-RPCs (quorum-calls) developed at UiS. A quorum-call allows to invoke a remote procedure simultaneously on multiple hosts and collect and combine the replies. The current version of Gorums relies on [gRPC](https://grpc.io/) to perform the individual remote procedure calls in a quorum-call.

In this project we want to compare the implementation of different algorithms (Paxos and Raft) for state machine replication in the Gorums framework. This project builds on previous work, where we implemented the Raft algorithm in the Gorums framework. During this implementation we experienced multiple difficulties due to the lack of the "separation of concerns" principle in the Raft algorithm.

The goal in this project is to implement the Paxos algorithm in the Gorums framework to understand if these difficulties can be avoided. The new implementation should also be compared experimentally to our Raft implementation.

### Tasks / Milestones:

- Utilize an existing implementation of a replicated key-value store and the Raft algorithm to repeat existing experiments
- Implement the Paxos algorithm using the Gorums framework
- Evaluate the novel Paxos implementation against the existing Raft implementation as module for the key-value store
- Report on findings from evaluation and implementation, concluding on the feasibility to implement Paxos in the Gorums framework and a comparison with the existing Raft implementation.

### Gorums Background:

[Gorums](https://github.com/relab/gorums) is a novel framework for building fault tolerant distributed systems. Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses. Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies. These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed. Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls. Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

### Reading material:

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums Source code](https://github.com/relab/gorums)
- [Raft algorithm](https://raft.github.io/)
- [Raft in Gorums thesis](https://brage.bibsys.no/xmlui/handle/11250/2455424)
