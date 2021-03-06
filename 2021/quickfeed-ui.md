# Quickfeed: Redesigned Web Frontend

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 or 3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended.
- Be interest in user interface design.
- DAT310 Web programming is recommended.

## Expected Learning Outcomes

Learn how to design dynamic web applications.
Students are expected to learn these technologies on their own.

## Background on Quickfeed (also known as Autograder)

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

In this project, the goal is to design a revised user interface for Quickfeed.
The project should assess different web UI frameworks, including React, Vue.js, Overmind, Vugu and possibly others.
The focus is the build a robust and maintainable web app for Quickfeed, that handles state management without passing state information across numerous components.

The app must be able to connect to the Quickfeed server over a gRPC-based connection to fetch information needed for presentation in the Quickfeed app.
The feature set to implement should be at least same to the set already available in the current React web app, but additional features could be added.
For instance, the current app already supports gRPC, but not streaming data from the server to the client.
It would be highly desirable to support updating the frontend when the backend CI system has completed the test execution for a student's assignment.
That way, students and teachers don't need to reload the page to get updated information.

Implementation language should be either Go or TypeScript.

## Reading material

- [overmind.js](https://overmindjs.org)
- [vugu](https://www.vugu.org)
- [grpc-web](https://github.com/grpc/grpc-web)
- [Wails](https://wails.app/)
- [React patterns](https://reactpatterns.com/)
- [Stencile vs React](https://www.wix.engineering/post/is-stencil-a-better-react)
- [Redux (React)](https://redux.js.org/)
- [Adopting TypeScript](https://www.techatbloomberg.com/blog/10-insights-adopting-typescript-at-scale/)
- [Vue vs React](https://www.monterail.com/blog/vue-vs-react-2020)
- [Preact](https://preactjs.com/)

[1]: https://github.com/autograde/quickfeed
