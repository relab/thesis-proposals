# Implementation of a Test Framework for HotStuff

## Administrative

- Supervisor: Hanish Gogada, Leander Jehl, and Hein Meling

## Prerequisites

- DAT520 Distributed systems
- Go programming language

## Background

Byzantine fault-tolerant protocols are used to replicate arbitrary applications on multiple servers, called replicas while tolerating arbitrary failures or attacks from a subset of the replicas.
HotStuff is a Byzantine fault-tolerant state machine replication protocol designed for permissioned blockchains.
Relab research group implemented a modular and extensible framework to design, implement and analyze BFT protocols.
Presently, the framework supports a few variants of HotStuff protocol like Chained HotStuff, Fast HotStuff, and Simple HotStuff.
We developed a test suite based on Twins approach.
Along with the test suite, we also developed a deployment tool to test the implementation on various configurations.

## Project Description

This project aims to build a new extensible test framework for our HotStuff implementation.
New test framework development involves creating tools for performance regression evaluations, network partitions, and fuzz testing.
Project work includes improving the existing test suites and integrating them with the new framework.
The framework shall integrate the third-party static code analyzers and log analyzers.
Eventually the test framework shall be integrated with github containers to create a CI system.

## Milestones

Learning outcomes of the project are

- Understand the existing design and implementation of the framework.
- Study existing literature to understand existing testing paradigms for BFT testing.
- Design and implement new test framework for the HotStuff.
- Conduct experiments to analyze and document the functionality of the test framework.

## Reading Material

[1] [HotStuff: BFT Consensus in the Lens of Blockchain](https://arxiv.org/abs/1803.05069)
