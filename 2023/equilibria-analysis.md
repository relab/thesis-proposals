# Evaluating formal methods for equilibria analysis

## Administrative

- Supervisor: Leander Jehl and Arian Baloochestani

## Prerequisites

- DAT530 Discrete Simulation and Performance Analysis

## Project Description

Distributed algorithms are notoriously difficult to get right, and different tools (TLA/Petri nets) have been proposed to specify and verify the correctness of such algorithms in the presence of failure. 
In the area of blockchain and decentralized systems, complex distributed algorithms are enhanced with reward systems, that encourage participation and correct behavior.
The rewarding mechanisms typically aim to establish Nash-Equilibria, i.e. situations, where any node, that unilaterally deviates from the protocol, receives a reduced reward.

The goal for this project is to build a tool, that can analyse reward systems in TLA+ models.
The goal of such an analysis is to both verify the existence of a predefined Nash-Equilibrium, as well as the systematic search for potentially unknown Equilibria.
Since TLA+ is only partially suited for such an analysis, in this project, we will explore the possibility to extract a model from the TLA toolbox and process it using external tools.

You will work on a simple sample of a reward mechanism from the literature, however, the goal is to establish methods easily transferable to other algorithms. You can also build on an existing TLA+ model.

## Tasks / Milestones

- Study the existing TLA+ model
- Extract state graph from the TLA toolbox and parse with external tool
- Model the equilibrium condition 
- Verify a well known Equilibrium for given instantiations of the model, comparing running times of the external tool with verification inside the toolbox
- Design method to search for existence, or verify absence of Equilibria in external tool

## Reading material

[1] Amoussou-Guenou, Yackolley, et al. "Rational behavior in committee-based blockchains." *Cryptology ePrint Archive* (2020). https://eprint.iacr.org/2020/710.pdf

[2] The TLA+ homepage: http://lamport.azurewebsites.net/tla/tla.html

[3] Lamport, Leslie, and Fred B. Schneider. "Verifying hyperproperties with TLA." *2021 IEEE 34th Computer Security Foundations Symposium (CSF)*. IEEE, 2021. https://ieeexplore.ieee.org/abstract/document/9505222

