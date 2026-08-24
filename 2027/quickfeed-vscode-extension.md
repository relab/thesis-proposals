# Bachelor: A VSCode Extension for QuickFeed

## Administrative

- Supervisor: Hein Meling
- Group Composition: 1-3 students (the scope can be adjusted based on the number of students)
- Project period: Spring 2027
- Bachelor thesis

This project is a sibling of the [test-authoring extension for teachers][15], and the two can be taken by separate groups.
Both build a VSCode extension for QuickFeed, but they target different users and different problems.

### Prerequisites

- DAT310 Web programming is recommended
- DAT320 Operating systems and systems programming is recommended
- Proficient in TypeScript, or willing to become proficient quickly
- Some Go programming is useful for the server-side parts
- Interest in developer tooling and user interface design

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Briefly document significant AI assistance to make provenance clear.

## Background on QuickFeed

[QuickFeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
QuickFeed runs a set of tests against any hand-in delivered by students and provides a score and feedback.
The backend is a Go server that speaks [Connect RPC][2] over [Protocol Buffers][3]; the frontend is a TypeScript and React web application using [protobuf-es][4].

Three details matter for this project, all visible in [`qf/quickfeed.proto`][5] and [`qf/types.proto`][6]:

- A `Submission` already carries the `score`, the `Status` (approved, rejected, revision), the per-test `Score` records, and a `BuildInfo` record with the full `BuildLog`.
- `SubmissionStream` is a server-streaming RPC that pushes updated submissions to a connected client as soon as a CI run finishes.
- Third-party clients can already authenticate by sending a GitHub access token in the `Authorization` header; see `web/interceptor/token_auth.go`.

## Motivation and Research Question

Students work in their editor, but QuickFeed's feedback lives in a browser tab.
The loop is: push, switch to the browser, find the assignment, expand the build log, translate a failing test name back into a file and line number, and switch back.
VSCode can host all of this natively: tree views in the sidebar, a Testing API that populates the Test Explorer, and diagnostics that appear in the Problems panel and as markers in the source.
A QuickFeed extension is the only client that can put feedback *next to the code the feedback is about*.

> How much does an editor-integrated feedback client reduce the time and the number of context switches a student needs to go from a failing test to a corrected submission, compared to QuickFeed's web frontend?

A positive result is plausible: the data and the streaming RPC already exist, VSCode provides exactly the right primitives, and removing an application switch from a tight iteration loop is the kind of effect developer tooling reliably produces.
The risk is building a browser inside the editor: a webview that reproduces the web page without shortening the loop.
Part B is designed to avoid that, and Part C measures context switches rather than satisfaction alone.

## Project Description

### Part A: Client API and Authentication

- Generate TypeScript bindings from QuickFeed's `.proto` files and build a small, tested client library for the extension host, which is a Node process rather than a browser.
- Identify which parts of the existing `QuickFeedService` API the extension actually needs.
  The student-facing subset is much smaller than the full service, and knowing it keeps the client library small.
- Authenticate using VSCode's built-in GitHub authentication provider, so students never copy tokens by hand, and keep secrets in VSCode's `SecretStorage`.
- Consume `SubmissionStream`, handling reconnection, token expiry, and offline use.

### Part B: The Extension

- A sidebar tree view of courses, assignments, and the student's own submissions, with score, status, and deadline.
- Per-test results shown as a readable table, and access to the full build log.
- **Test results where the code is**, which is the core of the project.
  Investigate and compare two mechanisms: the VSCode *Testing API*, so server-side results appear in the Test Explorer next to locally run tests, and *diagnostics*, which put a marker on the offending line in the source file.
  Diagnostics require parsing the build log to recover file names and line numbers, and the log format depends on the language and test framework the course uses.
  Start with Go, whose `go test` output already reports the file and line of each failure, and structure the parser so that other languages can be added later.
- Live updates: notify the student when a CI run completes, with no manual refresh.
- Packaging: extension manifest, tests running in the VSCode test host, and a documented path to the Marketplace.

### Part C: Evaluation

Use QuickFeed's web frontend as the baseline.

- Measure the time from CI completion on the server until feedback is visible in each client, over repeated runs against a local QuickFeed instance.
- Enumerate the student-facing features of the web frontend and report which the extension covers, and at what code size.
- Run a small user study: volunteers fix seeded bugs in prepared assignments, half the tasks with each client, with the order counterbalanced between participants.
  Measure time on task, switches between editor and browser, and submissions needed before approval, and collect a [System Usability Scale][7] score.
- Report the sample size honestly.
  A bachelor-scale study will not support strong significance claims; descriptive statistics and qualitative observations are the appropriate output.

### Scope

- Core: Part A, the tree view and log display in Part B, one of the two test-result mechanisms, and the measurements in Part C.
- Optional: the second test-result mechanism, the user study, and local test execution.

## Reading Material

- [VSCode Extension API][8] and the [Testing API guide][9]
- [Connect RPC][2] and [protobuf-es][4]
- QuickFeed's [issue tracker][10] and the existing frontend under `public/src`
- Paiva, Leal, and Figueira, [*Automated Assessment in Computer Science Education: A State-of-the-Art Review*][11], ACM Transactions on Computing Education, 2022
- Keuning, Jeuring, and Heeren, [*A Systematic Literature Review of Automated Feedback Generation for Programming Exercises*][12], ACM Transactions on Computing Education, 2018
- Earlier QuickFeed client proposals: [command line client][13] and [SwiftUI app][14]

[1]: https://github.com/quickfeed/quickfeed
[2]: https://connectrpc.com/docs/web/getting-started
[3]: https://protobuf.dev
[4]: https://github.com/bufbuild/protobuf-es
[5]: https://github.com/quickfeed/quickfeed/blob/master/qf/quickfeed.proto
[6]: https://github.com/quickfeed/quickfeed/blob/master/qf/types.proto
[7]: https://en.wikipedia.org/wiki/System_usability_scale
[8]: https://code.visualstudio.com/api
[9]: https://code.visualstudio.com/api/extension-guides/testing
[10]: https://github.com/quickfeed/quickfeed/issues
[11]: https://dl.acm.org/doi/10.1145/3513140
[12]: https://dl.acm.org/doi/10.1145/3231711
[13]: https://github.com/relab/thesis-proposals/blob/master/2022/quickfeed-cli.md
[14]: https://github.com/relab/thesis-proposals/blob/master/2021/quickfeed-swift.md
[15]: https://github.com/relab/thesis-proposals/blob/master/2027/quickfeed-vscode-test-authoring.md
