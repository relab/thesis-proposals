# Bachelor: Optimizing Overlay Topologies with Population-Based Search

## Administrative

- Supervisor: Leander Jehl
- Group Composition: 2 students
- Bachelor thesis

## Background

The ReLab research group works on fault-tolerant distributed systems, including consensus and Byzantine fault-tolerant (BFT) protocols for blockchains.
As BFT systems are deployed across wide-area networks, the choice of communication topology among replicas becomes critical for latency and throughput.

A recent paper from the group, [OptiLog: Assigning Roles in Byzantine Consensus][1], presents a logging framework that collects real-time network measurements and uses them to assign roles to replicas in globally distributed deployments, even in the presence of faults.
OptiLog is applied to two BFT protocols: Aware, an optimized PBFT-like protocol, and Kauri, a tree-based protocol for large-scale deployments.
To find a suitable tree overlay for Kauri, OptiLog uses *simulated annealing*: starting from a candidate assignment of replicas to positions (roles) in the tree, the algorithm repeatedly proposes new candidate topologies by randomly swapping the roles of two replicas, and evaluates each candidate's expected latency using the collected measurements.
Better candidates are always accepted, while worse candidates are accepted with a probability that decreases over time, allowing the search to escape local optima early on while converging towards a good solution later.
This process yields a single tree overlay, which the experiments show has substantially lower latency (39% lower than Kauri's default overlay when deployed across 73 worldwide cities).

## Project Description

Simulated annealing, as used in OptiLog, explores the search space by maintaining and refining a single candidate topology at a time.
This is simple and effective, but it discards information about other promising topologies found along the way, and it provides no way to compare or fall back on alternative candidates, e.g., if the top candidate later turns out to be unsuitable due to a fault or a churn event.

The goal of this thesis is to extend the simulation framework used to evaluate tree overlays in OptiLog with more advanced optimization and search techniques.
In particular, the thesis should implement and evaluate techniques that maintain a *population* or *archive* of multiple, varying candidate topologies throughout the search, rather than a single evolving candidate.
Such approaches could make it possible to return several good, but structurally different, topologies to the operator or protocol, e.g., to support fast fallback options or to expose trade-offs between latency and other properties (such as fault-tolerance or load balancing).

Concrete alternatives to investigate and implement include:

- **Genetic Algorithms (GA)**, which maintain a *population* of candidate topologies and evolve it over generations using selection, crossover, and mutation operators, keeping many varying candidates alive throughout the search [2].
- **Particle Swarm Optimization (PSO)**, which maintains a *swarm* of candidate topologies ("particles") that move through the search space, guided by each particle's own best-found solution and the swarm's overall best, again naturally keeping multiple diverse candidates around at all times [3].

The student(s) should implement one of these approaches within (or alongside) OptiLog's existing simulation framework implemented in Go, and evaluate it against the current simulated annealing baseline in terms of solution quality, diversity of returned candidates, and computational cost.

### Resources

[1]: https://arxiv.org/abs/2502.15428
[2]: https://www.geeksforgeeks.org/dsa/genetic-algorithms/
[3]: https://www.geeksforgeeks.org/particle-swarm-optimization-pso-an-overview/

