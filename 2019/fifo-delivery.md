# FIFO Delivery for Multiparty RPC Framework Using QUIC

### Supervisors: Hein Meling and Leander Jehl

### Prerequisites:

- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Project Description:

Gorums is a framework for group-RPCs (quorum-calls) developed at UiS. A quorum-call allows to invoke a remote procedure simultaneously on multiple hosts and collect and combine the replies. The current version of Gorums relies on [gRPC](https://grpc.io/) to perform the individual remote procedure calls in a quorum-call.

The current version of Gorums does not ensure that individual RPCs are executed in order. This is due to the desire to handle multiple individual RPCs concurrently in separate goroutines, and the obvious solutions to invoke individual RPCs sequentially has a very negative performance penalty. For a detailed description of the problem see the relevant GitHub [issue](https://github.com/relab/gorums/issues/16).

The aim for this project is to reimplement Gorums ensuring that individual RPCs are executed in the order they are invoked. It is particularly interesting to examine the QUIC protocol in this context.

### Tasks / Milestones:

- Analyse different design alternatives (e.g. gRPC channels, simple TCP, the UDP-based QUIC protocol) to build upon
- Experiment with different design alternatives through hardcoded implementations
- Evaluate the design alternatives in terms of performance and code complexity
- Redesign and reimplement Gorums to ensure in-order execution of RPCs using selected implementation technology
- Evaluate new implementation using microbenchmarks
- Evaluate new implementation using a system implemented for the previous version of Gorums

### Gorums Background:

[Gorums](https://github.com/relab/gorums) is a novel framework for building fault tolerant distributed systems. Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses. Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies. These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed. Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls. Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

### Reading material:

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums Source code](https://github.com/relab/gorums)
- [The Road to QUIC (Blog post)](https://blog.cloudflare.com/the-road-to-quic/?hn)
- [QUIC Wikipedia page](https://en.wikipedia.org/wiki/QUIC)
- [QUIC Implementation in Go](https://github.com/lucas-clemente/quic-go)
