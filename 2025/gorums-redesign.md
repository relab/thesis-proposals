# Redesign Gorums with Better Modularity and Generics

## Administrative

- Supervisor: Hein Meling
- Contact: <hein.meling@uis.no>
- Several students can work on this project.

## Prerequisites

- Distributed systems (DAT520)
- Proficient in the Go programming language
- Have a strong interest in software design with a focus on distributed systems and networking

## Project Description

The goal of this project is to rethink the design of [Gorums][1] to provide better modularity, decoupling, and to use generics where appropriate.
Moreover, the design should provide a better separation of concerns between the application layer and the Gorums library.
The new design should provide a selection of building blocks that can be used in generated code.

The goal is to retain an RPC-like calling semantics, but to provide a more flexible and modular design that can support a variety of use cases for distributed systems in general, but Quorum-based system in particular.

The design could draw inspiration from a variety of sources:

- [DepFast: Orchestrating Code of Quorum Systems][2]
- [connectrpc][4] and other Buf tools
- [gRPC][3]
- [relab/hotstuff][5]'s event loop architecture and other features

Features that should (optionally) be supported:

- Most existing features of Gorums, such as quorum calls to groups of servers (configurations)
- An event loop mechanism or similar to support internal event handling
- Client and server-side code generation
- Quorum functions or a similar mechanism to support quorum-based protocols
- (Optional) [H3/QUIC-based][6] transport layer for RPCs; QUIC is being considered for inclusion in the Go standard library (see [discussion here][7]).

Note: The supervisor has discussed some of these ideas with the [connectrpc][4] developers, and they are willing to make adjustments to their API design to support our use cases, if we can provide a clear description of our requirements.
That would allow us to rely on their RPC library, and focus on the design of the Gorums library.

## Tasks

- Review literature [Gorums][1] and [DepFast][2] and more
  - Write background section discussing the state of the art
- Become familiar with [connect-go][4], [relab/hotstuff][5], and [relab/gorums][8] implementations
- Propose a new design for Gorums
  - Prototype the design in Go, based on the existing Gorums code
- Evaluate the design with a few use cases:
  - A simplified version of [relab/hotstuff][5], where the hotstuff protocol uses the new Gorums library
  - Focus on the separation of concerns between the blockchain application layer using hotstuff and the Gorums library
    - The application layer should be a blockchain application
  - Evaluate and discuss the benefits of the new design
- Evaluate the performance of the new design
  - Compare with the existing Gorums implementation

[1]: https://ieeexplore.ieee.org/document/7980198
[2]: https://www.usenix.org/conference/atc22/presentation/luo
[3]: https://grpc.io/
[4]: https://github.com/connectrpc/connect-go
[5]: https://github.com/relab/hotstuff
[6]: https://github.com/quic-go/quic-go
[7]: https://github.com/golang/go/issues/58547
[8]: https://github.com/relab/gorums
