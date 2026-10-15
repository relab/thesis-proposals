# Bachelor: Building a Replicated Service with Raft and Gorums

## Administrative

- Supervisor: Hein Meling
- Bachelor thesis

### Prerequisites

- Basic knowledge of distributed systems, networking, and concurrent programming.
- Go programming skills, or willingness to learn Go.
- Interest in fault-tolerant systems.

### AI Tools

Students may use AI tools and LLMs to explore the technologies and fill in technical gaps.
They remain responsible for understanding, testing, and documenting the resulting code and claims.

## Background and Motivation

Distributed services often keep several copies of important data so that they can continue operating when a server fails.
The replicas must agree on the same updates despite crashes, delays, and lost connections.
Consensus protocols solve this problem by making the replicas agree on an ordered sequence of operations.

[Raft][1] is a widely used consensus protocol designed to be understandable.
A Raft cluster elects a leader, which orders client commands and replicates them to the other servers.
An operation is committed after a majority has accepted it, allowing all replicas to apply commands in the same order.
Raft is used in systems such as [etcd][8], which stores Kubernetes cluster state, as well as [CockroachDB][10] and [Consul][11].
It is therefore a practical way to learn about replication, leader election, quorums, concurrency, and failure handling.

### gRPC and Gorums

[gRPC][2] is a remote procedure call framework.
Services and messages are defined with [Protocol Buffers][3], which are used to generate typed Go client and server code.
gRPC handles communication between individual processes, but applications must still handle failures, timeouts, and multiple replies.

[Gorums][4] is a Go framework developed at UiS for communication with groups of replicas.
It builds on gRPC and lets applications send requests to a group and use quorum functions to decide when enough replies have arrived.
Gorums handles some communication details, while the students implement the Raft protocol itself.

## Project Description

Implement Raft in Go using Gorums and use it to build one of these demonstrators:

- A **replicated key-value store** in which clients can read and update values.
- A **replicated log** in which clients can append and inspect committed records.

The system should run with several replicas, continue serving clients while a majority is available, and demonstrate recovery from leader and follower failures.
The result should be a clear educational prototype rather than a production database.

### Core Scope

- Learn the relevant parts of Raft, gRPC, Protocol Buffers, and Gorums.
- Implement a fixed-membership Raft cluster using Gorums.
- Build a simple client and one of the replicated services above.
- Test the main protocol behavior under normal operation and selected failures.
- Deliver documented code, running instructions, and a bachelor report discussing the design and results.

The exact design, APIs, failure model, and test strategy should be developed by the students and adjusted to the group size.
The core implementation may keep state in memory if this limitation is documented.

### Possible Extensions

Possible extensions include persistent recovery, snapshots, request deduplication, visualization, more extensive fault injection, or a comparison with direct gRPC communication.
Dynamic membership is outside the expected core scope.

## Evaluation

Demonstrate the service with at least three replicas and repeatable client workloads.
Test normal operation, follower failure, leader failure and re-election, and a replica catching up after falling behind.
Check that replicas agree on committed operations and that progress requires a communicating majority.
Report basic latency and throughput results, along with the assumptions and limitations of the implementation.

## Reading Material

1. [In Search of an Understandable Consensus Algorithm (Raft)][1] and the [Raft website][7].
2. [Introduction to gRPC][2] and the [Protocol Buffers overview][3].
3. [Gorums paper][4], [source code][5], and [user guide][6].
4. [An Analysis of Quorum-based Abstractions: A Case Study using Gorums to Implement Raft][12].

[1]: https://raft.github.io/raft.pdf
[2]: https://grpc.io/docs/what-is-grpc/introduction/
[3]: https://protobuf.dev/overview/
[4]: https://ieeexplore.ieee.org/document/7980198
[5]: https://github.com/relab/gorums
[6]: https://github.com/relab/gorums/blob/master/doc/user-guide.md
[7]: https://raft.github.io/
[8]: https://github.com/etcd-io/raft
[10]: https://www.cockroachlabs.com/docs/stable/architecture/replication-layer
[11]: https://developer.hashicorp.com/consul/docs/architecture/consensus
[12]: https://dl.acm.org/doi/10.1145/3231104.3231108
