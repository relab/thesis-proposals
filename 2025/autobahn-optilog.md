# Implement OptiLog and OptiTree in Autobahn's BFT Framework

## Administrative

- Supervisors: Hein Meling, Hanish Gogada, Leander Jehl
- Contact: <hein.meling@uis.no>

## Prerequisites

- DAT520 Distributed systems
- Rust programming, or willing to learn

## Project Description

Byzantine fault tolerant (BFT) protocols are often used to implement blockchains, but their lack of scalability is a challenge.
The goal in this project is to use OptiLog to implement OptiTree, which is a scalable tree-based BFT protocol.

The OptiLog architecture is a novel architecture for metrics collection designed by the Relab research group.
In this project, we want to reimplement the OptiLog architecture in Rust on top of the [Autobahn][7] framework.
The original OptiTree and OptiLog implementations are written in Go.
However, we want to take advantage of existing Rust-based BFT implementations based on a production-grade implementation.
Moreover, Rust is known for its performance, and has the potential for verifying parts of the implementation using [Verus][8].

## Tasks

- Read [OptiLog][1] paper (will be made available), [HotStuff][2], [Autobahn][3] papers
- Become familiar with [autobahn][7] and [relab/optilog][6] (will be made available)
- Implement the OptiLog sensor and monitor mechanisms within the Autobahn framework
- Implement the OptiTree algorithm on top of OptiLog's mechanisms
- Evaluate the OptiTree and compare with existing solution

[1]: https://not-available.yet/
[2]: https://dl.acm.org/doi/pdf/10.1145/3293611.3331591
[3]: https://sigops.org/s/conferences/sosp/2024/assets/papers/sosp24-final26-acmpaginated.pdf
[6]: https://github.com/relab/optilog
[7]: https://github.com/neilgiri/autobahn-artifact
[8]: https://sigops.org/s/conferences/sosp/2024/assets/papers/sosp24-final125-acmpaginated.pdf
