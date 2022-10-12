# Formal verification of a tree data structure

## Administrative

- Supervisor: Leander Jehl

## Prerequisites

- Go programming

## Background

Blockchains are run in an open and uncontrolled environment and handle significant values. 
Additionally, software updates are often difficult or even impossible.
Therefore, the correctness and security of blockchain systems is of utmost importance.
Formal verification allows to prove the correctness of algorithms and code before deployment.

The Hotstuff consensus algorithm [1] is a key component of several blockchain systems.
The relab research group maintains a prototype implementation of Hotstuff [2].
A prior analysis [3] has shown that the key element to formal correctness of Hotstuff is a tree structure.

## Project Description

The goal for this thesis is to create a formally verified tree structure.
The structure should use the interface used in the relab/hotstuff implementation [2] and specification from the formal analysis [3]. 

To create formal verified code you will model the tree using Dafny [4] to proof correctness, and then extract Go code from your proof. You should also evaluate the ability to include and evalute the extracted code the existing relab/hotstuff implementation.


## References

[1] Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness." *Proceedings of the 2019 ACM Symposium on Principles of Distributed Computing*. 2019. https://dl.acm.org/doi/pdf/10.1145/3293611.3331591

[2] https://github.com/relab/hotstuff

[3] Jehl, Leander. "Formal verification of hotstuff." *International Conference on Formal Techniques for Distributed Objects, Components, and Systems*. Springer, Cham, 2021. https://link.springer.com/chapter/10.1007/978-3-030-78089-0_13

[4] https://dafny.org/