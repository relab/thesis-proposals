Master
# Quorum selection for XPaxos

### Supervisor: Leander Jehl

### Prerequisites:

- Distributed systems (DAT520)
- Go programming language

### Motivation:
With the advent of the *blockchain* paradigm, algorithm tolerating arbitrary
failures have received increased attention. *Byzantine Fault Tolerance* (BFT)
allows to maintain an available and consistent service despite
crashes, omission of messages and even malicious failures caused by an attacker
that may have compromised one of the machines.

BFT algorithms build the backbone of small and medium scale blockchains, such as
consortium blockchains. However, BFT algorithm typically require many correct
machines and high message complexity, to mask such failures.

Quorum-Selection and the XFT model [2] are two novel advances that aim to address
the high resource utilization of BFT algorithms.

When using the XPaxos algorithm [2] in the *XFT Model*, it is possible
to implement BFT with fewer resources or tolerating more failures than
traditional approaches. However, the existing XPaxos algorithm uses an ad hoc
solution for quorum selection which can lead to reduced availability, especially
when XPaxos is scaled to tolerate more than just a single failure, as shown in [3].

*Quorum-Selection* [1] is a novel mechanism that can be used to select a set
(quorum) of well-behaved nodes, among the nodes running a BFT algorithm. Quorum-Selection is expected to significantly reduce worst case quorum changes in XPaxos.

### Project Description:
The goal for this project is to implement and evaluate Quorum-Selection for XPaxos.
A priliminary addoption of Quorum-Selection for XPaxos is described in [1].

### Milestones:
* implement and evaluate Quorum-Selection primitive
* design and implement XPaxos variant utilizing Quorum-Selection
* evaluate system experimentally

### References

[1] [Quorum-Selection draft](https://conferences.computer.org/icdcs/2019/pdfs/ICDCS2019-49XpIlu3rRtYi2T0qVYnNX/7rH2hXOH1RkmmqRLWkbBRr/6ROVWhdvws3qigH5fUMxtk.pdf)

[2] [XFT and XPaxos](https://arxiv.org/pdf/1502.05831.pdf)

[3] [XPaxos inGo](https://medium.com/princeton-systems-course/xft-implementation-evaluation-5d57b25c5c5f)