# Co-Signing over P2P networks

### Supervisors: Leander Jehl and Hein Meling

### Prerequisits
- Network security (DAT510)
- Distributed systems (DAT520)
- Go programming language

A good understanding of elliptic curve cryptography would be a plus, but what is
necessary can be picked up on the way.

### Background
Secure distributed systems that are meant to withstand arbitrary failures and
malicious attacks require messages to be authenticated, e.g. using digital
signatures. To establish a common truth, the nodes in such system may publish a
certificate, signed by a majority of the participating nodes. However,
when the number of nodes in the system increases, verifying such certificates
quickly becomes infeasible.

A promising alternative is *Co-Signing* using Schnorr-Signatures. Co signing can
produce certificates that are signed by thousands of nodes, but can be verified
as checking a single signature.
However, Schnorr-Signatures require the signing processes to be available during
a two phase protocol. This poses a challenge when the underlying system is
subject to frequent failures, disconnections or churn in membership as is the
case in Peer-To-Peer (P2P) networks.

A solution for this problem is to utilize a membership service, such as Fireflies.
Nodes in Fireflies maintain an up-to-date membership list over the system.

### Project Description
The goal of this project is to investigate the impact of frequent node and network
failures and membership churn on Co-Signing protocols, and how the Fireflies
membership service can be utilized for Co-Signing.

The project will build on open source implementation of both Co-Signing and
Fireflies. Initial experiments should verify the behavior of Co-Signing under
network churn. We will then investigate how Fireflies can be utilized to improve
these results. To tolerate frequent churn events some extensions to Co-Signing
may have to be implemented.

### Milestones
- Study Co-Signing library and perform initial experiments
- Design scheme to integrate Co-Signing with Fireflies membership
- Implement and evaluate Co-Signing using Fireflies membership

### References
[Co-Signing](https://arxiv.org/pdf/1503.08768.pdf)

[Co-Signing implementation](https://github.com/dedis/cothority/tree/master/ftcosi)

[Firefiles](https://dl.acm.org/citation.cfm?doid=2701418)
