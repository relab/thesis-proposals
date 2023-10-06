# Swarm storage incentives, a new smart contract

## Administrative

- Supervisor: Leander Jehl and Vahid Heidaripour Lakhani

## Prerequisites

- DAT650 Blockchain Technology

## Background

Decentralized storage networks have developed over the past two decades with the idea of being an alternative to centralized data silos. 
This idea solves current problems like the **single point of failure** and possible **censorship** differently. There is no single node in the network that keeps all the data, and data is distributed all over the network. 
The Swarm storage network is one such system that tries to offer decentralized storage capacity to users. In Swarm, nodes share 
their storage capacity with others, store their data (in the form of small chunks with 4KB size), and receive a reward for it. 
The financial incentive is the primary motivation to encourage peers to participate in the network, 
and it is expected to prevent free-riding.

In the current Swarm version, nodes storing the same content make a neighborhood. 
In each round (approximately 15 minutes), a neighborhood is picked at random, and honest nodes in that neighborhood storing 
the correct chunks have the chance to win the reward proportional to their stake. 

## Project Description

The staking nodes' distribution is not uniform. 
There is one neighborhood with 14 nodes and 5 neighborhoods with only 2 nodes (at the moment of writing this). 
Swarm storage documentation states that this is not good and may result in a situation where chunks are not retrievable. 
Is it possible to make this distribution uniform using the power of 2 choices algorithm? 
Does it shift the overall fairness in reward distribution in the network?
Currently, after choosing a random anchor and, consequently, a random neighborhood, 
an honest node in that neighborhood wins the reward for that round proportional to its stake. 
Isn’t it a fairer approach to distribute the reward proportionate to stakes between all honest 
nodes in that neighborhood? Or a level before that one when choosing a random neighborhood, 
it can be chosen with considering all stakes in all neighborhoods. 

Consequently, making these changes to the system will significantly change the smart contracts in use, 
specifically in terms of cost and complexity.

This project aims to implement a smart contract considering all the above questions.

## Tasks / Milestones

- Understand the current storage incentive of the Swarm storage network using the reading materials
- Implement the new smart contract 
- Explain the observations with the new smart contract

## Reading Material
[1] [Future-proof Storage; economic incentives for sharing storage capacity to achieve data persistance in the Swarm peer to peer network](https://www.overleaf.com/project/6173a105d96be57785c743e0)

[2] [Swarm Specification](https://www.overleaf.com/project/64a8d9af0110a0b0d22b7a81)

[3] [Bee repository](https://github.com/ethersphere/bee)

[4] [Storage incentives: The missing piece to make blockchains complete](https://www.youtube.com/watch?v=OH18D_PKo9U)

[5] [Storage incentives — when, what, and how. An EthBerlin meetup recap](https://www.reddit.com/r/ethswarm/comments/xruv51/storage_incentives_when_what_and_how_an_ethberlin/)

[6] [The power of two choices - Petar Maymounkov](https://www.youtube.com/watch?v=0dKz_K-7eoI)



