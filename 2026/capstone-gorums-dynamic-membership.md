# Capstone: Paxos Dynamic Membership using Gorums

- Supervisor: Hein Meling
- Fall capstone project, 10 ECTS

## Motivation

Multi-Paxos and similar consensus protocols assume a fixed set of participants.
Real deployments, however, need to replace failed nodes, scale capacity, or roll out software updates without halting the service.
This requires *reconfiguration*: safely transitioning the protocol from one configuration (set of servers) to another while preserving safety and liveness.

Reconfiguration is non-trivial even for crash-fault-tolerant protocols.
A naïve switch can allow two configurations to each decide a different value for the same consensus instance.
Getting it right requires careful reasoning about which instances belong to which configuration, how state is transferred to new members, and how old instances are finalized.

The goal is to design, implement, and evaluate one or more reconfiguration schemes for Multi-Paxos using [Gorums][gorums], and to deliver the result as a reusable DAT520 lab assignment with QuickFeed tests.

## Goal

1. Implement at least one correct reconfiguration scheme for Multi-Paxos in Go using Gorums.
2. Write a QuickFeed test suite that automatically grades student submissions of the same lab.
3. Write a student-facing lab description that explains the task, the relevant theory, and how the tests work.

A clean, well-tested baseline is more valuable than a large but fragile prototype.

## Background: Reconfiguration Approaches

The original DAT520 assignment text describes two main approaches; both remain valid starting points:

**Configuration-per-instance (Vertical Paxos / Flexible Paxos style)**
A special *reconfiguration command* is agreed upon through normal consensus and takes effect at a designated future slot.
Nodes that learn of the new configuration stop using the old quorum for subsequent slots.
Instances that stalled in the old configuration are finalized with a `noop` command before the cut-over.

**Stop-migrate-restart (State Transfer style)**
The current configuration is halted cleanly, every pending instance is finalized, a state snapshot is taken, the snapshot is transferred to new members, and consensus restarts in the new configuration.
This is conceptually simpler but requires a reliable snapshot and transfer mechanism.

Section 2 of Lamport, Malkhi, and Zhou (2010) [[1]][lmz] describes these approaches and their trade-offs in detail.
Both approaches should be understood and the choice(s) made should be justified.

## Suggested Stages

1. Read the core reconfiguration material ([[1]][lmz], [[2]][smart]) and understand the Multi-Paxos baseline in the DAT520 code repository.
2. Define the reconfiguration protocol: what messages are added, when a configuration becomes active, and how old instances are finalized.
3. Implement the reconfiguration logic and integrate it with the existing Multi-Paxos Gorums service definitions.
4. Write unit and integration tests: normal-case reconfiguration, scale-out (3→5→7 servers), node replacement, and reconfiguration while client requests are in flight.
5. Package the tests as a QuickFeed-compatible test suite with clear pass/fail criteria.
6. Write the lab description: motivation, protocol description, task specification, and a guide to running the tests.
7. (Optional) Run a small benchmark comparing throughput and latency before and after reconfiguration, and across the two reconfiguration approaches.

## Deliverables

| Deliverable | Description |
|---|---|
| Protocol implementation | Working reconfiguration in Go with Gorums |
| QuickFeed test suite | Automated tests that grade a student's implementation |
| Lab description | A clear, standalone lab write-up for DAT520 students |
| Report | Design rationale, trade-offs, limitations, and optional benchmarks |

## Questions to Explore

- How does Gorums' configuration model (creating a `Configuration` object from a set of node addresses) interact with dynamic membership changes?
- Can a reconfiguration command be expressed cleanly as a Gorums quorum-call, or does it require out-of-band coordination?
- How should a new `Configuration` be composed from the existing `Manager` and the updated node set, using combinators such as `WithNewNodes`, `And`, or `WithoutNodes`, and when does the old configuration need to remain live during the transition?
- What is the minimum set of invariants that a test suite must check to confirm safety and liveness across a reconfiguration?
- How much throughput is lost during a stop-migrate-restart reconfiguration compared to the configuration-per-instance approach?

## Master's Thesis Continuation

A capstone on reconfiguration can grow into a thesis in several directions:

- Comparing multiple reconfiguration approaches under realistic workloads and fault scenarios.
- Designing a general Gorums abstraction for reconfigurable quorum groups, applicable beyond Paxos.
- Studying liveness under concurrent reconfigurations or adversarial reconfiguration timing.
- Extending reconfiguration to a Byzantine fault-tolerant protocol such as HotStuff.
- Implementing Raft with Gorums and adding joint-consensus reconfiguration, building on prior Gorums/Raft work [[3]][raft-gorums].
- Developing a principled test methodology for reconfiguration correctness (e.g., linearizability checking across configuration boundaries).

## Reading Materials

- [Gorums paper][gorums-paper]
- [Gorums source code][gorums]
- [Reconfiguring a State Machine][lmz] — Lamport, Malkhi, and Zhou (2010)
- [The SMART Way to Migrate Replicated Stateful Services][smart] — Lorch et al. (EuroSys 2006)
- [Vertical Paxos and Primary-Backup Replication][vertical] — Lamport, Malkhi, and Zhou (2009)
- [Paxos Made Simple][paxos-simple] — Lamport (2001)
- [An Analysis of Quorum-based Abstractions: A Case Study using Gorums to Implement Raft][raft-gorums] — Pedersen, Meling, and Jehl (2018)

[gorums-paper]: https://ieeexplore.ieee.org/document/7980198
[gorums]: https://github.com/relab/gorums
[lmz]: https://dl.acm.org/doi/10.1145/1753171.1753191
[smart]: https://dl.acm.org/doi/10.1145/1218063.1217934
[vertical]: https://www.microsoft.com/en-us/research/publication/vertical-paxos-and-primary-backup-replication/
[paxos-simple]: https://lamport.azurewebsites.net/pubs/paxos-simple.pdf
[raft-gorums]: https://dl.acm.org/doi/10.1145/3231104.3231108
