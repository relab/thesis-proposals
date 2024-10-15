# Use of the quint specification language

## Administrative

- Supervisor: Leander Jehl
- Contact: <leander.jehl@uis.no>

## Prerequesists:

- DAT520 Distributed systems

## Project Description

Quint [1] is a novel specification language with support for execution and formal analysis.
The ability to execute specifications allows to create example runs which give a better understanding of how an algorithm functions. 
The connection to formal analysis allows to verify if the specification fulfills certain properties.

We have a formal specification of the Hotstuff algorithm [2,3]. 
Hotstuff is a consensus algorithm, which lies at the core of several Blockchain systems.
Quint is said to provide a more user friendly interface than traditional tools like TLA+.
The goal for this thesis is to transform the existing TLA+ specification for hotstuff to a quint specification. 

You should evaluate usability, and performance of the two tools.

You should also work on additional goals like:
- Extending the quint specification to include additional details or
- Generating an additional quint specification of a different algorithm

*If you have questions, please contact Leander Jehl by email or in E403b.*