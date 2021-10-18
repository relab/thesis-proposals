# Revised Concurrency Architecture for Snarl

## Administrative

- Supervisors: Hein Meling and Racin Nygaard
- Group Composition: 1 or 2 master students

### Prerequisites

- Concurrent programming with Go (e.g., DAT320)
- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills
- Optional: background in formal methods

### Project Description

Snarl is a novel component for improving the file availability in decentralized storage systems, such as [IPFS](https://ipfs.io/) and Swarm.
Snarl was developed at the University of Stavanger and can be used by end-users to protect their data stored in Swarm or IPFS.

To achieve its goal of high file availability, Snarl uses a sophisticated repair algorithm that requires that several goroutines communicate to exchange their state.
However, the current concurrency architecture has evolved in an ad hoc manner, and is non-trivial to understand, maintain and to prove correct.

The goal in this project is to design a new concurrency architecture for Snarl that is both scalable and provably correct.
Snarl builds on a lattice data structure, in which each element connects to a set of other elements.
These elements represents data chunks in the storage system, and the edges between the elements represent redundancy chunks.
To repair missing data chunks, Snarl traverses the lattice to find redundancy chunks that can help to repair data chunks.

The primary goal is to design the concurrency architecture for the repair algorithm over the lattice data structure.
The secondary goal is to integrate the lattice-based repair algorithm with Snarl's Merkle tree structure to allow for efficient lookup.

### Tasks / Milestones

- Review literature about concurrency patterns and concurrency algorithms
- Analyse the existing concurrency architecture
- Implement one or more designs in Go
  - Multiple implementations should be considered
- Evaluate and benchmark your designs
- Argue for the correctness of your designs
- Report on findings and lesson learned from the implementations
- Compare the new design with the existing implementation
- OPTIONAL if two students: Formal verification
  - Prove that your designs are correct/equivalent
  - Prove design is correct using a formal verification tool (TLA+, Ivy, or Spin)
  - Formal verification requires a solid foundation in discrete mathematics

### Background on Distributed Storage Systems

A few videos to get an overview of the technology

- [Filecoin](https://www.youtube.com/watch?v=EClPAFPeXIQ)
- [Ethereum Swarm](https://www.youtube.com/watch?v=VgTZV471WFM)
- [Filecoin detailed](https://www.youtube.com/watch?v=P28aNAdZDi4)
  
### Reading Material

- [Book of Swarm](https://www.ethswarm.org/The-Book-of-Swarm.pdf)
- [Swarm Whitepaper](https://www.ethswarm.org/swarm-whitepaper.pdf)
- [Snarl](##TODO)
