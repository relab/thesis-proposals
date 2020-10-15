# Quorum-Selection in the XFT model

### Supervisors: Leander Jehl

### Prerequisites:

- Distributed systems (DAT520)
- Go programming language
- Excellent programming skills

### Motivation:
With the advent of the *blockchain* paradigm, algorithm tolerating arbitrary
failures have received increased attention. *Byzantine Fault Tolerance* (BFT)
allow to maintain an available and consistent service despite
crashes, omission of messages and even malicious failures caused by an attacker
that may have compromised one of the machines.

BFT algorithms build the backbone of small and medium scale blockchains, such as
consortium blockchains. However, BFT algorithm typically require many correct
machines and high message complexity, to mask such failures.

Quorum-Selection and the XFT model [2] are two novel advances that aim to address
the high resource utilization of BFT algorithms.

*Quorum-Selection* [1] is a novel mechanism that can be used to select a set
(quorum) of well-behaved nodes, among the nodes running a BFT algorithm. When
running on such a quorum the number of messages and operations in the
algorithm can be significantly reduced, since no failures have to be masked.

When using the XPaxos algorithm [2] in the *XFT Model*, it is possible
to implement BFT with fewer resources or tolerating more failures than
traditional approaches. However, the existing XPaxos algorithm uses an ad hoc
solution for quorum selection which can lead to reduced availability, especially
when XPaxos is scaled to tolerate more than just a single failure.

### Project Description:
The goal for this project is to develop, implement and evaluate an algorithm
that utilizes Quorum-Selection in the XFT model.

To adopt Quorum-Selection in XPaxos requires among other a careful analysis of
the message patterns in XPaxos and detection of omission of such messages.
Other changes may be added to XPaxos to improve performance.

### Milestones:
* re-implement and evaluate XPaxos and show deficit in availability in presence of failures
* implement and evaluate Quorum-Selection primitive
* design and implement XPaxos variant utilizing Quorum-Selection
* evaluate system experimentally

### References

[1] [Quorum-Selection draft](http://www.ux.uis.no/~ljehl/pdf/QSforDAT620.pdf)

[2] [XFT and XPaxos](https://arxiv.org/pdf/1502.05831.pdf)
