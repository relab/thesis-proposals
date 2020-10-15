# Implementing a Distributed Key-value Store Using the Corums Framework

## Supervisor: Hein Meling (w/ Thomas Stidsborg Sylvest)

## Prerequisites 

- Distributed systems (DAT520)
- Excellent knowledge of C# and programming skills 

## Project Description

The goal of this project is to implement a distributed highly available key value store with strong consistency guarantees using the Corums framework. Such systems are built using a consensus algorithm algorithm, e.g. Raft or Multi-Paxos at their core. The student is free to choose an algorithm in cooperation with the supervisors.

Corums is an artifact of the current research, into simplifying implementation of consensus algorithms, conducted by the research group headed by Hein Meling. Corums is a .NET framework specifically designed for this purpose. This means that the key value store must be implemented in C#.

The project provides the opportunity for the student to dig into and understand how enterprise systems such as Cassandra and distributed databases functions at a low level. Thereby, providing the student with invaluable knowledge before pursuing be it a professional or academic career afterwards. Furthermore, the project is very much open for the ambitious student. 

## Tasks / Milestones

- Understand a chosen consensus algorithm
- Understand the Corums framework
- Decide and design the overall system architecture
- Implement the system iteratively

## Reading material

### Consensus algorithms - at least one of

- [Raft](https://raft.github.io/)
- [Paxos](https://lamport.azurewebsites.net/pubs/paxos-simple.pdf)
- [Viewstamped Replication](http://pmg.csail.mit.edu/papers/vr-revisited.pdf)

### Event-driven programming

- Chapter 33 of http://pages.cs.wisc.edu/~remzi/OSTEP/
