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

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

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
- [Hacking with Swift UI](https://www.hackingwithswift.com/)
- [Swift UI Tutorials](https://developer.apple.com/tutorials/app-dev-training)
- [The missing Swift Web UI](http://www.alwaysrightinstitute.com/swiftwebui/)

[1]: https://github.com/autograde/quickfeed
