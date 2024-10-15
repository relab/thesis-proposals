# Components for complex systems

## Administrative

- Supervisor: Leander Jehl
- Contact: <leander.jehl@uis.no>

## Preliminaries

- DAT520 Distributed systems
- Familiarity with Rust will be a plus

## Project Description

Implementing distributed algorithms like Paxos, Raft, PBFT or Hotstuff is difficult.
Implementations often result in big and monolithic code bases.

The goal for this thesis is to investigate how WebAssembly components can be used to compartmentalize implementations of distributed algorithms.

WebAssembly is not limited to the browser, but is seen as a new building block for deploying arbitrary applications.
The interface of WebAssembly components can be specified in a language agnostic WIT file.
The components can be implemented in different source languages, like Rust, C++, Go, Javascript that can be compiled to WebAssembly.

The goal of this thesis is to create a compartmentalized version of Paxos, where proposer, acceptor, learner and state machine application are different modules.
Research questions include how best to combine, test, and run the modules. 
This may include adjustment of a WebAssembly runtime.
Further, the thesis should continue to investigate at least one of the following *advanced questions*:
- How to update components without stopping the system?
- How to design components that allow flexible storage solutions, i.e. in memory and on disk?
- Can the experimental threading feature be used for some components?
- Extension of the compartmentalized approach to more complex algorithms like Hotstuff?

## Milestones

- Define interface for Paxos components
- Implement and run first variant of Paxos components
- Investigate further advanced questions

If you have questions, please contact Leander Jehl by email or in E403b.