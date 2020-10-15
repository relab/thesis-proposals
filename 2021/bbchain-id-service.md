# BBChain Identity Service

## Administrative

- Supervisor: Hein Meling and Rodrigo Saramago

## Prerequisites

- DAT520 Distributed Systems
- DAT650 Blockchain Technology
- Proficient in the Go programming language

## Project Description

The BBChain project has modeled some of the procedures of academic institutions in the form of smart contracts on the [Ethereum platform](https://github.com/ethereum/go-ethereum).
The goal of this project is to study biometric methodologies that can be used by the BBChain project in order to create a link between the users' biometric traits and their cryptographic signing keys.
Currently, only the public key of an user is used by the BBChain project to establish a link between the users' academic credential and his pseudo-identity.

Further, users should be able to authenticate by exchanging the identity information with other devices using an encrypted peer-to-peer channel.
The identity information (represented by a DID) should be verified through an identity provider (e.g. University).

## Tasks / Milestones

* Study existing literature on privacy-preserving biometric authentication.
* Study existing literature on Decentralized Identifiers (i.e. DID).
* Study existing literature on secure key exchange protocols and peer-to-peer networks.
* Design and implement an biometric-based identification service that can be incorporated to the bbchain project. The implemented system should, among other things:
    - extract biometric traits and create the users' DID based on the extracted data.
    - allow users to securely exchange identity data in a peer-to-peer basis.
    - allow users to authenticate academic credentials using their DIDs and a biometric samples.
    - provide an RPC API that expose the system functionalities for easy integration with BBChain.
    - store the identity data encrypted in a configurable storage (users' device and Swarm network)
* Identify procedures whose security properties can be strengthened by the biometric link.
* Report on findings and lessons learned from the implementation, concluding on the feasibility of the developed application for the BBChain scenario

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

- [DID](https://github.com/w3c/did-core)
- [openbr](https://github.com/biometrics/openbr)
- [Fuzzy signatures](https://www.researchgate.net/publication/303860396_Fuzzy_Signatures_Relaxing_Requirements_and_a_New_Construction)
- [Fuzzy identity based signature](https://doi.org/10.1016/j.compeleceng.2011.04.013)
- [Double Ratchet key exchange algorithm](https://signal.org/docs/specifications/doubleratchet/#introduction)
- [X3DH key agreement protocol](https://signal.org/docs/specifications/x3dh)
- [Swarm](https://swarm.ethereum.org/)
- Rodrigo's draft paper
