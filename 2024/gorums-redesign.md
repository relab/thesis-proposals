# Redesign Gorums with Better Modularity and Generics

## Administrative

- Supervisor: Hein Meling

## Prerequisites

- Proficient in the Go programming language
- Have an interest in distributed systems and networking

## Project Description

The goal of this project is to rethink the design of Gorums to provide better modularity, decoupling, and to use generics where appropriate.

Support RPC calling to groups (configurations).
Should draw experience from relab/hotstuff's eventloop (eloop or evloop or eveloop) and other features.
Should maybe be compatible with connect-go. Reach out to them for advice on or suggestions for the API needing to support multiple URLs, and the QuorumFunction.

## OLD BELOW

The goal of this project is to implement a QUIC RPC library in Go.
The library should support the following features:

- Send and receive protobuf messages over QUIC.
- Cryptographic authentication of the server and client.
- Largely compatible with the [gRPC](https://grpc.io/) library.
- Integrated with the [hotstuff](https://github.com/relab/hotstuff) library.

## Tasks

- Study existing QUIC libraries, such as [quic-go](https://github.com/quic-go/quic-go) and the ongoing discussion about inclusion of [quic](https://github.com/golang/go/issues/58547) into the Go standard library.
- Study the [gRPC](https://grpc.io/) library.
- Identify the requirements for the QUIC RPC library together with supervisors.
- Design API for and implement the QUIC RPC library.
