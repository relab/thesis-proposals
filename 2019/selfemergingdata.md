
# Smart Contracts for Self-emerging Data

### Supervisors: Leander Jehl

### Prerequisites:
- Students should have a good grade in network security (DAT510).

- Students should be eager to learn about both blockchain technology and to dive into a new programming language [2], but also interested in a more theoretical analysis and design of Smart Contracts.


### Background:

*Self-emerging data* allow users to publish
encrypted data and arrange for this data to be decrypted and made publicly
available at an arranged point in time without requiring additional actions of
the user.

*Possible applications* for self-emerging data are secure auction systems, where
bidding information needs to be protected until the end of the auction or secure
voting mechanisms, where votes need to be kept secret while the election is ongoing.

A promising solution for self-emerging data are Smart Contracts on a blockchain
platform like Ethereum. These contracts allow a user to setup for an external
agent to decode the data, or publish the key at a specific point in time [1].

The difficulty with such contracts is the possibility that an agent may fail to
publish the key, or that an agent could publish or access the file before the
agreed time for publication. To avoid this, contracts include mechanisms to pay
the agent and to punish misbehavior.


### Project Description:
The goal for this project is to design, implement and evaluate a
Smart Contract for self-emerging data on the Ethereum platform.
We want to investigate how the job of decryption can be distributed to multiple
agents, ensuring that several agents need to participate to decrypt the data.
Further, we want to investigate how coding techniques (e.g. erasure coding or
linear network coding) can be applied to ensure that the data is decoded even if
some agent fails to participate in the decoding.

Running such functionality on the Ethereum blockchain will consume Gas.
An experimental evaluation on an Ethereum test network may be used to evaluate
the cost of setup and execution of a contract about self-emerging data.

### Milestones
* Get familiar with the Solidity language used for Smart Contract on Ethereum
* Design and implement a Smart Contract for self-emerging data relying on multiple agents
* Test and evaluate the Contract on an Ethereum testbed
* Analyze the incentives and necessary rewards in the Smart Contract

### References

[1] [Self-emerging Data using Smart Contracts](http://www.sis.pitt.edu/bpalan/papers/SRDS2018.pdf)
a paper on implementing Self-emerging data using Smart Contracts on Ethereum

[2] [Solidity contract-oriented programming language](https://solidity.readthedocs.io/en/v0.4.25/#)

[3] [Getting started with Ethereum (video)](https://www.youtube.com/watch?v=F7Ehnt1ht_o&feature=youtu.be) see minute 45

[4] [Getting started with Solidity (video)](https://www.youtube.com/watch?v=rwfENZJT-i0)
