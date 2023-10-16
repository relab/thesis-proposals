# Formally verified go code

## Administrative

- Supervisor: Leander Jehl
- Contact: <leander.jehl@uis.no>

## Project Description

Software products are subjects to errors and bugs. 
Formal verification is a collection of methods and tools that allow to formally proof that a function, method or larger unit of code implements a given specification.
Modern methods for formal verification mostly automate the process of writing proofs, but still require users to write specifications and provide annotations used in the proof, and therefore is still considered a time consuming and complex task.
However, for certain safety critical applications, where bugs may be desastrous or may easily be exploited, such efforts are valid.

Blockchain infrastructure is one such application.
The goal for this thesis is to create a formally verified variant of core datastructure of the relab/hotstuff [2] blockchain implementation.


Daphny [1] is a well developed tool, which uses its own language to write code and specifications. 
The relab/hotstuff framework is implemented in Go and a compiler for generating Go code from Daphny exists. 

The envisioned approach for this thesis is to first create a verified data structure in Daphny, then try to generate Go code, and compare its performance and structure with native code. 
Finally, the goal is to try and incorporate the generated code into the framework, replacing code written by hand.

## Tasks
- Familiarize yourself with the Dafny framework and language.
- Model and verify the tree/blockchain datastructure from relab/hotstuff in Dafny.
- Generate and evaluate generated Go code.
- Investigate ability to integrate generated Go code in existing framework.


## Resources
[1]: https://dafny.org/dafny/
[2]: https://github.com/relab/hotstuff/