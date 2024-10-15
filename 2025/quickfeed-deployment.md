# Quickfeed Deployment and Test Execution Environment

## Administrative

- Supervisor: Hein Meling and Jostein Hagen Lindhom
- Group Composition: 1-3 students (the scope can be adjusted based to the number of students)

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT310 Web programming is recommended
- Proficient in the Go programming language
- Proficient with Git and GitHub

## Background on Quickfeed

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

### Part 1: The Continuous Deployment Environment

The deployment environment should be configured to support Continuous Deployment.

The production version of Quickfeed runs on a virtual machine on one of UiS's Unix machines.
However, development and testing in this environment result in a certain amount of fragility.
Hence, we would like to move to a world where setting up and running a test environment is as simple as building and running a docker image or even simpler.

In this project you will prepare docker images for development and deployment environments for QuickFeed.
A more detailed description of this project is available here: [QuickFeed DevOps](https://github.com/relab/thesis-proposals/blob/master/2022/quickfeed-devops.md).
(PS: The project description is a bit outdated. We no longer use the Envoy proxy and certificates are now managed directly by QuickFeed.)

The goals for this part:

- Create a continuous deployment pipeline
- Should be possible to deploy to test.itest.run before uis.itest.run

Note that we already have a CI pipeline on GitHub Actions that builds and tests the code.
The students are expected to extend this pipeline to deploy the code to a test environment.

### Part 2: Test Execution Environment

In this task, the idea is scale up the test execution environment to run student tests in a cloud or cluster environment.

We are interested in experimenting with a relatively new technology called [Service Weaver](https://serviceweaver.dev).
Service Weaver is a platform that allows you write microservice components that can be deployed in a cloud environment, but is easy to test and run on your local machine.
In this task you will prepare a Service Weaver component to run student tests that can be deployed using Service Weaver's deployment modules.
This will involve interacting with Service Weaver API to deploy a container to run and test student submitted code.
The deployment component should be integrated with the QuickFeed server to run tests on student submitted code.

### Part 3: Test Execution Environment Advanced (optional)

Another deployment option is to deploy the test execution environment to a Kubernetes cluster.
In this project you will prepare a Kubernetes cluster to run student tests.
This will involve interacting with Kubernetes API to deploy a container to run and test student submitted code.
A more detailed description of this project is available here: [QuickFeed Kubernetes](https://github.com/relab/thesis-proposals/blob/master/2020/autograder-cicd.md).
(PS: The project description is a bit outdated. Using GitHub Actions is no longer a relevant choice and it is unlikely to involve frontend development.)

## Reading Material

- Service Weaver [documentation](https://serviceweaver.dev/docs.html)
- See [this issue](https://github.com/quickfeed/quickfeed/issues/360) on Quickfeed's issue tracker
- Full [list of issues](https://github.com/quickfeed/quickfeed/issues)
- [Get Started with Docker](https://www.docker.com/get-started)
- [Container Networking is simple](https://iximiuz.com/en/posts/container-networking-is-simple/)
- Contact supervisor for more information.

[1]: https://github.com/quickfeed/quickfeed
