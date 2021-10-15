# Quickfeed Frontend Design Improvements and Robustness Testing

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT220 Databases
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

The frontend code in Quickfeed is written in Typescript and uses React.
However, there are virtually no tests for the frontend code.

The goal in this project is to write tests for the frontend code to improve code coverage, and to make the frontend code more robust.
Further, the code under test should be improved where appropriate.

The other goal of the project is to improve the design and usability of the frontend.

Milestones:

- Review state of the art in frontend testing of React components
- Write tests for the frontend code
- Improve the frontend code
- Evaluate the code quality improvement obtained
- Simplify the design and layout
- Implement various missing frontend features and design improvements; see [issue tracker][2]
- Improve the usability of the frontend
  - For example, add mechanism to view the log for each test separately

There are now two React-based frontend implementations, and this project should mainly focus on the new implementation; see [this Pull Request](https://github.com/autograde/quickfeed/pull/502).

The implementation is mainly based on TypeScript, React, and [overmind.js][3].

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/autograde/quickfeed/labels/frontend
[3]: https://overmindjs.org
