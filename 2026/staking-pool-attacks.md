# Staking pool attack simulation

## Administrative

- Supervisor: Leander Jehl
- Master thesis

## Prerequisites

- DAT655 or strong interest in token economy

## Background and Motivation

Proof of Stake blockchains with committee based consensus protocols often reward participating nodes, if their signatures are included in the blockchain.
Members of the Relab research group have shown in several publications [1][1], [2][2], [3][3] that these rewards may be subject to attacks.
However, many of the attacks are unlikely, since the cost of the attack is often larger than the loss suffered by the victim.

However, these works did not look at staking providers and liquid staking. Liquid staking allows small investors to participate in staking rewards, depositing small amounts with limited or no binding periods.

## Project Description

The goal for this thesis is to investigate whether otherwise costly attacks can be profitable if a well functioning market with multiple liquid staking providers exist.
The intuition behind this hypothesis is that attacks on one staking bool may convince profit seeking investors to move to a different staking pool and that the benefit of additional customers can outweigh the cost of an attack.

### Objectives

1. **Extend Simulation Framework**: Extend the existing [DPoS simulation framework](https://github.com/relab/DPoS-simulations) to model the behavior of investors in liquid staking.

2. **Find suitable parameters**: Find suitable parameters for attacks, profitability, the working on staking pools, and the behavior of investors. Parameters may be based on related work, or analysis of existing decentralized markets.

3. **Evaluation**: Use the simulation framework to perform extensive evaluation, documenting the impact of different parameters.

4. **Analysis**: Summarize evaluation results to extract relevant findings.

[1]: https://relab.website/publication/rebop
[2]: https://arxiv.org/pdf/2404.04948
[3]: https://arxiv.org/pdf/2505.24482
