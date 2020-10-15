master
# Uncles and inclusion for sharding permissionless blockchains

### Supervisor: Leander Jehl

### Prerequisites:

- Blockchain technology (DAT650)

### Background

#### Sharding
Sharding is a promising step to increase the performance of permissionless blockchains. 
Sharding would allow nodes to not process every transaction and not maintain the complete state.

Besides technical questions like (i) how to distribute state among shards or (ii) how to execute transactions across shards,
the main security challenge for sharding is that an attacker, concentrating on a single shard may corrupt a majority of the nodes in that shard.

Existing solutions for this security challenge fall short, since they either 
1. encourage nodes to actually participate in all shards, thus countering the effect of sharding [Monoxide]. 
2. require strict assignment and frequent reshuffeling of nodes between shards [Omniledger].

#### Inclusive blockchains and uncles
Inclusiveness is a mechanism to counter centralization and creation of mining pools in permissionless blockchains.
The idea is that blocks on the blockchain may reference *uncles*, i.e. blocks on different forks than the main chain. Being included as uncles, these
blocks can also receive a slightly reduced block reward.

Scientific descriptions of inclusive protocolls allow transactions in uncle blocks to be executed. 
While not implemented in systems like Ethereum, this mechanism would allow uncles to contribute to performance of the blockchain.

### Project goal
The goal of this project is to investigate how uncles can be used to enable sharding of a blockchain.
The idea is that nodes running different shards should contribute to a common chain, similar to [Monoxide].
However a solution to a proof of work puzzle should only allow to publish a block in a single shard.
To increase throughput, blocks should be allowed to include one uncle for every shard.

The goal for this project is to further develop the above ideas and to validate them using simulations.
Simulations should be implemented and run in a simplified model, e.g. ignoring transaction fees and networking.

Simulations should try to answer the following questions:
1. Does Chu-ko-nu mining from [Monoxide] encourage nodes to actually participate in all shards?
2. Does mining in multiple shards increase expected reward in inclusive blockchains?
3. If difficulties are adjusted for different shards, do inclusive blockchains provide incentives to balance mining power in shards?

### Resources
[Monoxide](https://www.usenix.org/conference/nsdi19/presentation/wang-jiaping)
[Inclusiveness](https://fc15.ifca.ai/preproceedings/paper_101.pdf)
[Inclusiveness for throughput](https://arxiv.org/pdf/1805.03870.pdf)
[Omniledger](https://blog.acolyer.org/2018/02/09/omniledger-a-secure-scale-out-decentralized-ledger-via-sharding/)




