# Graphical Interface for File Repair Algorithm

## Administrative

- Supervisor: Hein Meling and Racin Nygaard

## Prerequisites

- DAT200 Algorithms and Data Structures
- DAT320 Operating systems and systems programming is recommended.
- Proficient in the Go programming language

## Project Description

The main task of this project will be to create a graphical user interface for Alpha Entanglement codes.
Alpha Entanglement codes is a redundancy scheme used for preserving availability and durability despite large amounts of failures.

Currently the BBChain project at the department is researching on how to apply Alpha Entanglement codes in distributed storage systems where storage nodes may fail at any time.

To aid us in this work we want a graphical user interface with the following features:

- Parsing a log in CSV format with data from the repair algorithm
- Provide an intuitive display for Alpha Entanglement
- Stepping through each entry in the log using the arrow keys
- Simulate storage failures to test the repair algorithm
- Support different entanglement configurations
- Generate plots

The technology to be used for the user interface is flexible, but these two libraries may be worth a closer look: [gio](https://gioui.org) and [gonum/plot](https://github.com/gonum/plot).

## Reading Material

- [Alpha Entanglement Codes](https://arxiv.org/abs/1810.02974)
- [Swarm](https://swarm.ethereum.org/)
- [Filecoin](https://filecoin.io/)
- [gio](https://gioui.org)
- [gonum/plot](https://github.com/gonum/plot)
