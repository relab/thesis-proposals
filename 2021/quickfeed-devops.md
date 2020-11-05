# Quickfeed DevOps: Improved Development and Deployment Facilities

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 or 3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT310 Web programming is recommended
- Proficient in the Go programming language

## Background on Quickfeed (also known as Autograder)

Quickfeed is a system developed at UiS to automatically evaluate student hand-ins.
Quickfeed is able to run a set of tests against any hand-in delivered by students and will provide a score and feedback for the students.
We have recently reimplemented both the Quickfeed backend and frontend to improve its robustness.
In particular, the backend is now based on a gRPC-based server, a SQL database, the backend interacts with GitHub (and GitLab).
The backend use the gRPC-web framework for handling client requests (with a few remaining REST interface calls).
We use Docker containers to run student code.
On the frontend, we used the Typescript language along with the React framework from Facebook to avoid many of the concerns with the Javascript language.

## Project description

In this project, the goal is to create a development and deployment environment based on docker images for running the Quickfeed server and other components, such as Envoy proxy, NGINX, and the database etc.
The development and deployment environment should be simple to use and get started with for new developers.

Currently, the production version of Quickfeed runs on a virtual machine on one of UiS's Unix machines.
However, development and testing in this environment results in a certain amount of fragility.
Hence, we would like to move to a world in which setting up and running a test environment is as simple as building and running a docker image or even simpler.
Possibly with integration using VSCode's Remote Containers plugin.

The project involves configuring GitHub (and possibly GitLab) to interact with the development environment. Ideally, these configuration steps should be possible to automate.

Depending on the complexity of this project, the students that take this project may also be asked to help with some of the other issues listed on the [issue tracker](https://github.com/autograde/quickfeed/issues) that fit the scope of the project.

Implementation language is mainly Go and Docker files.

## Reading material

- See [this issue](https://github.com/autograde/quickfeed/issues/360) on Quickfeed's issue tracker.
- Full [list of issues](https://github.com/autograde/quickfeed/issues).
- More to be added; contact supervisor for more information.
