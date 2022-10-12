# A Fair Selection Mechanism in Committee-based Blockchains

## Administrative

- Supervisor: Leander Jehl and Arian Baloochestani

## Prerequisites

- Python/Go programming

## Project Description

Committee-based blockchains are a popular type of blockchain in which a small group of processes is selected as the committee to decide over which block to append next to the chain. 
In most committee-based blockchains, first, a leader is elected to propose a new block. 
Then, other committee members verify the proposed block and vote for it in case the block is valid. 
If the majority of the members vote for a proposed block, it is considered approved.

To incentivize the committee members, we need a mechanism to reward them accordingly. 
Since only the committee members get rewarded, the committee selection algorithm needs to be fair, giving everyone a chance to get rewarded. 
The selection mechanism can be based on different things, such as process stakes (money they freeze before starting the protocol), or reputation.

In [1], we have designed different methods to reward and elect the leader to prevent some attacks. 
We evaluated the methods through simulations written in python. 
The project's main task is to design a fair selection mechanism for committee-based blockchains based on their past behavior. 
You should extend the simulation framework to evaluate other methods.


## Tasks / Milestones

- Reading relevant paper (Rebop)
- Extending the simulations for committee selection 
- Running the simulation and get proper outputs (charts, graphs, etc)
- Analyzing the results


## Reading Material
[1] Rebop: Reputation-based Incentives in Committee-based Blockchains
