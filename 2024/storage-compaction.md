# Storage Compaction for Append-only Ledgers

## Administrative

- Supervisor: Hein Meling
- Co-supervisors: Natacha Crooks and Suyash Gupta (University of California, Berkeley)

### Prerequisites

- Distributed systems (DAT520)
- Security and Vulnerability in Networks (DAT510)
- Blockchain Technologies (DAT650)
- Go programming language
- Excellent programming skills

### Motivation

The following is copied (and slightly edited) from the [Samurai][1] poster paper for your convenience:

Decentralized systems promise an immutable, append-only ledger that can be queried for transaction data.
Yet, current approaches fail to offer clients an efficient mechanism for retrieving information about past transactions.
These systems adopt solutions that must make sacrifices, be it in terms of storage, performance, or decentralization.
Most decentralized systems follow a similar architecture in which a set of distrustful parties form a replicated state machine.
These parties run a Byzantine fault-tolerant consensus protocol to order blocks (batches) of client transactions.
After ordering, the parties make the Merkle root publicly available as proof that the block was ordered.
The root of the Merkle tree is constructed from the transactions in the block.
If a client sends a query to determine if its transaction is in a specific block, these systems adopt the following approaches:
Sacrifice Storage, Sacrifice Performance, or Sacrifice Decentralization.

### Project Description

In the Samurai project, the goal is to develop a decentralized system that offers clients an efficient mechanism for retrieving information about past transactions, without sacrificing storage, performance, or decentralization.
Realizing that an append-only ledger, commonly used in blockchain systems, is going to grow indefinitely, there is an urgent need to develop techniques for compacting the storage of such ledgers.

To that end, we are currently developing a prototype of [Samurai][1] as a Go library, and integrating it with Ethereum's Geth client.
In this sub-project, the goal is to integrate Samurai's storage compaction techniques for another blockchain system (see section below for a list of possible blockchain systems).
The main goal of this sub-project is to validate that Samurai's API design is suitable for other blockchain systems.
The secondary goal is to evaluate the performance of Samurai on the other blockchain system, and compare Samurai's performance on Geth.

### Tasks / Milestones

- Literature review of storage compaction techniques (for blockchains)
  - Write background section discussing the state of the art
- Review the code for blockchain X
  - Understand the storage architecture and transaction query interface
- Implement a client application to exercise the transaction query interface
  - Evaluate blockchain X's performance (for transaction querying)
  - Obtain performance metrics similar to those reported in the Samurai poster paper
  - (You may need to extend blockchain X's implementation to support the transaction query interface)
- Implement Samurai's storage compaction techniques for blockchain X
  - Analyze and discuss Samurai's API design for suitability for blockchain X
- Evaluate the performance of Samurai on blockchain X
  - Compare the performance of Samurai on blockchain X and Geth
- Report on findings and lesson learned from the implementations

### Reading Material

- [Samurai: Slash your Decentralized Storage][1]
- More will be added...

[1]: https://github.com/relab/thesis-proposals/2024/samurai-poster.pdf

### Possible Blockchain Implementations to use

I'm looking for something relatively stable and robust with good documentation to give the student(s) a good experience...
Here is a list of the ones I can think of that are implemented in Go:

- Bitcoin: <https://github.com/btcsuite/btcd>
- Cosmos: <https://cosmos.network/>
- GnoLand: <https://gno.land/>
- ChainLink: <https://chain.link/>  <https://github.com/smartcontractkit/chainlink>
- Avalanche: <https://www.avax.network/>
- HotStuff: <https://github.com/relab/hotstuff>
  This would probably require a lot more work than some others since I think our blockchain application is missing features we probably want for this project...
- Algorand: (only if there aren't any better options, because ... )

Rust alternatives:

- Supra
- Aptos
- Mysten Labs
- Solana
