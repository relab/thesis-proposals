# Continuous Integration Test Platform Using SSH Deployment with Iago

## Administrative

- Supervisor: Hanish Gogada, Hein Meling

## Prerequisites

- Proficient in the Go programming language

## Project Description

TODO(meling): Update description with more details on CI test platform.

The goal of this project is to implement a generic deployment tool for deploying our Go-based command line applications on a set of servers.
The tool should be able to deploy applications on a set of servers, run the applications in parallel, and collect the output from the applications.
A key requirement is simplicity of use.

We currently use [iago][1] and [wrfs][2] in [hotstuff][3].
However, we want to simplify and improve the user experience for using iago, both

## Tasks

- Study and take inspiration from existing deployment tools, such as Ansible, Terraform, and Iago.
- Identify the requirements for the deployment tool together with supervisors.
- Fix existing TODOs in Iago.
- Improve documentation.
- Design API for and implement several generic tasks based on the identified requirements; examples include:
  - Create temporary directory on a set of servers.
  - Deploy application on a set of servers.
  - Run application in parallel on a set of servers.
  - Collect output from the application.
- Establish a CI test environment for hotstuff using the deployment tool.

[1]: https://github.com/relab/iago
[2]: https://github.com/relab/wrfs
[3]: https://github.com/relab/hotstuff
