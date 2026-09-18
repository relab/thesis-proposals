# Master's Thesis Project: DAG under client skew

## Administrative

- **Program:** Computer Science
- **Project period:** Spring 2027
- **Supervisor(s):** Leander Jehl
- **Prerequsite:** DAT520  or DAT655

## Research Question

> How do DAG-based BFT protocols behave under skewed client workloads?

## Background and Motivation

DAG-based BFT protocols (e.g., [Narwhal/Tusk](https://arxiv.org/abs/2105.11827), [Bullshark](https://arxiv.org/abs/2201.05677), [Mysticeti](https://arxiv.org/abs/2310.14821), [Sui's consensus](https://docs.sui.io/concepts/sui-architecture/consensus), [DAG-Rider](https://arxiv.org/abs/2102.08325)) decouple data dissemination from ordering by having every node build its own local DAG of batches and periodically propose them to others.
A common assumption in evaluations of these systems is that client load is roughly uniform across all nodes: every validator receives a similar rate and mix of client requests.
In practice this assumption rarely holds — clients may be geographically or organizationally concentrated, request types (e.g., reads vs. writes, large vs. small transactions) may not be evenly distributed, and some validators may be preferred due to lower latency or being closer to major client populations.

It is not well understood how DAG-based protocols perform when this assumption breaks down.
Because these protocols rely on nodes referencing each other's batches to make progress, a skewed workload could create imbalances in DAG growth, uneven batch/certificate sizes, increased latency for requests submitted to overloaded nodes, or unfairness in how quickly transactions from different clients are committed.
It is also unclear whether existing deployed systems (e.g., [Sui](https://docs.sui.io/concepts/sui-architecture/consensus), [Aptos](https://aptos.dev/en/network/blockchain/consensus), or other DAG-based production blockchains) have explicit load-balancing, request-routing, or fairness mechanisms to mitigate such skew, or whether they simply rely on the assumption of uniform load.

## Evaluation

The students will use one or more academic DAG-BFT prototypes (e.g., [Narwhal/Bullshark](https://arxiv.org/abs/2201.05677), or a similar open-source implementation) and inject client workloads with controlled skew:

- **Load skew:** vary the fraction of client requests directed to a subset of nodes, ranging from uniform to highly concentrated.
- **Request-type skew:** where relevant, vary the mix of request types (e.g., read/write ratio, payload size) sent to different nodes.

Experiments should be run on a simulated wide-area network with realistic, diverse inter-node latencies (e.g., using `tc netem`, or a network simulator such as Berger et al. [7], to capture the interaction between workload skew and geographic distribution.

Metrics to measure include end-to-end and per-client latency, throughput, DAG growth/round latency, and fairness of commit order across clients/nodes.
The baseline is the same prototype(s) under a uniform workload.

As a complementary study, the students should investigate whether deployed DAG-based systems document or implement mechanisms (e.g., request routing, rate limiting, load balancing, or fairness guarantees) intended to address client load skew, and report their findings.

## Scope

- Core work: Set up and instrument a DAG-based BFT prototype; build a workload generator capable of injecting configurable client-load and request-type skew; run experiments on a simulated WAN topology; analyze latency, throughput, and fairness under varying skew.
- Optional work: Investigate and prototype mitigation mechanisms (e.g., request redirection or load-aware batching) and evaluate their effect on skewed workloads.
- Alternatives: If a full WAN emulation is infeasible, evaluate on a smaller set of representative latency profiles (e.g., same-region vs. cross-region) instead of a full topology.

## References

1. Danezis et al., ["Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus"](https://arxiv.org/abs/2105.11827)
2. Spiegelman et al., ["Bullshark: DAG BFT Protocols Made Practical"](https://arxiv.org/abs/2201.05677)
3. Keidar et al., ["All You Need is DAG"](https://arxiv.org/abs/2102.08325) (DAG-Rider)
4. Mysten Labs, ["Mysticeti: Reaching the Limits of Latency with Uncertified DAGs"](https://arxiv.org/abs/2310.14821)
5. [Sui consensus documentation](https://docs.sui.io/concepts/sui-architecture/consensus)
6. [Aptos consensus documentation](https://aptos.dev/en/network/blockchain/consensus)
7. Berger et al., ["Exploring Scalability of BFT Blockchain Protocols through Network Simulations"](https://doi.org/10.1145/3689343) (network simulator)
