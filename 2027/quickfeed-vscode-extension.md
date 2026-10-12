# Bachelor: A VSCode Extension for QuickFeed

## Administrative

- Supervisor: Hein Meling
- Group Composition: 1-3 students (the scope can be adjusted based on the number of students)
- Project period: Spring 2027
- Bachelor thesis

This project focuses on students and complements the [test-authoring extension for teachers][15].

### Prerequisites

- DAT310 Web programming is recommended
- DAT320 Operating systems and systems programming is recommended
- Proficient in TypeScript, or willing to become proficient quickly
- Familiarity with Go, Protocol Buffers, and RPC is useful for understanding QuickFeed's API
- Interest in developer tooling and user interface design

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Briefly document significant AI assistance to make provenance clear.

## Background

[QuickFeed][1] is a system developed at UiS that runs tests against student submissions and provides scores and feedback. Students currently view this feedback in its web frontend, switching between the browser and their code when investigating failures.

QuickFeed's Go backend exposes a [Connect RPC][2] API defined with [Protocol Buffers][3]. The API provides submission status, scores, per-test score records, build information and logs, and a `SubmissionStream` for live updates. Third-party clients can authenticate with a GitHub access token; see `web/interceptor/token_auth.go`.

Planned improvements to per-test results and the Go scoring API ([PR #1655][16], [issue #1681][17]) may provide additional opportunities. The project should work with the capabilities available when it begins.

## Project Description

Develop a VSCode extension that helps students access QuickFeed feedback without leaving their editor. It should complement the web frontend rather than reproduce it, making relevant results easy to find and interpret.

Use TypeScript and the VSCode Extension API to connect directly to the existing QuickFeed server from the Node.js extension host.

### Core Scope

- Give students convenient access to their courses, assignments, submissions, scores, per-test results, and build logs.
- Keep submission feedback current without requiring manual refreshes.
- Handle authentication and credentials securely.
- Deliver a maintainable, tested extension with instructions for running and packaging it.

Students should explore and justify their design choices, including how to present feedback and handle authentication and updates. The interface and interaction design are open.

### Possible Extensions

Where the available output supports it, help students relate failed tests to source locations. Other possibilities include VSCode Testing API integration or support for additional test-output formats. Select extensions according to group size, interests, and available time.

## Evaluation

Use automated tests and, where possible, a local QuickFeed instance to check that displayed results match QuickFeed, updates arrive reliably, and credentials are handled securely. Evaluate any code-navigation features with representative test output. Document the findings and limitations; an informal usability check may be useful, but a comparative user study is not required.

## Reading Material

- [VSCode Extension API][8], including the [Testing API guide][9]
- [Connect RPC][2] and [protobuf-es][4]
- QuickFeed's [issue tracker][10], [service definitions][5], [data types][6], and existing frontend under `public/src`
- Earlier QuickFeed client proposals: [command line client][13] and [SwiftUI app][14]

[1]: https://github.com/quickfeed/quickfeed
[2]: https://connectrpc.com/docs/web/getting-started
[3]: https://protobuf.dev
[4]: https://github.com/bufbuild/protobuf-es
[5]: https://github.com/quickfeed/quickfeed/blob/master/qf/quickfeed.proto
[6]: https://github.com/quickfeed/quickfeed/blob/master/qf/types.proto

[8]: https://code.visualstudio.com/api
[9]: https://code.visualstudio.com/api/extension-guides/testing
[10]: https://github.com/quickfeed/quickfeed/issues

[13]: https://github.com/relab/thesis-proposals/blob/master/2022/quickfeed-cli.md
[14]: https://github.com/relab/thesis-proposals/blob/master/2021/quickfeed-swift.md
[15]: https://github.com/relab/thesis-proposals/blob/master/2027/quickfeed-vscode-test-authoring.md
[16]: https://github.com/quickfeed/quickfeed/pull/1655
[17]: https://github.com/quickfeed/quickfeed/issues/1681
