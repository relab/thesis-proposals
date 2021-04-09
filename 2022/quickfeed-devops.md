# Quickfeed DevOps: Improved Development and Deployment Facilities

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

In this project, the goal is to create a development and deployment environment based on docker images for running the Quickfeed server and other components, such as Envoy proxy, NGINX, and the database, etc.
The development and deployment environment should be simple to use and get started with for new developers.

The production version of Quickfeed runs on a virtual machine on one of UiS's Unix machines.
However, development and testing in this environment result in a certain amount of fragility.
Hence, we would like to move to a world where setting up and running a test environment is as simple as building and running a docker image or even simpler.
Possibly with integration using VSCode's Remote Containers plugin.

The project involves configuring GitHub (and possibly GitLab) to interact with the development environment.
Ideally, these configuration steps should be possible to automate.

Depending on the complexity of this project, the students who take this project may also be asked to help with some of the other issues listed on the [issue tracker][2] that fit the project's scope.

The implementation language is mainly Go and Docker files and possibly Ansible scripts.

## Reading material

- See [this issue](https://github.com/autograde/quickfeed/issues/360) on Quickfeed's issue tracker
- Full [list of issues](https://github.com/autograde/quickfeed/issues)
- [Get Started with Docker](https://www.docker.com/get-started)
- [Container Networking is simple](https://iximiuz.com/en/posts/container-networking-is-simple/)
- [Get Started with Ansible](https://www.ansible.com/resources/get-started)
- Contact supervisor for more information.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/autograde/quickfeed/issues
