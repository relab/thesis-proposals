Master
# Tree selection for signature aggregation

### Supervisor: Leander Jehl

### Prerequisits
- Network security (DAT510)
- Go programming language
- Distributed systems (DAT520)

### Background
Secure distributed systems that are meant to withstand arbitrary failures and malicious attacks require messages to be authenticated, e.g. using digital signatures. To establish a common truth, the nodes in such system may publish a certificate, signed by a majority of the participating nodes. However, when the number of nodes in the system increases, verifying such certificates quickly becomes infeasible.

#### Multisignatures
A promising alternative to classical DSA and ECDSA algorithms are multisignature schemes. Multisignatures, e.g. BLS signatures allow to combine individual signatures for the same message. Verification of the aggregated signature has a similar cost 
as verification of one individual signature.

While an understanding of digital signatures is usefull, existing libraries will be used to perform all cryptographic operations in this project.

#### Broadcast trees and aggregation
In a tree overlay, messages can be broadcast when every node forwards the message to its children. Similarly, aggregation can happen when every node collects and verifies the signatures from its children and forwards the aggregated signature.


### Project Description
The goal for this project is to investiaget different optimization techniques for the aggregation of multisignatures on broadcast trees.
Especially, it would be interesting to investigate optimization techniques that assume that all nodes are correct, 
and how to maintain the benefit of these techniques in the presence of individual failures.

Possible optimization encompass the following:
* Aggregated verification: Instead of verifying individual signatures (from children) before aggregation and forwarding, signatures can be aggregated, verified and forwarded. This significantly reduces computational overhead if all children deliver correct signatures.
* Binary search for invalid signatures in aggregates: If the verification of an aggregate fails, it is possible to use binary search to find and remove invalid signatures from the aggregate.
* Tree reconfiguration: Faulty, slow or misbehaving nodes should be removed from central positions in the tree and possibly excluded from aggregate signatures.

### Groups
This project may be taken by a group of two students.

### References
* [Co-Signing (Signature aggregation)](https://arxiv.org/pdf/1503.08768.pdf)
* [Co-Signing implementation using BLS signatures](https://github.com/dedis/cothority/tree/master/blscosi)
* [BLS signatures](https://crypto.stanford.edu/~dabo/pubs/papers/BLSmultisig.html)

