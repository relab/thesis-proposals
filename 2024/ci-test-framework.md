# Implementation of a Continuous Integration Test Framework for HotStuff

## Administrative

- Supervisor: Hanish Gogada, Leander Jehl, and Hein Meling
- Prof Meling is currently on sabbatical, but will be available for physical meetings from November 27, 2023.
- Before that I will be happy to answer questions by email, or set up a Zoom call to discuss the project with prospective students.
- Contact: <hein.meling@uis.no>
- Several students can work on this project.

## Prerequisites

- Strong interest in continuous integration and testing
- Willingness to learn about distributed systems
- Proficient in the Go programming language

## Background and Motivation

Byzantine fault-tolerant (BFT) protocols are used to replicate arbitrary applications on multiple servers, called replicas, while tolerating arbitrary failures or even attacks from a subset of the replicas.
HotStuff is a popular BFT state machine replication protocol designed for permissioned blockchains.

The Relab research group has implemented a modular and extensible framework to design, implement, and analyze BFT protocols.
Currently, the framework supports several variants of the HotStuff protocol, such as Chained HotStuff, Fast HotStuff, and Simple HotStuff.
We have also developed a test suite based on the [Twins approach][5].
Along with the test suite, we have developed a deployment tool to test the implementation on various configurations.

## Project Description

This project aims to build a new extensible test framework for our HotStuff implementation.
New test framework development involves creating tools for performance regression evaluations, network partitions, and fuzz testing.
Project work includes improving the existing test suites and integrating them with the new framework.
The framework shall integrate the third-party static code analyzers and log analyzers.
Eventually the test framework shall be integrated with github containers to create a CI system.

Moreover, the projects aims to improve our [hotstuff][3] implementation's capabilities to execute test various configurations in a distributed environment (on our cluster).
Our former student John Ingve Olsen has developed a solid foundation for running such experiments using [iago][1] and [wrfs][2].
However, we want to simplify and improve the user experience for using iago, both for running experiments on our cluster, and for running experiments on a local machine.
The goal is to facilitate running experiments on demand when new code is being added, to quickly detect performance regressions.

## Milestones

Learning outcomes of the project are

- Understand the existing design and implementation of the framework.
- Study existing literature to understand existing testing paradigms for BFT testing.
- Design and implement new test framework for the HotStuff.
- Conduct experiments to analyze and document the functionality of the test framework.

## Reading Material

- [HotStuff: BFT Consensus in the Lens of Blockchain][4]
- [The Twins Approach][5]
- [Fuzz Testing][6]

[1]: https://github.com/relab/iago
[2]: https://github.com/relab/wrfs
[3]: https://github.com/relab/hotstuff
[4]: https://arxiv.org/abs/1803.05069
[5]: https://malkhi.com/posts/2020/04/making-BFT-systems-robust/
[6]: https://go.dev/security/fuzz/
