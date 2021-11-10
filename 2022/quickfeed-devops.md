# Quickfeed DevOps: Improved Development and Continuous Deployment Facilities

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 or 3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT310 Web programming is recommended
- Proficient in the Go programming language

## Background on Quickfeed (also known as Autograder)

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

In this project, the goal is to create a development and deployment environment for QuickFeed.

### Part 1: The Development Environment

The development environment should be designed to be as simple as possible to get started for new developers, and should mimick as much as possible of the real environment.

The dev environment must support running the QuickFeed server and related components, including the Envoy proxy, certificate handling, the Discord helpbot server.
The dev environment should also encompass a test course with users in the database and corresponding organization and users on GitHub.

Creating test users and organization on GitHub should also be made as simple as possible, either with clear instructions or using a script.
Ideally, these configuration steps should be possible to automate.

Much of the dev environment could be placed in a Docker image or similar technology with integration with VSCode's Remote Containers plugin.
The dev environment should also be accessible to use with other IDEs, such as Goland.
Furthermore, the dev environment should also be made available via [GitHub's codespaces][3].

The goals for this part:

- Must be able to run and view the frontend on the local machine or in a container
- Should be able to receive GitHub webhook events

### Part 2: The Continuous Deployment Environment

The deployment environment should be configured to support Continuous Deployment.

The production version of Quickfeed runs on a virtual machine on one of UiS's Unix machines.
However, development and testing in this environment result in a certain amount of fragility.
Hence, we would like to move to a world where setting up and running a test environment is as simple as building and running a docker image or even simpler.

The goals for this part:

- Create a continuous deployment pipeline
- Should be possible to deploy to test.itest.run before uis.itest.run

PS: We already have a CI pipeline.

### Summary

The students who take this project is also expected to create issues on the [issue tracker][2] related to this project to make adjustments to the Go code of the QuickFeed server and the frontend code, as necessary to make it easier to facilitate the two parts above.

The students may also be asked to help with some of the existing issues listed on the [issue tracker][2] that fit the project's scope.

The results of this project could be implementation of one or more command line tools written in Go, Dockerfiles and possibly Ansible scripts.

## Reading Material

- See [this issue](https://github.com/autograde/quickfeed/issues/360) on Quickfeed's issue tracker
- Full [list of issues](https://github.com/autograde/quickfeed/issues)
- [Get Started with Docker](https://www.docker.com/get-started)
- [Container Networking is simple](https://iximiuz.com/en/posts/container-networking-is-simple/)
- [Get Started with Ansible](https://www.ansible.com/resources/get-started)
- Contact supervisor for more information.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/autograde/quickfeed/issues
[3]: https://github.com/features/codespaces
