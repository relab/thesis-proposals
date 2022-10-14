# Fuzz testing a GRPC service

## Administrative

- Supervisor: Leander Jehl and Hanish Gogada

## Prerequisites

- Excellent Go programming

## Background

Byzantine fault tolerant (BFT) protocols are used to implement a reliable service despite arbitrary behaviour and attacks from individual service participants. This model is well suited for Blockchains and similar systems implemented between distrustful parties.
Hotstuff [1] is one particular protocol designed for this model.
The Relab research group maintains a prototype implementation of Hotstuff, relab/hotstuff [2]. 

## Project Description

Fuzz testing is a technique where arbitrary inputs are provided to test the robustness of a system.
The goal of this thesis is to apply fuzz testing to the relab/hotstuff system.
For this you can build on an existing framework that implements scenario-tests.
The goal it for this thesis is to record and fuzz the messages in these scenarios.

The resulting fuzzed scenarios should be included in the CI pipeline.

## Resources

[1] Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness." *Proceedings of the 2019 ACM Symposium on Principles of Distributed Computing*. 2019. https://dl.acm.org/doi/pdf/10.1145/3293611.3331591

[2] https://github.com/relab/hotstuff
