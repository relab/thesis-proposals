# Implementation of the Narwhal mempool

## Administrative

- Supervisor: Hanish Gogada, Hein Meling, Leander Jehl

## Prerequisites

- DAT530 Distributed systems

## Project Description

BFT protocols are adopted by the BlockChains, but their lack of scalability is a challange.
Relab group at UiS has built a framework to develop and evaluate new Byzantine Fault tolerant protocols and it has been used by other research teams.
This project aims to add Narwhal, a DAG-based mempool protocol to the existing framework
.Narwhal mempool helps the traditional BFT protocols, separate the dissemination and ordering transactions in blockchains for high performance. 

## Tasks

- Reading Narwhal[1], HotStuff[2], BullShark[3] papers.
- Design and implement Narwhal mempool on existing framework.
- Evaluate the benefits of Narwhal mempool with different configurations.
- Analyze and verify the claims of the Narwhal-Hotstuff protocol.

## Reading materials
[1] [Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus](https://arxiv.org/pdf/2105.11827.pdf)
[2] [Yin, Maofan, et al. "Hotstuff: Bft consensus with linearity and responsiveness.](https://dl.acm.org/doi/pdf/10.1145/3293611.3331591)
[3] [Bullshark: DAG BFT Protocols Made Practical](https://arxiv.org/abs/2201.05677)
