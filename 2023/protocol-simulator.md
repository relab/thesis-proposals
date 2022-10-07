# Simulating Distributed Algorithms

## Administrative

- Supervisors: Nejm Saadallah and Hein Meling

## Prerequisites

- DAT530 Discrete Simulation and Performance Analysis.
- DAT520 Distributed systems.
- Golang.

## Project Description

Testing and analyzing distributed system algorithms is a challenging task. It is usually difficult to reproduce faulty situations or to ensure that a certain implementation will always produce the desired output. Model checking can in some cases be used to check the correctness of a distributed algorithm but that requires a representation of the system (often simplified) using a modelling language other than the language used for implementation. Examples are TLA+ and Petri nets.
In this thesis you will implement a distributed system simulator in the Golang. The simulator should be able to simulate the execution of a concurrent protocol using a sequential process. That is, the simulator should be able to run a distributed system in a single process with controlled steps (synchronized). This will make it possible to test possible execution paths of a given algorithm and store the state transitions in an appropriate data structure (e.g, tree) for further analysis. The implementation should ideally be compatible with Gorums to make it easier to switch between two modes real execution or simulation.

## Tasks / Milestones

- Get familiar with Gorums and implement a reference case. For example Paxos.
- Implement the simulator and compare its results with the reference implementation.
- Extend the simulator with state exploration capabilities represented in a process execution tree. The tree could consist of a number of state variables and their possible transition to  next states (transition system representation).

## Literature search

[1] Distributed Systems algorithms

[2] Golang

[3] Gorums with some examples

[4] Petri nets, TLA+
