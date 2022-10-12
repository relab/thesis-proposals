# DOS testing for a BFT framework

## Administrative

- Supervisor: Leander Jehl and Hanish Gogada

## Prerequisites

- Excellent Go programming

## Background

Byznatine fault tolerant (BFT) protocols are used to implement a repliable service despite arbitrary behaviour and attacks from individual service participants. This model is well suited for Blockchains and similar systems implemented between distrustful parties.
Hotstuff [1] is one particular protocol designed for this model.
The Relab research group maintains a prototype implementation of Hotstuff, relab/hotstuff [2]. 
This implementation is build on the GRPC rpc layer.

## Project Description

The goal of this thesis is to design a testing framework that evaluates the ability of a relab/hotstuff replicas to withstand Denial of Service attacks (DOS), especially, to handle arbitrary input from other participants. 
To this end, the tool should introduce arbitrary changes to the Protobuf messages created by a relab/hotstuff replica, feed these into other replicas and see if they crash.
Optionally, the resulting tool should be included in the CI pipeline of relab/hotstuff.

## Resources

[1] Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness." *Proceedings of the 2019 ACM Symposium on Principles of Distributed Computing*. 2019. https://dl.acm.org/doi/pdf/10.1145/3293611.3331591

[2] https://github.com/relab/hotstuff
