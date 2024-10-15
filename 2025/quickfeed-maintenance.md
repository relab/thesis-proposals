# Quickfeed Maintenance

## Administrative

- Supervisor: Hein Meling and Jostein Hagen Lindhom
- Group Composition: 1-4 students (the scope can be adjusted based to the number of students)

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

This project is about software maintenance of the QuickFeed system.
In the real-world, you rarely start from scratch, but you often inherit a system that has been developed by others.

The goal is to learn about, through experience, the best practices for software maintenance, including testing, refactoring, and simplifications.
This involves learning about selected parts of the system and making improvements to it.

Students must also follow style guides and best practices for the programming languages and tools used in the project.

### Part 1: Refactoring: Chores and Simplifications

QuickFeed has been developed, as a side project, by the supervisors and many students over the last ten years or so.
A large software project like QuickFeed will always have a fair amount of chores and simplifications that can be done, but are not prioritized.

In this part, the students will be asked to go through the [issue tracker][2] and find issues that are related to simplifications, refactoring, and other chores.
The students will be asked to create a plan for how to solve these issues, including:

- Make sure the issue is well defined; clarify via issue comments if necessary
- If the task is large, break it down into smaller tasks
- Make sure there are sufficient tests, or write tests if necessary
- Implement the task
- Make sure the tests pass and that the CI pipeline is green
- Make sure the code is reviewed by another team member (including the supervisors)

#### Chores: Frontend

- Resolve formatting issues; so that the codebase is consistent and that VSCode can format the code automatically.
- Fix accessibility issues.
- Fix deep source (and other linter) issues.
- Improve Jest testing or add other testing frameworks.
- Replace bootstrap with Tailwind CSS.

### Part 2: Feature Development

Once the majority of the chores and simplifications have been completed, the students will be asked to implement new features.
The features will be selected from the [issue tracker][2] and will be related to the QuickFeed system's functionality.

#### Some Frontend Ideas

- Rearchitect the frontend to use a more modern React architecture?
- Replace the current state management with Redux or Recoil, or some other state management library.

### Summary

The students who take this project is also expected to create issues on the [issue tracker][2] related to this project to make adjustments to the Go code of the QuickFeed server and the frontend code, as necessary to make it easier to facilitate the two parts above.

The students may also be asked to help with some of the existing issues listed on the [issue tracker][2] that fit the project's scope.

The results of this project could be implementation of one or more command line tools written in Go and Dockerfiles.

## Reading Material

- See [this issue](https://github.com/quickfeed/quickfeed/issues/360) on Quickfeed's issue tracker
- Full [list of issues](https://github.com/quickfeed/quickfeed/issues)
- [Get Started with Docker](https://www.docker.com/get-started)
- [Container Networking is simple](https://iximiuz.com/en/posts/container-networking-is-simple/)
- Contact supervisor for more information.

[1]: https://github.com/quickfeed/quickfeed
[2]: https://github.com/quickfeed/quickfeed/issues
