# Fuzz testing a GRPC service

## Administrative

- Supervisor: Leander Jehl and Hanish Gogada

## Prerequisites

- Excellent Go programming

## Background

Byzantine fault tolerant (BFT) protocols are used to implement a reliable service despite arbitrary behaviour and attacks from individual service participants. This model is well suited for Blockchains and similar systems implemented between distrustful parties.
Hotstuff [1] is one particular protocol designed for this model.
The Relab research group maintains a prototype implementation of Hotstuff, relab/hotstuff [2]. 
This implementation is build on the GRPC rpc layer.

## Project Description

Fuzz testing is a technique where arbitrary inputs are provided to test the robustness of a system.
The goal of this thesis is to apply fuzz testing to a GRPC service, i.e. to test the services behaviour to arbitrary input, created on the basis of the service interface definition.

The relab/hotstuff implementation should serve as examle. Due to its failure model, system should not react with crash to any malformed messages.
Optionally, the resulting tool should be included in the CI pipeline of relab/hotstuff.

## Resources

[1] Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness." *Proceedings of the 2019 ACM Symposium on Principles of Distributed Computing*. 2019. https://dl.acm.org/doi/pdf/10.1145/3293611.3331591

[2] https://github.com/relab/hotstuff
