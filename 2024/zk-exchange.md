# Using Zero-Knowledge for Fair Stock and Crypto Trading

## Administrative

- Supervisor: Racin Nygaard and Hein Meling
- Prof Meling is currently on sabbatical, but will be available for physical meetings from November 27, 2023.
- Before that I will be happy to answer questions by email, or set up a Zoom call to discuss the project with prospective students.
- Contact: <hein.meling@uis.no>
- Several students can work on this project.

## Prerequisites

- Good understanding of cryptographic primitives
- Strong math background
- Recommended:
  - Blockchain
  - Proficiency in a programming language
- Optional / Nice to have:
  - Zero-Knowledge
  - Stock or crypto trading
  - Formal verification

## Background

A centralized stock exchange such as [Nordnet][1] matches a buyer and seller of a particular security.
In normal circumstances, the exchange matches the buyer and seller of a particular security at a given price.
The buyer first has to place a *BUY* order at the exchange, or the seller must place a *SELL* order at the exchange.

Regardless of who goes first, a significant amount of information is publicly revealed.
Using this information, other parties can learn about potential arbitrage opportunities, security correlation, etc.

Moreover, from the instant the opposite party clicks to place the order on their device, there is a non-negligible delay until the order is executed.
This delay leaves time for malicious third parties to attack, such as executing the order for themselves by jumping ahead in line, canceling the opposite order to manipulate the price, and more.

## Technical Description

A Zero-Knowledge (ZK) proof allows a party (**prover**) to cryptographically prove knowledge of some secret information to another party (**verifier**) without revealing the information itself.
If you are new to ZK proofs, I recommend looking at the toy examples described on the [Wikipedia page][2].

A ZK-proof system may either be interactive or non-interactive.
The latter continues to gain traction as proofs may be stored on a blockchain and do not require any (direct) interaction between the parties (the prover and verifier).

For a stock exchange, a ZK proof may allow the buyer to place a *BUY* order without revealing to anyone, not even the exchange, which security he wants to buy, the offered price, or the amount.
The *BUY* order should be placed on a non-immutable data storage like a blockchain.
When a seller places a *SELL* order, the buyer can prove that he has the right to buy the security, given his order matches the asking price and amount.

After the buyer and seller have been matched and the order executed, it may be publicly revealed to be registered in the official records.

For a practical implementation, allowing the *BUY* and *SELL* orders to reveal some information publicly may be necessary.
This information could be expressed in a range instead of an explicit value, e.g., a *BUY* order for [100,300] stocks at $[50,80] each.

## Project Description

This project aims to design and implement a prototype of a secure privacy-oriented exchange based on Zero-Knowledge technology.

Our group mainly uses Go for system implementation, but you will be free to use other language(s).
In particular, some libraries and dependencies may require a certain programming language.

You are expected to evaluate multiple design choices.
Some of the design criteria to consider are performance, privacy, security, threat model, scalability, correctness, and on/off-chain.

The scope of the project will be limited after discussions during the initial project meetings.

The supervisor can provide further guidance on the design choices and implementation.

## Tasks

- Review the supplied resources and other literature on Zero Knowledge proofs and zk-SNARK
  - Write a background section discussing the state-of-the-art
- Design an exchange based on ZK technology
  - Document the process by considering alternative design choices and pros/cons
- Implement a prototype of the design
- Deploy the implementation on a larger network, such as a public test net or our own BBchain cluster
  - Evaluate the implementation and discuss any changes from the original design
- Report on findings and lessons learned


## Resources
- [Wikipedia page on Zero Knowledge][2]
- [Zero Knowledge Proof original paper][6]
- [Why and How zk-SNARK Works: Definitive Explanation][8]
- [Circom circuit compiler][3]
- [Example projects on Starknet][4]
- [Overview article from Ethereum][7]

[1]: https://www.nordnet.no/market/stocks/16119063-microsoft
[2]: https://en.wikipedia.org/wiki/Zero-knowledge_proof
[3]: https://docs.circom.io/getting-started/installation/
[4]: https://www.dappland.com/category/defi
[5]: https://github.com/iden3/circom
[6]: https://web.archive.org/web/20110706185820id_/http://crypto.cs.mcgill.ca/~crepeau/COMP647/2007/TOPIC02/GMR89.pdf
[7]: https://ethereum.org/en/zero-knowledge-proofs/
[8]: https://arxiv.org/pdf/1906.07221.pdf%EF%BC%9B
