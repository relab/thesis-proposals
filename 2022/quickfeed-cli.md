# Quickfeed: Command Line Client for Teachers and Students

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 or 3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended.
- Strong interest in Go programming.

## Expected Learning Outcomes

Become proficient in Go programming.

## Background on Quickfeed (also known as Autograder)

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

Motivation: Quickfeed's React-based frontend has a high maintenance cost, consisting of more than 10k lines of code.

In this project, the goal is to create an easy to use command line tool for interacting with Quickfeed.
The interaction must be done over Quickfeed's gRPC-based API, or directly towards GitHub's API, as appropriate for the different features.

The tool must be able to connect to the Quickfeed server over a gRPC-based connection to fetch information to be displayed in the terminal.
The feature set to implement should be similar to the set already available in the current React web app and SwiftUI app, but additional features could be added.
The tool should be able to receive updates in real-time and display these as they arrive.

The project should focus on a modular design, documentation and testing.

This project has these milestones and design ideas:

- Decide on a short and unique name for the tool that is easy to type
- Decide on Go library for processing command line arguments, or use `flags` package
- Decide on Go library for pretty-printing data retrieved from Quickfeed, or use `text/tabwriter` package
- Decide if the tool could work with [fzf][2]
- Design the command structure and decide which commands to be supported
  - The tool should follow designs similar to `git` and `gh`
  - Example commands could be:
    - `qf view results`
    - `qf view results -s ola`
    - `qf view students`
    - `qf view lab5`
    - `qf view lab5 -s ola`
    - `qf approve lab5 -s ola`
- Create process for setting up test environment for the command line tool
  - Since each user/developer of this tool need to access a test instance of Quickfeed and corresponding test repositories, the project must simplify the set up process
- Repositories and Quickfeed instance can possibly be configured with environment variables, but as few as possible
  - A configuration file could also be stored in `.qfconfig` or similar
  - Configuration format should take advantage of [cuelang][4]
- Users should be authenticated using personal access token
- The tool should ideally work on all major platforms (Linux, macOS, Windows)

Implementation language is Go.

## Reading material

- [cobra](https://github.com/spf13/cobra)
- [urfave/cli](https://github.com/urfave/cli)
- [viper](https://github.com/spf13/viper)
- [cuelang][4]
- [fzf][2]
- [Building Command Line Interfaces using Go][3]

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/junegunn/fzf
[3]: https://medium.com/swlh/building-command-line-interfaces-using-go-ce6a75d60bf5
[4]: https://cuelang.org
