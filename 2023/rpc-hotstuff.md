# Building an rpc based hotstuff implementation

## Administrative

- Supervisor: Leander Jehl

## Prerequisites

- DAT530 Distributed systems

## Project Description

The goal of this project is, to build a diverse implementation of the hotstuff bft algorithm [1].
Towards this end, we want to devide the hotstuff algorithm into two parts, a leader and a server/replica.
The replica should have a pure rpc based interface and only reply to requests from one or multiple leaders, i.e. no traffic going between replicas.
Building on a common rpc library available in different languages, i.e. GRPC the goal is to implement 2 or more versions of the replica in different languages.

## Reading material

[1] Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness." *Proceedings of the 2019 ACM Symposium on Principles of Distributed Computing*. 2019. https://dl.acm.org/doi/pdf/10.1145/3293611.3331591