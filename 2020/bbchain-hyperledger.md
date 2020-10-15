# Evaluate Hyperledger's Chaincode Smart Contracts for BBChain

## Supervision: Hein Meling (w/ Rodrigo Saramago)

## Prerequisites

- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills
- Knowledge of Docker or Kubernetes

## Project Description

The goal of this project is to implement smart contracts for a document verification system using Chaincode on the Hyperledger blockchain. This project is offered as part of the BBChain research project, in which we have started to develop a similar set of smart contracts for the Ethereum blockchain.

## Tasks / Milestones

- Identify the differences between Hyperledger's Chaincode and smart contracts in the Ethereum architecture in the context of the document verification system;
- Investigate the limitations of both platforms and what consensus algorithms and consistency models are currently supported by them;
- Configure and deploy the Hyperledger blockchain environment following the current documentation [1];
- Develop Chaincode [2] for issuing and verifying academic documents;
- Adapt our current model of academic procedures (admission process, student grade registration, etc.) using Chaincode;
- Report on findings from the implementation, concluding on the feasibility of the developed application for the BBChain scenario.
- Benchmark the implementation using simulated workloads and compare results with Solidity implementation.

## Background on BBChain

Today certified documents are mostly based on paper and the verification process is expensive, time-consuming, and prone to human error and fraud [4]. Besides that, the current digital solutions that make use of digital signatures require third-party central authority and impose many limitations for use on a global scale. Some of these limitations are:

- Bureaucracy;
- Lack of interoperability and trust between issuers and verifiers;
- Centralization of information on third party companies;

Academic document verification procedure consists of the process, e.g., collecting, analyzing and verifying academic documents provided by a student, such as their diploma, transcript of records or any kind of academic degree certificate [5].

Institutions often require a copy of such documents as proof of qualification to attest the proficiency of the student. Thus, the authenticity of these documents need to be verified. Usually this is done by a certification authority (e.g., university administration department, notary office) through handwritten or digital signatures, stamps and watermarks.

The verification process checks that the document provided is legitimate and was issued by the correspondent institution for that student, and ensures that it was not tampered or forged.

Our BBChain project aims to build a global and public database of digitally authenticated documents, reducing the complexity and costs of the procedures for issuing and verifying academic degree certificates, while improving the trust and privacy between all involved parties. 

## Reading Material

- [1] [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html)
- [2] [Hyperledger Chaincode Docs](https://hyperledger-fabric.readthedocs.io/en/latest/chaincode.html)
- [3] [Ethereum Project](https://github.com/ethereum/go-ethereum)
- [4] [World Economic Forum](http://www3.weforum.org/docs/WEF_The_Known_Traveller_Digital_Identity_Concept.pdf)
- [5] [Verifiable Claims for Educational Systems](https://www.w3.org/TR/verifiable-claims-use-cases/#education)
