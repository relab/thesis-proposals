# Using go to implement trusted execution enclaves

## Administrative

- Supervisor: Leander Jehl

## Prerequisites

- Go programming
- DAT320 Operating systems

## Project Description

A trusted execution environment (TEE), such as Intel software guard extensions (SGX) or ARM trust zone, allows to run code in a trusted environment on remote systems.
For example, this allows outsourcing operations to the cloud without the need to trust the cloud provider with your data or the correctness of your computations.
Similarly, this allows the employment of edge devices, which are located near users, allowing attackers to gain physical access.

The goal of this project is to evaluate a recent framework, Ego [1], for the implementation of trusted enclaves using the Go language.
As an example application, this project aims to reimplement the ContractBox smart contract framework [2].

## Milestones

* Study Ego, install, run and play with examples.
* Study ContractBox and plan for its reimplementation using Ego.
* Implement and evaluate the reimplemented framework.

## References

[1] https://github.com/edgelesssys/ego
[2] ContractBox: Not yet publicly available, but shared on request.
