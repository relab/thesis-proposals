# Visualization of distributed executions

### Supervisors: Leander Jehl and Hein Meling

### Prerequisites:
- Go programming language

### Project Description

Gorums is a framework for group-RPCs (quorum-calls) developed at UiS. A
quorum-call allows to invoke a remote procedure simultaneously on multiple hosts
and collect and combine the replies.

Distributed algorithms, such as the ones implemented using Gorums are often difficult
to get right, test or debug, since RPCs belonging to different quorum-calls may
be processed in different order by different servers.

The goal of this project is to build a web application that allows to run,
visualize and debug executions of distributed applications in the Gorums framework.
The web application should consist of a backend that intersects quorum-calls invoked
by Gorums, and allows to manually trigger, delay or cancel the individual RPCs.

Quorum-calls invoked at different processes should be displayed in a common Web
application. The Web application should allow to manually or programmatically trigger,
delay or cancel the individual RPCs and record and display requests and replies
of these RPCs.

Additionally the web application should also allow to display state of the processes
after completing a quorum-call and the ability to trigger or delay timeouts
used at the individual processes.

### Milestones
- get used to Gorums, implementing and running a simple example
- hardcode debug front-end and backend for example
- integrate debug backend to be created by the Gorums code generator
- use debug application to visualize a complex existing application build in the Gorums framework


### Gorums Background:

[Gorums](https://github.com/relab/gorums) is a novel framework for building fault tolerant distributed systems. Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses. Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies. These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed. Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls. Gorums is a wrapper around the gRPC library. Services are defined using the protocol buffers interface definition language.

### Resources

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198/)
- [Gorums Source code](https://github.com/relab/gorums)
