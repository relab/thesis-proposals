## Master's Thesis Project:
# Learning topology scores in presence of faults

## Administrative

- **Program:** Computer Science/Data Science
- **Project period:** Fall 2027
- **Supervisor(s):** Leander Jehl

## Research Question

> Can machine learning, trained on measurements of individual topologies' performance under faults, improve the scoring function used to search for low-latency tree overlays?

## Background and Motivation

The ReLab research group works on fault-tolerant distributed systems, including consensus and Byzantine fault-tolerant (BFT) protocols for blockchains.
As these systems are deployed across wide-area networks, the topology used to organize replicas has a large impact on latency and throughput, and this impact grows worse in the presence of faulty or misbehaving replicas.

A recent paper from the group, [OptiLog: Assigning Roles in Byzantine Consensus][1], introduces a logging framework that collects real-time network measurements and uses them to search for low-latency tree overlays for the Kauri protocol.
OptiLog searches for a suitable overlay using simulated annealing: starting from a candidate assignment of replicas to positions in the tree, it repeatedly proposes new candidates by swapping the roles of two replicas, and accepts or rejects them based on a *scoring function* that estimates the candidate's latency from the collected measurements.
This scoring function is static and hand-crafted; it does not learn from the actual, measured performance of the topologies that have already been tried, nor does it explicitly account for the effect of faulty replicas on that performance.

Closely related work, [Beware: Robust and Automated Reconfiguration of Byzantine Wide-Area Replication][2], addresses a similar problem for leader- and weight-based BFT configurations rather than tree overlays.
Beware applies machine learning to iteratively adjust its configuration search so that it converges towards configurations that remain performant even when nodes misreport their measurements or otherwise misbehave.
This shows that a learned, measurement-driven scoring function can be made more robust to faults and adversarial behavior than a static one, at least for the leader/weight-assignment problem studied in that paper.

The goal of this thesis is to investigate the benefits of applying a similar approach to tree overlays. 
Can the static scoring function used for the search of a tree overlay (e.g. in the simulated annealing procedure used in OptiLog) be replaced or adjusted with a learned function? 
Does this approach allow the search to react to observed failures and how many trials are needed to find a performant overlay in the presence of faults?

The learned scoring function should ideally become more accurate over time, and more robust to inaccurate or falsified measurements reported by faulty replicas, than the static scoring function currently used in OptiLog.

## Evaluation

The thesis should evaluate how well the learned scoring function predicts the performance of tree topologies under faults. The evaluation should combine both simulation and system experiments.

- **Simulation**: Given OptiLogs static scoring function, it is possible to evaluate configurations under faults. While this fault aware scoring function is not achievable in practice, where faults may avoid detection, it can be used to simulate measurements under faults and provides a baseline for the learned function.
This simulation allows large scale experiments.

- **System performance**: Real system performance may significantly differ from simulation, due to scheduling effects and other unpredictable variation. If data is collected in real system runs, can the scoring function accurately predict performance, and find suitable configurations in presence of faults?

- **Other objectives**: Additional to the above, the performance or running time of the learned scoring function and its impact on the search time for simulated annealing should be evaluated.
Further, the thesis should investigate how much data probes are needed to find a working or suitable configuration in the presence of faults.


## Scope

- Core work:
  - Review OptiLog's scoring function and simulated annealing search, and Beware's approach to learning a robust scoring function.
  - Decide whether to train a general learned scoring function or to do a simpler online-learning or regression-based correction applied on top of OptiLog's existing scoring function.
  - Design and implement a learned scoring function for tree overlays, trained on measurements for individual overlays.
  - Integrate the learned scoring function into OptiLog's simulated annealing search (or a comparable search technique).
  - Evaluate the resulting, measurement guided search in the simulation framework.
- Optional work:
  - Evaluate the scoring function using measurements and faults in a real deployment of Optilog.
  - Try to design or learn a dynamic rather than static attack, that causes the search to repeatedly output low performant configurations.
- Alternatives: 
  - If the amount of measurements needed to find a working tree in the presence of faults proofs unrealistically large, a tree structure with additional redundancy could be investigated.

## References

1. [OptiLog: Assigning Roles in Byzantine Consensus](https://arxiv.org/abs/2502.15428)
2. [Beware: Robust and Automated Reconfiguration of Byzantine Wide-Area Replication](https://arxiv.org/abs/2606.16740)

[1]: https://arxiv.org/abs/2502.15428
[2]: https://arxiv.org/abs/2606.16740
