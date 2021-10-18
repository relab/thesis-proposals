# Quickfeed Code Review Data Collection and Machine Learning Model Generation

## Administrative

- Supervisor: Hein Meling and Vinay Setty
- Group Composition: 1 or 2 master students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT310 Web programming is recommended
- DATxxx Machine Learning
- Proficient in the Go programming language
- Relevant Machine Learning tools

## Background on Quickfeed (also known as Autograder)

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

The goal of this project is to design a system that can help students to improve their code quality and to improve their code reviewing skills.
To achieve this goal, you should design a system that can be used to collect data about student code and code reviews.
Specifically, we want to collect information about student submitted code, code reviewer's assessment of the code, and other aspects of the code review process.
The collected data should be used to train a machine learning model that can be used to predict the quality of future student submitted code, and the quality of code reviews performed by students and teachers.

The data about student code may include the source code, statistics about the code, and static code analysis results.
The code reviewers may specify in the review text some form of score that the machine learning model can use for training.

In an ongoing project, we are developing mechanisms for manual code review by student peers and teachers via the traditional Pull Request mechanism.
The students that choose this project are expected to also contribute to this ongoing project, to ensure that the relevant mechanisms for code reviewing can be used for the data collection part.
Specifically, different code review comments must be correlated with a specific code segment and the code quality should be rated in some way.

## Reading material

- See [this design document](https://github.com/AdilKhurshid/quickfeed/blob/github_enhancement/doc/github-enhancement.md) for more information about the ongoing project.
- See also Pull Requests and code reviewing as described in [this issue][4]
- Contact supervisor for more information.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/google/go-github
[3]: https://github.com/xanzy/go-gitlab
[4]: https://github.com/autograde/quickfeed/issues/416
[5]: https://github.com/autograde/quickfeed/issues/302
