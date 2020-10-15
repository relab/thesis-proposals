# BBChain DApp for Academic Credentials

## Administrative

- Supervisor: Hein Meling and Rodrigo Saramago

## Prerequisites

- DAT310 Web programming
- DAT320 Operating systems and systems programming
- Be interest in user interface design
- Proficient in the Go programming language
- Proficient in web programming

## Project Description

The BBChain project has modeled some of the procedures of academic institutions in the form of smart contracts on the [Ethereum platform](https://github.com/ethereum/go-ethereum).
The goal of this project is to develop a DApp (i.e. Decentralized application) that can be integrated in the BBChain project.
Currently, the BBChain project only have a command line interface and this project aims to enhance its usability by invoking the BBChain contracts API from a graphical user interface.
Further, support could be added to Quickfeed (formerly Autograder), to automate or simplify the grade registration process.

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

- [Vugu](https://www.vugu.org/)
- [GIO](https://github.com/theclapp/gio-mirror)
- [GopherJS](https://github.com/gopherjs/gopherjs)
- [WebAssembly](https://github.com/golang/go/wiki/WebAssembly)
- [Ethereum Faucet](https://github.com/ethersphere/goerli-faucet.git)
- [Metamask](https://metamask.io/)
- Rodrigo's draft paper
