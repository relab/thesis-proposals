# Evaluating formal methods for equilibria analysis

## Administrative

- Supervisor: Leander Jehl and Arian Balouchestani

## Prerequisites

- DAT530 Discrete Simulation and Performance Analysis

## Project Description

Distributed algorithms are notoriously difficult to get right, and different tools (TLA/Petri nets) have been proposed to specify and verify the correctness of such algorithms in the presence of failure. 
In the area of blockchain and decentralized systems, complex distributed algorithms are enhanced with reward systems, that encourage participation and correct behavior.
The rewarding mechanisms typically aim to establish Nash-Equilibria, i.e. situations, where any node, that unilaterally deviates from the protocol, receives a reduced reward.

The goal for this project is to investigate the use of established tools for the formal analysis of distributed algorithms, to also analyze reward systems. The goal of such an analysis is to both verify the existence of a predefined Nash-Equilibrium, as well as the systematic search for potentially unknown Equilibria.

You will work on a simple sample of a reward mechanism from the literature, however, the goal is to establish methods easily transferable to other algorithms. You can also build on an existing TLA+ model.



## Tasks / Milestones

- Model the given reward mechanism in 2 of the tools
- Model the equilibrium condition
- Verify a well known Equilibrium for given instantiations of the model, comparing running times of different tools
- (optional) design method to search for existance, or verify absence of Equilibria.

## Reading material

[1] Rational behavior in committee-based blockchains
[2] Verifying Hyperproperties With TLA
