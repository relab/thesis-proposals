# A Fair Selection Mechanism in Committee-based Blockchains

## Administrative

- Supervisor: Arian Baloochestani
- Responsible Professor: Leander Jehl

## Prerequisites

- Distributed systems (DAT520)
- Recommended to take DAT650 Blockchain technology concurrently

## Project Description

Committee-based blockchains are a popular varaient of blockchains in which a small group of processes are selected as the committee to decide over which block to append next to the chain.
In most committee-baased blockchains, first a leader is elected to propose a new block. 
Then, other committee members verify the proposed block and vote for it in case the block is valid. 
If the majority of the members vote for a proposed block, it is considered as approved. 

To incentivise the committee members we need a mechanism to reward them accordingly. 
Since only the committee members get rewarded, the committee selection algorithm needs to be fair, giving everyone a chance to get rewarded. 
The selection mechanism can be based on different things such as processes stakes (money they freeze before starting the protocol).

in [1] we  have designed different methods to reward and elect the leader to prevent some attacks. 
We evaluated the methods through simulations written in python.
The main task of the project is to design a fair selection mechanism for committe-based blockchains based on their past behaviour and you should extend the methods to additional methods for committee selection and extend the simulation framework to evaluate these methods. 


## Tasks / Milestones

- Reading relevant paper
- Extending the paper for committee selection
- Simulating the proposed algorithm in python or go
- Analyzing the results


## Reading Material
[1] Rebop: Reputation-based Incentives in Committee-based Blockchains (on demand)
