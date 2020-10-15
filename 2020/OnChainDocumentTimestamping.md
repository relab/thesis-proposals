master?
# Batching for document timestamping on Ethereum

### Supervisor: Leander Jehl

### Prerequisites:

- Blockchain technology (DAT650) ?

### Project Description
[Linked Timestamping](https://en.wikipedia.org/wiki/Linked_timestamping) is a fundamental building block for modern blockchain technology.
The original timestamping schemes rely on "blocks" published in dayly newspapers.
The goal for this project is to investigate timestamping schemes utilizing the Ethereum blockchain.

A baseline scheme would store document hashes, their associated timestamp and issuer addresses in the contract (on chain).
This scheme allows to retrieve a documents timestamp using a view function, however, it causes linear storage overhead.
Contract storage on ethereum is very expensive.
The idea for this project is to investigate mechanisms to reduce the storage overhead and thereby the execution (gas) cost.
The project should evaluate the following ideas:
1. Batching documents off chain and only publishing their merkle root.
2. Batching documents on chain and only storing their merkle root.
3. Batching the complete history of documents and only storing a single merkle root.

In all cases, the smart contract should ensure that documents are batched correctly.
Further, it should be considered how inclusion proofs can be distributed and maintained by the different document holders.
The project could also investigate systems like Swarm or IPFS for storage of documents and inclusion proofs.
