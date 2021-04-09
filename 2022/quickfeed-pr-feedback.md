# Quickfeed Support for Feedback via Pull Requests and Issues

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

In this project, the main goal is to add support for manual and automated feedback directly on a Pull Request on GitHub.
Further, we also want support for creating issues directly on student repositories.
Quickfeed has built a custom source control management (SCM) API for interacting with GitHub and possibly other source repositories.
Quickfeed's `scm` package currently only supports GitHub via [Google's go-github library][2].

This project has these milestones:

- Review the existing SCM API and the GitHub implementation
- Review Quickfeed's use of the SCM API to find possible simplifications of the SCM API
- Expand the SCM API and corresponding Quickfeed implementation to support
  - Pull Requests as described in [this issue][4]
  - Create GitHub Issues as described in [this issue][5]

GitHub's Pull Request page can be extended with additional details via GitHub actions.
In this project, we envision providing more precise feedback on specific parts of the code via the Pull Request interface.
Similarly, we can also create GitHub Issues directly on a student's repository, e.g., to support multiple-choice questions that Quickfeed can automatically grade.

A partial GitLab implementation of the SCM API exists using [xanzy's go-gitlab library][3].
We have focused our efforts on GitHub support so far. However, if time allows, a possible extension of this project is to:

- Add support for GitLab

The implementation language is mainly Go.

## Reading material

- See [this issue](https://github.com/autograde/quickfeed/issues/360) on Quickfeed's issue tracker
- Full [list of issues](https://github.com/autograde/quickfeed/issues)
- [Get Started with Docker](https://www.docker.com/get-started)
- [Container Networking is simple](https://iximiuz.com/en/posts/container-networking-is-simple/)
- [Get Started with Ansible](https://www.ansible.com/resources/get-started)
- Contact supervisor for more information.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/google/go-github
[3]: https://github.com/xanzy/go-gitlab
[4]: https://github.com/autograde/quickfeed/issues/416
[5]: https://github.com/autograde/quickfeed/issues/302
