# BBChain Application for Academic Institutions

## Administrative

- Supervisor: Hein Meling and Rodrigo Saramago

## Prerequisites

- DAT520 Distributed Systems
- DAT650 Blockchain Technology
- Proficient in the Go programming language

## Project Description

The BBChain project has modeled some of the procedures of academic institutions in the form of smart contracts on the [Ethereum platform](https://github.com/ethereum/go-ethereum).
The goal of this project is to extend our current models with support for automated admission with provable ranking, grade registration and more.
Further, these models (smart contracts) must be made accessible via a web frontend or a mobile application via secure communication.
In particular, support could be added to Quickfeed (formerly Autograder), to automate or simplify the grade registration process.

## Tasks / Milestones

- Study existing literature on academic credential management on blockchains
- Study the current procedures of academic institutions
- Identify procedures that can be automated by smart contracts
- Example procedure: automated admission with provable ranking from existing blockchain issued diplomas
- Identify procedures whose security properties can be strengthened by smart contracts
- Implement the relevant smart contracts on the Ethereum platform
- Design and implement a web frontend or mobile application to access these procedures
- Evaluate the cost of executing the relevant procedures as smart contracts
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

- To be added
- Rodrigo's draft paper
