# Designing a simulation platform for Tangle 2

## Administrative

- Supervisor: Leander Jehl and Arian Baloochestani

## Prerequisites

- DAT520 Distributed systems
- DAT650 Blockchain technology (Recommended)

## Project Description

Tangle is the underlying technology for IOTA, one of the most popular cryptocurrencies used for IoT devices. 
Unlike blockchains, Tangle provides consensus based on a directed acyclic graph (DAG). 
In the first version of Tangle, each node that issues a transaction needs to verify and approve two other transactions. 
Then, if a transaction proved to be invalid, the transactions approving that transaction were also discarded. 
In tangle 2, the authors made changes to the initial protocol to tackle the mentioned problem.

The project's main task is to design a simulation platform for tangle 2.
You will need to read and understand the Tangle 2 paper, and then design simulations to verify the claims of the paper. 
The simulations should be high-level, so you won't need to actually implement the whole protocol. 
It is recommended to use either python or golang. 


## Tasks / Milestones

- Reading tangle 2 paper
- Designing simulations for the paper
- Implementing the simulation platform in python or go
- Analyzing the results and verifying the paper's claims


## Reading Material
[1] [Tangle 2.0: Leaderless Nakamoto Consensus on the Heaviest DAG](https://arxiv.org/pdf/2205.02177.pdf)
