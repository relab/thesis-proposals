# Quickfeed Support for Feedback via Pull Requests and Issues

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 or 3 students (or 1 for master's thesis)

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

In this project, the main goal is to add support for manual and automated feedback directly on a Pull Request in GitHub.
Further, we also want support for creating issues directly on student repositories.
Quickfeed has built a custom source control management (SCM) API for interacting with GitHub and possibly other source repositories.
Quickfeed's `scm` package currently only supports GitHub via [Google's go-github library][2].

This project has these milestones:

- Review the existing SCM API and the GitHub implementation
- Review Quickfeed's use of the SCM API to find possible simplifications of the SCM API
- Expand the SCM API and corresponding Quickfeed implementation to support
  - Pull Requests as described in [this issue][4] and [this issue][15]
  - Create GitHub Issues as described in [this issue][5]

GitHub's Pull Request page can be extended with additional details via GitHub actions.
In this project, we envision providing more precise feedback on specific parts of the code via the Pull Request interface.
Similarly, we can also create GitHub Issues directly on a student's repository, e.g., to support multiple-choice questions that Quickfeed can automatically grade.

The implementation language is mainly Go.

## Reading material

- [Report about Pull Requests and Issues in QuickFeed][7]
- [QuickFeed Issue Creation][13]
- [QuickFeed User Manual for Teachers][14]
- [Peer Code Review as Formative Assessment: A Case Study from a Database
Course Project][11]
- [GitHub Classroom][8]

## Related Tools and Libraries

- [Reviewdog][6] seems interesting and related
- [GitHub's command line tool][9]
- [Google's client library for accessing the GitHub API v3][10]
- [GitHub Webhooks][12]

[1]: https://github.com/quickfeed/quickfeed
[2]: https://github.com/google/go-github
[3]: https://github.com/xanzy/go-gitlab
[4]: https://github.com/quickfeed/quickfeed/issues/416
[5]: https://github.com/quickfeed/quickfeed/issues/302
[6]: https://github.com/reviewdog/reviewdog
[7]: https://www.dropbox.com/s/h1tpw8425sp5clp/khurshidadil-pull-request-support.pdf?dl=0
[8]: https://classroom.github.com/classrooms
[9]: https://github.com/cli/cli
[10]: https://github.com/google/go-github
[11]: https://ojs.bibsys.no/index.php/NIK/article/view/902
[12]: https://docs.github.com/en/developers/webhooks-and-events/webhooks/about-webhooks
[13]: https://github.com/AdilKhurshid/quickfeed/tree/github_enhancement
[14]: https://github.com/quickfeed/quickfeed/blob/master/doc/teacher.md
[15]: https://github.com/quickfeed/quickfeed/issues/458
