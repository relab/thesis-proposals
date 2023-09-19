# Implement a QUIC RPC library

## Administrative

- Supervisor: Hein Meling

## Prerequisites

- Proficient in the Go programming language

## Project Description

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
