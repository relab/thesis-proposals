# Module Composition for Gorums

### Supervisors: Hein Meling

### Prerequisites:

- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Motivation:

Two key software engineering design principles are encapsulation and separation of concerns. That is, we ideally want to separate access to internal private data in different modules from one another (encapsulation), and we want to construct software modules with only a single task (only one concern). This if often complicated by the desire to build optimal distributed protocols that reduce the number of messages and the message size in a distributed system protocol.

### Gorums Background:

[Gorums](https://github.com/relab/gorums) is a novel framework for building fault tolerant distributed systems. Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses. Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies. These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed. Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls. Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

Over the last four years, we have built Gorums and used it to build several distributed protocols, including EPaxos, Raft, and several distributed storage implementations (including one based on erasure coded replicated storage and one for Byzantine fault tolerant storage). 

### Project Description:

Our previous experience with designing distributed algorithms with Gorums have revealed several issues composing different protocol modules such that sound software engineering design principles are upheld, including encapsulation and separation of concerns. Example modules include: failure detection module, consensus module, reconfiguration module, key-value storage module etc.

The goal is to design a robust and safe software architecture for module composition that adheres to the above mentioned software engineering design principles, and that can be incorporated into the Gorums framework. Gorums makes heavy use of code generation, and it is therefore reasonable to assume that the proposed module composition may also use code generation.

*Update: A recent dependency injection tool called wire seems like a promising approach to wire up different modules.*

### Tasks / Milestones: 

- Investigate existing layered and graph software architectures for module composition.
- Propose several design alternatives for layering with Gorums/gRPC.
- Implement at least two design alternatives (the most promising candidates).
- Evaluate the performance of the different design alternatives. Evaluation is expected to involve both performance overhead and software complexity overhead, such as subjective difficulty for developer to use module architecture, as well as objective software complexity metrics.
- Report on findings from evaluation and implementation. 

### Reading Material: 

- [Compile-time Dependency Injection With Go Cloud's Wire](https://blog.golang.org/wire)
- Textbook used in distributed systems
- Frausing and Meland's master's theses
- [Design document for layering in Gorums](https://github.com/relab/gorums/blob/master/doc/design-doc-layering.md)
- [Type-safe Dynamic Protocol Composition in Jgroup/ARM](http://www.ux.uis.no/~meling/papers/2009-protocolcomposition-daisw.pdf)
- Chapter describing Modules in Distributed Systems book (Ed. Sape Mullender)
- Horus and Ensemble group communication systems.
- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums Source code](https://github.com/relab/gorums)
