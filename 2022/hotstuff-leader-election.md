# Implementing Different Leader Elections in HotStuff

## Administrative 

- Supervisor: Arian Baloochestani
- Responsible Professor: Hein Meling

## Prerequisites

 - DAT530 Distributed systems
 - Experience with Golang
 - Recommended to take DAT650 Blockchain technology concurrently 

## Learning Outcomes

- become familiar with blockchains
- become familiar with HotStuff
- become familiar with leader elections

## Project Description

Blockchains have been one of the most appealing technologies in recent years. The fundamental element of each blockchain is its underlying consensus protocol. There are various consensus protocols such as Proof-of-Work and Proof-of-Stake. Due to the limitations of these approaches, such as high energy consumption, some blockchains adopt a Byzantine fault-tolerant protocol as their consensus algorithm. HotStuff is one of these blockchains which provides interesting features. In HotStuff, a leader is selected and proposes new blocks. The other processes have to vote for the new blocks. The leader has to aggregate the voters' signatures as proof.

Recent works at UiS have implemented the HotStuff protocol in Golang. The current implementation supports only round-robin leader election. The implementation can be found in [here](https://github.com/relab/hotstuff/). The main task of this project is to implement new leader election schemes such as random-based leader elections in which leaders are elected randomly (based on some properties such as reputation) in the current implementation for HotStuff and evaluate the impact of these mechanisms on the security and performance of the system. 

## Tasks / Milestones

 - Study HotStuff paper carefully and understand the parts of its implementation that are needed for this project.
 - Study different leader election mechanisms.
 - Implement rewarding scheme to give rewards to voters.
 - Implement random leader election.
 - Implement reputation and reputation-based leader election.

## Evaulation

- The outcome of this project is measuring the impact of different leader elections in HotStuff implementation. We expect to analyze security and performance of HotStuff with these different mechanisms and have a comparison. 

 ## Background

 A few videos regarding HotStuff:

 - [HotStuff](https://www.youtube.com/watch?v=GAGW-c4hADA)

 ## Reading Material

 - [HotStuff paper](https://dl.acm.org/doi/pdf/10.1145/3293611.3331591)
