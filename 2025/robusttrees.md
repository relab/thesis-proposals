# Robust trees

## Administrative

- Supervisor: Leander Jehl
- Contact: <leander.jehl@uis.no>


## Project Description

Previous work has shown that tree overlays can give significant performance improvements to the distribution of proposals and the aggregation of votes in BFT algorithms, as used in committee based blockchains.

However, tree overlays are very sensitive to failures, since a single nodes can prevent the aggregation of all votes from the subtree rooted in that single node.
The goal of this thesis is to investigate more robust tree-like structures, e.g. structures where every nodes has two parents. 
It is expected that such structures can make dissemination and aggregation less sensitive to failures but cause a certain performance overhead.

The goal for this thesis is to evaluate different designs for more robust tree structures.
Robustness can be evaluated analytically, or through large scale simulations. 
The performance overhead should be evaluated experimentally by implementing the chosen dissemination structure in a BFT framework.

The framework used for implementation should be the relab/hotstuff implementation, or the Kauri code base.

Optionally, different tree-like structures could be evaluated against the goal of inclusion defined in Iniva.

Relevant related work is:
- Kauri: https://dl.acm.org/doi/pdf/10.1145/3477132.3483584
- Iniva: https://arxiv.org/pdf/2404.04948