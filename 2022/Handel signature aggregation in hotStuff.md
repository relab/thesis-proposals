# Implementing Handel signature aggregation in HotStuff

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

The blockchain that was first introduced as an infrastructure for Bitcoin Cryptocurrency in 2008 has been one of the most appealing technologies in recent years. The fundamental element of each blockchain is its underlying consensus protocol. There are various consensus protocols such as Proof-of-Work and Proof-of-Stake. Due to the limitations of these approaches, such as high energy consumption, some blockchains adopt a Byzantine fault-tolerant protocol as their consensus algorithm. HotStuff is one of these blockchains which provides interesting features. In HotStuff, a leader is selected and proposes new blocks. The other processes have to vote for the new blocks. The leader has to aggregate the voters' signatures as proof.    

The main task of this project is to implement HotStuff on top of a new signature aggregation scheme called Handel. Some implementations exist for Handel and HotStuff, and the challenge is to connect these. The preferred programming language for implementation is Golang. 

## Tasks / Milestones

 - Study HotStuff and its implementation
 - Study Handel and its implementation
 - Implement HotStuff in top of Handel

 ## Background

 A few videos regarding HotStuff and Handel:

 - [HotStuff](https://www.youtube.com/watch?v=GAGW-c4hADA)
 - [Handel](https://www.youtube.com/watch?v=cmX8Fmbh9Yc)

 ## Reading Material

 - [HotStuff paper](https://dl.acm.org/doi/pdf/10.1145/3293611.3331591)
 - [Handel](https://arxiv.org/pdf/1906.05132.pdf)
