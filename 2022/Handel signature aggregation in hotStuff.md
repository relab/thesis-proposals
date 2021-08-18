# Implementing Different signature aggregations in HotStuff

## Administrative 

- Supervisor: Arian Baloochestani
- Responsible Professor: Leander Jehl

## Prerequisites

 - DAT650 Blockchains

## Learning Outcomes

- become familiar with blockchains
- become familiar with HotStuff
- become familiar with signatures aggregations such as Handel

## Project Description

Blockchains have been one of the most appealing technologies in recent years. The fundamental element of each blockchain is its underlying consensus protocol. There are various consensus protocols such as Proof-of-Work and Proof-of-Stake. Due to the limitations of these approaches, such as high energy consumption, some blockchains adopt a Byzantine fault-tolerant protocol as their consensus algorithm. HotStuff is one of these blockchains which provides interesting features. In HotStuff, a leader is selected and proposes new blocks. The other processes have to vote for the new blocks. The leader has to aggregate the voters' signatures as proof. 

Recent works at UiS have implemented the HotStuff protocol in Golang. The current implementation supports BLS signatures and also ECDSA signatures. The implementation can be found in [here](https://github.com/relab/hotstuff/). The main task of this project is to implement new signature aggregation schemes such as Handel in the current implementation for HotStuff and evaluate the impact of these mechanisms on the security and performance of the system. 

## Tasks / Milestones

 - Study HotStuff paper carefully and understand the parts of its implementation that are needed for this project, e.g., [the crypto module](https://github.com/relab/hotstuff/tree/master/crypto) could be a starting point.
 - Study different signature aggregation mechanisms such as Handel, and learn how to work with their libraries in Golang.
 - Implement some of the signature aggregations in the HotStuff.

 ## Background

 A few videos regarding HotStuff and Handel:

 - [HotStuff](https://www.youtube.com/watch?v=GAGW-c4hADA)
 - [Handel](https://www.youtube.com/watch?v=cmX8Fmbh9Yc)

 ## Reading Material

 - [HotStuff paper](https://dl.acm.org/doi/pdf/10.1145/3293611.3331591)
 - [Handel](https://arxiv.org/pdf/1906.05132.pdf)
