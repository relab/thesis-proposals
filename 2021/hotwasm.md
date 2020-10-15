
# Diversification for HotStuff through WebAssembly

### Supervisor: Leander Jehl


### Prerequisits
- Go programming
- Preferably Distributed systems (DAT520) or Blockchain Technology (DAT650)

### Project
The goal of this project is to utilise WebAssembly technology to provide a diverse execution environment for a BFT algorithm.
To reach this goal, it is planned to build on an existing implementation of the HotStuff algorithm, developed at UiS [1].

The goal for this thesis is to compile the existing algorithm to Web Assembly and try to run the resulting system using different VMs or Interpreters.

The long term goal is to develop a runtime that can be used with different BFT algorithms. 
If time permits, you may be able to indentify, how to separate the runtime from the BFT algorithm.

### Background
BFT algorithms such as the HotStuff algorithm can prevent not only malicious actions of protocol participants, but also tolerate arbitrary software failures and outsider attacks on the system. However this guarantee requires that nodes fail independently. If the same software bug causes all replicas to fail, or the same vulnerability allows an attacker to subvert all machines, the system is of little use. Since it is almost impossible to completely prevent the occurrence of vulnerabilities and bugs in the complex stack that modern software systems are running, a reasonable alternative is to try and prevent the same bugs from occurring at multiple nodes in the system. A promising approach for this is to use different, of the shelve software, e.g. run replicas on different operating systems as done in [2].
In this project we want to expand on this approach and, relying on WebAssembly technology, use multiple runtimes to execute the same BFT algorithm.

### DiVeS
This project is part of the DiVeS research project, which is a collaboration between the Reliable Systems Lab at UiS and the Distributed Systems group at TU Braunschweig, Germany.

The group in Braunschweig has significant experience with the instrumentation of Web Assembly and Prof. Kapitza from Braunschweig will participate in the supervision.


### Resources

[1] Hot Stuff implementation: https://github.com/relab/hotstuff

[2] Garcia et al., “Lazarus: Automatic Management of Diversity in BFT Systems”. In:
Proceedings of the 20th International Middleware Conference. ACM, 2019. [pdf](http://www.di.fc.ul.pt/~bessani/publications/middleware19-lazarus.pdf)
