# BBChain Custom Blockchain for Academic Credentials

## Administrative

- Supervisor: Hein Meling, Leander Jehl and Rodrigo Saramago

## Prerequisites

- DAT520 Distributed Systems
- DAT650 Blockchain Technology
- Proficient in the Go programming language

## Project Description

The BBChain project has modeled some of the procedures of academic institutions in the form of smart contracts on the [Ethereum platform](https://github.com/ethereum/go-ethereum).
The goal of this project is to implement a custom blockchain for academic credentials based on state machine replication via the Gorums/HotStuff protocol.

## Tasks / Milestones

- Study existing literature on RSM-based blockchains (see linked references below)
- Implement a permissioned blockchain based on Gorums/HotStuff
- Identify academic procedures that can be implemented in the context of such a blockchain, e.g. inspired by Rodrigo's work
- Example procedure: automated admission with provable ranking from existing blockchain issued diplomas
- Implement the relevant academic procedures on blockchain platform
- Implement a client application to test the procedures
- Evaluate the cost of executing the relevant procedures on the blockchain
- Evaluate the performance of the blockchain and compare with other similar blockchain architectures
- Report on findings and lessons learned from the implementation, concluding on the feasibility of the developed application for the BBChain scenario

## Background on BBChain

Today certified documents are mostly based on paper and the verification process is expensive, time-consuming, and prone to human error and fraud (see [World Economic Forum](http://www3.weforum.org/docs/WEF_The_Known_Traveller_Digital_Identity_Concept.pdf)).
Besides that, the current digital solutions that make use of digital signatures require third-party central authority and impose many limitations for use on a global scale.
Some of these limitations are:

- Bureaucracy;
- Lack of interoperability and trust between issuers and verifiers;
- Centralization of information on third party companies;

Academic document verification procedure consists of the process, e.g., collecting, analyzing and verifying academic documents provided by a student, such as their diploma, transcript of records or any kind of academic degree certificate (see [Verifiable Claims for Educational Systems](https://www.w3.org/TR/verifiable-claims-use-cases/#education)).

Institutions often require a copy of such documents as proof of qualification to attest the proficiency of the student.
Thus, the authenticity of these documents need to be verified. Usually this is done by a certification authority (e.g., university administration department, notary office) through handwritten or digital signatures, stamps and watermarks.

The verification process checks that the document provided is legitimate and was issued by the correspondent institution for that student, and ensures that it was not tampered with or forged.

Our BBChain project aims to build a global and public database of digitally authenticated documents, reducing the complexity and costs of the procedures for issuing and verifying academic degree certificates, while improving the trust and privacy between all involved parties.

## Reading Material

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums source code](https://github.com/relab/gorums)
- [Gorums/HotStuff source code](https://github.com/relab/hotstuff)
- [HotStuff paper](https://arxiv.org/pdf/1803.05069.pdf)
- [HotStuff thesis](https://www.dropbox.com/s/n3no6zvsbrugf28/hotstuff-thesis.pdf?dl=0)
- [SmartCoin](https://www.inf.usi.ch/faculty/pedone/Paper/2020/2020DSNb.pdf)
- [Bloxy](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9049615)
- Rodrigo's draft paper
