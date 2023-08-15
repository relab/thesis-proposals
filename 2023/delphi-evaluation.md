# Network simulations for a BFT framework

## Administrative

- Supervisor: Leander Jehl

## Prerequisites

- Go programming

## Project Description

Byzantine fault-tolerant (BFT) protocols are at the core of modern blockchain ecosystems.
The Relab research group maintains a prototype for one such protocol, namely the Hotstuff consensus algorithm [1]. 

Evaluating the prototype in realistic wide-area scenarios is challenging and resource-intensive.
The evaluation via a network simulator would therefore be beneficial.

The goal of this project is to integrate the prototype with the Delphi-BFT network simulator [2,3].

## Milestones

* Study the Delphi-BFT network simulator.
* Integrate the relab/hotstuff with the Delphi-BFT network simulator.
* Run extensive simulation:
  * Compare small simulated deployments with real deployment
  * Evaluate large-scale and wide-area deployments in simulation
* (optional) Integrate small-scale simulations into the CI pipeline of relab/hotstuff.

## References

[1] https://github.com/relab/hotstuff
[2] https://github.com/Delphi-BFT/tool
[3] Berger, Christian, Sadok Ben Toumia, and Hans P. Reiser. "Simulating BFT Protocol Implementations at Scale." *arXiv preprint* (2022). https://arxiv.org/pdf/2208.14745.pdf