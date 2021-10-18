# Proving Redundancy In Decentralized Storage Networks

## Administrative

- Supervisors: Hein Meling and Racin Nygaard
- Group Composition: 1 or 2 master students

### Prerequisites

- Security and Vulnerability in Networks (DAT510)
- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Project Description

Decentralized storage system backed by blockchain technology are swiftly emerging.
The basis for these systems is to enable cheap, secure and reliable storage by having a network of peers pool their storage capacity together.
The peers are incentivized by token rewards on the blockchain.
However, as these peers are untrusted, it remains an open challenge to create a verifiable proof of which data they store.

The goal of this project, is to tackle this challenge by using Proof-of-Storage algorithms and implementing them in Swarm Bee.

By having a verifiable proofs of stored data, decentralized storage systems could see mainstream adoption as the system would be able to provide storage guarantees to end-users. This research is highly relevant, so successful implementations might see real-life adoptions.

In addition, this work will be relevant for Snarl, which is a novel component developed at the University of Stavanger that can be used by end-users to protect their data stored in Distributed Storage Systems.

### Proof-of-Storage

Proving data possession by retrieval is problematic both in terms of network bandwidth, and hard-drive I/O. Instead, we can generate probabilistic proofs of possession without accessing the entire file.

The basis of such a probabilistic proof is to have the verifier **V** store a constant amount of metadata which is kept secret from the prover **P** and used to generate probabilistic storage challenges **C**. A challenge-proof cycle start by having **V** generate a random challenge **C** and send it to **P**. Then **P** computes the proof and sends it back to **V**. Finally **V** verifies the proof. If the proof is invalid, **P** will be marked as faulty. Failure to respond will also result in being marked as faulty.

A few examples of Proof of Storage algorithms are given in the Reading Material section. The algorithms offer different properties in terms of performance, accuracy and metadata requirements. By using homomorphic encryption, it is even possible to gain the *public verifiability* property, which refers to the ability of anyone, not just the data owner, to take on the role as the verifier. This is highly interesting for storage system powered by a blockchain, as the metadata could be appended to the ledger to empower all users to verify storage.

### Tasks / Milestones

- Literature review of Proof of Storage algorithms
- Analyse different design alternatives and consider key features such as:
  - Public verifiability
  - Computation impact
  - Proof and challenge sizes
- Implement your best design in Swarm Bee
- Evaluate your implementation on our BBChain cluster
- Report on findings and lesson learned from the implementations
- Compare the new design with existing Proof of Storage algorithms
- Show how we can aggegate storage proofs to estimate the replication factor in the storage network

### Background on Distributed Storage Systems

A few videos to get an overview of the technology

- [Filecoin](https://www.youtube.com/watch?v=EClPAFPeXIQ)
- [Ethereum Swarm](https://www.youtube.com/watch?v=VgTZV471WFM)
- [Filecoin detailed](https://www.youtube.com/watch?v=P28aNAdZDi4)
  
### Reading Material

- [Proofs of Replicated Storage Without Timing Assumptions](https://eprint.iacr.org/2018/654.pdf)
- [Proof of Replication](https://filecoin.io/proof-of-replication.pdf)
- [Provable Data Possession at Untrusted Stores](https://eprint.iacr.org/2007/202.pdf)
- [Compact Proofs of Retrievability](https://eprint.iacr.org/2008/073.pdf)
- [PIEs: Public Incompressible Encodings for Decentralized Storage](https://eprint.iacr.org/2018/684.pdf)
- [Book of Swarm](https://www.ethswarm.org/The-Book-of-Swarm.pdf)
- [Swarm Whitepaper](https://www.ethswarm.org/swarm-whitepaper.pdf)
- [Snarl](##TODO)
