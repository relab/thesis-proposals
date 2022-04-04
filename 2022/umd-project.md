# Verifiable Credentials and Trustworthy Admissions Process

Draft of possible UMD Credence student project.

## Background for the BBChain Project

Today certified documents are mostly based on paper and the verification process is expensive, time-consuming, and prone to human error and fraud (see [World Economic Forum](http://www3.weforum.org/docs/WEF_The_Known_Traveller_Digital_Identity_Concept.pdf)).

The BBChain project aims to build a global and public database of digitally authenticated documents, reducing the complexity and costs of the procedures for issuing and verifying academic degree certificates, while improving the trust and privacy between all involved parties.

## Our Research so far

### Verifiable Diplomas with Issuer Transparency

In previous work we have designed a protocol and prototype of a system for verifiable academic credentials. In this system we record each student's (protected) grades in a blockchain-based structure suitable for integrity verification by parties authorized by the student. Further, the recording allows verifiers to check that the final degree comprises a set of grades and that these were time-locked onto the blockchain over the expected study period. The data recorded on the blockchain is a hash of the grade data.

Each grade is recorded by one or more authorized "exam" evaluators and cannot later be tampered with, even by other officials. Typically, each course of a study program is graded by different evaluators, and thus the overall trust in a diploma certificate is distributed among many different evaluators.

The paper describing this part is available [here](https://arxiv.org/pdf/2109.11590.pdf). The paper includes links to open source codebase with our prototype.

*Side note*: In the Norwegian system, typically one or two evaluators are used. With two evaluators, a consensus should be reached offline before recording the agreed-upon grade. Additionally, students can appeal the grade, in which case a new evaluation committee is appointed and a new final grade is recorded.

### Ranking Applicants

In ongoing project, we are designing a trustworthy admissions system, which would allow applicants to a study program to receive a fair ranking without having to trust the server running the admission software. That is, when applicants submit their applications to some college using our scheme, the applicant would be able to verify that their application was included in the ranking and that the ranking was fairly computed by the admission system of the college.

There is a paper in progress in early stages and there is a codebase with our prototype also being developed, currently not open sourced.

*Side note:* In Norway, a centralized national system has been developed to accept applications from students applying to higher education. Acceptance is based on their grade points, which is submitted electronically by high schools on behalf of students. This works fairly well, and most people trust the system. However, the system itself is designed using traditional technology and does not offer the same guarantees as our prototype will.

## Project Description

In this project, we would like to better understand the socio-technical aspects of deploying such a system to universities in the USA. Specifically, we are interested in existing processes at US universities and how our design fits these systems. Further, we would like to explore user interface designs suitable for the various expected interactions with such a system. An important aspect is to understand the trust requirements being placed on officials and others that need to interact with the system, and what processes could be introduced to limit this trust.

## Included Without Edits (TO BE DISCUSSED)

**In previous work a master student has designed a simplified Decentralized application (DApp) aimed at supporting parts of the requirements for recording grades that could to some extent be built on.**

The BBChain project has modeled some of the procedures of academic institutions in the form of smart contracts on the [Ethereum platform](https://github.com/ethereum/go-ethereum).
The goal of this project is to develop a DApp (i.e. Decentralized application) that can be integrated in the BBChain project.
Currently, the BBChain project only have a command line interface and this project aims to enhance its usability by invoking the BBChain contracts API from a graphical user interface.

In particular, the UI should allow easy use of the certification interface provided by the BBChain smart contracts, allowing users to among other things: create, sign, revoke and verify the academic credentials using a web browser or their phones.
The users should also be able to manage their cryptographic keys and interact with all functionalities exposed by the BBChain smart contracts.

## Tasks / Milestones

- Study existing literature on academic credential management on blockchains and DApp developments
- Study the current procedures of academic institutions
- Design and implement a web frontend or mobile application to access these procedures
- Implement and deploy a Ethereum Faucet on the BBChain private cluster
- Simulate an evaluation process using the developed UI and the Faucet to fund the accounts
- Optionally, integration with the BBChain identity service can be done
- Report on findings and lessons learned from the implementation, concluding on the feasibility of the developed application for the BBChain scenario
