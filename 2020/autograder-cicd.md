# Autograder: Scaling Autograder with Kubernetes or GitHub CI/CD Actions

## Supervisor: Hein Meling

## Prerequisites

- DAT320 Operating systems and systems programming is recommended.
- Go programming language is required.

## Expected Learning Outcomes

- Learn how to develop with Kubernetes and Docker containers and to use GitHub Actions to build and deploy.
- Students are expected to learn these technologies on their own.

## Group Composition: 2 or 3 Students.

## Background on Autograder

Autograder is a system developed at UiS to automatically evaluate student hand-ins. Autograder is able to run a set of tests against any hand-in delivered by students and will provide a score and feedback for the students. We have recently reimplemented both the Autograder backend and frontend to improve its robustness. In particular, the backend is now based on a gRPC-based server, a SQL database, the backend interacts with GitHub (and GitLab). The backend use the gRPC-web framework for handling client requests (with a few remaining REST interface calls). We use Docker containers to run student code. On the frontend, we used the Typescript language along with the React framework from Facebook to avoid many of the concerns with the Javascript language.

## Project Description

In this project we aim to scale Autograder to support more courses and users. One of the key challenges with Autograder is that we currently run tests of student code on every push to GitHub. This can cause a significant delay when many students are actively working on their assignments, because each student submission is tested in a separate docker container running on the same machine as the autograder server (actually a virtual machine).

To scale Autograder, this project will investigate and implement two technologies that can alleviate this problem. The first is to deploy the Docker containers to a Kubernetes cluster with appropriate scheduling and task management. The second solution is to use GitHub's newly released Github Actions that can support continuous integration and continuous deployment (CI/CD), and thus it should be possible to run student submissions in GitHub's data center, and thus offload our Autograder server.

We want to implement both solutions since it is not clear which is the easiest/best solution, and there is also a cost aspect to running CI/CD on GitHub machinery (that is, it is not clear how much "free credits" we as an academic institution will get from GitHub). The Kubernetes cluster can be run locally on our own machines, but it will require that the student learns how to set that up together with our local system administrator. Henceforth, both technologies, and possibly other alternatives, should be evaluated for the project.

The student should expect that also work on the frontend (React/TypeScript) to adapt it as needed, e.g. to receive notifications about completed test runs etc. But most of the work will probably take place on the backend.

## Reading Material

- [GitHub Actions](https://github.com/features/actions)
- [GitHub CI/CD Actions](https://github.blog/2019-08-08-github-actions-now-supports-ci-cd/)
- [Docker](https://www.docker.com)
- [Kubernetes](https://kubernetes.io)
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
