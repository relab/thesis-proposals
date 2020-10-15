# Performance Efficient Proof of Storage

### Supervisors: Hein Meling, Leander Jehl and Racin Nygaard

### Prerequisites: 
- Security and Vulnerability in Networks (DAT510)
- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Project Description: 

Ensuring permanent availability of data over long periods of time is problematic as data loss and data corruption may happen due to management errors or hardware failure, which could go undetected, until the data is accessed. This is a major challenge, as large amounts of data may rarely, if ever, be accessed. Proving data possession by retrieval is problematic both in terms of network bandwidth, and hard-drive I/O. Instead, we can generate probabilistic proofs of possession without accessing the entire file. One of the design goals is that it should be computationally cheap to both issue challenges, and to prove them.

The basis of such a probabilistic proof is to have the verifier **V** store a constant amount of metadata which is kept secret from the prover **P** and used to generate probabilistic storage challenges **C**. A challenge-proof cycle start by having **V** generate a random challenge **C** and send it to **P**. Then **P** computes the proof and sends it back to **V**. Finally **V** verifies the proof. If the proof is invalid, **P** will be marked as faulty. Failure to respond will also result in being marked as faulty.

Proof of Storage algorithms are a key component of blockchain based distributed storage systems where the ledger nodes maintaining the blockchain is separated from the storage nodes maintaining the payload data. The separation allows the storage nodes to be operated by multiple distinct entities. The blockchain is used to form verifiable storage contracts between clients and storage providers, specifying what should be stored, and when data can be deleted. In order to verify availability and increase confidence in the system, we require the storage nodes to publish proofs of storage to the blockchain.

The goal of this project is to analyze existing Proof of Storage algorithms, and to design one that is suitable for a blockchain storage system. A key property of a suitable algorithm is that it should have a low performance impact, allowing challenges to be issued frequently.

A few examples of Proof of Storage algorithms are given in the Reading Material section. The algorithms offer different properties in terms of performance, accuracy and metadata requirements. By using homomorphic encryption, it is even possible to gain the *public verifiability* property, which refers to the ability of anyone, not just the data owner, to take on the role as the verifier. This is highly interesting for storage system built on a blockchain, as the metadata could be appended to the ledger to empower all users verify storage.

A successful project may be incorporated into the blockchain storage system.

### Tasks / Milestones: 

- Analyse different design alternatives.
- Implement three Proof of Storage algorithms with different properties in Go.
	1. Provable Data Possession (Without Public Verifiability)
	2. Compact Proofs of Retrievability
	3. Public Incompressible Encodings
- Evaulate the implementations.
- Use knowledge gained to design and implement a Proof of Storage algorithm suitable for a storage system built on a blockchain.
- Evalute the new implementation.
- Compare the new design with existing Proof of Storage algorithms.

### Reading Material: 

- [Proof of Replication](https://filecoin.io/proof-of-replication.pdf)
- [Provable Data Possession at Untrusted Stores](https://eprint.iacr.org/2007/202.pdf)
- [Compact Proofs of Retrievability](https://eprint.iacr.org/2008/073.pdf)
- [PIEs: Public Incompressible Encodings for Decentralized Storage](https://eprint.iacr.org/2018/684.pdf)
