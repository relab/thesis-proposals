# Quickfeed: Desktop User Interface with SwiftUI

## Administrative

- Supervisor: Hein Meling
- Group Composition: 2 or 3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended.
- DAT310 Web programming is recommended.
- Be interest in user interface design.
- Access to modern Mac computer with Xcode for development is required.

## Expected Learning Outcomes

Learn how to design macOS and iOS apps using Xcode, Swift and SwiftUI, or other iOS development environments.
Students are expected to learn these technologies on their own.

## Background on Quickfeed (also known as Autograder)

Quickfeed is a system developed at UiS to automatically evaluate student hand-ins.
Quickfeed is able to run a set of tests against any hand-in delivered by students and will provide a score and feedback for the students.
We have recently reimplemented both the Quickfeed backend and frontend to improve its robustness.
In particular, the backend is now based on a gRPC-based server, a SQL database, the backend interacts with GitHub (and GitLab).
The backend use the gRPC-web framework for handling client requests (with a few remaining REST interface calls).
We use Docker containers to run student code.
On the frontend, we used the Typescript language along with the React framework from Facebook to avoid many of the concerns with the Javascript language.

## Project description

In this project we aim to design a new user interface for Quickfeed, specifically using the new SwiftUI design framework from Apple.
The target app should be a desktop app primarily for macOS, but iOS may also be supported, and should be possible with SwiftUI.

The app must be able to connect to the Quickfeed server over a gRPC-based connection to fetch information needed for presentation in the Quickfeed app.
The feature set to implement should be at least same to the set already available in the current React-based web app, but additional features could be added.
For instance, the current app supports gRPC, but not streaming data from the server to the client.
It would be highly desirable to support updating the user interface when the backend CI system has completed the test execution for a student's assignment.
That way, students and teachers don't need to reload the page to get updated information.

Implementation language is Swift and SwiftUI.

## Reading material

- [gRPC Swift](https://github.com/grpc/grpc-swift)
- [Swift Protobuf](https://github.com/apple/swift-protobuf)
- [Swift UI](https://developer.apple.com/xcode/swiftui)
- [Swift UI Doc](https://developer.apple.com/documentation/swiftui)
