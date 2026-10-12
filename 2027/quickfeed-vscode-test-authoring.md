# Bachelor: A VSCode Extension for Authoring QuickFeed Tests

## Administrative

- Supervisor: Hein Meling
- Group Composition: 1-3 students (the scope can be adjusted based on the number of students)
- Project period: Spring 2027
- Bachelor thesis

This project focuses on teachers and complements the [student-facing QuickFeed extension][6].

### Prerequisites

- DAT320 Operating systems and systems programming is recommended
- Proficient in Go, since QuickFeed and most course tests are written in Go
- Proficient in TypeScript, or willing to become proficient quickly
- Comfortable with Docker and containers
- Interest in developer tooling and user interface design

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Briefly document significant AI assistance to make provenance clear.

## Background

[QuickFeed][1] is a system developed at UiS that runs tests against student submissions and provides scores and feedback. Teachers maintain assignments, test code, and configuration in course repositories. Checking that these work together before students encounter problems is an important part of preparing a course.

QuickFeed's revised [`qcm` command line tool][4] can run assignment tests locally in Docker and check course repositories, including tests against skeleton code and reference solutions. Teachers can therefore check changes before pushing the assignments and tests repositories. QuickFeed also provides [streaming course logs][5] for following server-side activity and diagnosing problems after a push. These existing capabilities provide a foundation for editor-integrated tools rather than a need to build another test runner.

## Project Description

Develop a VSCode extension that helps teachers prepare and check QuickFeed assignments and tests without leaving their editor. It should complement the existing command line tools and web frontend, making relevant checks and feedback convenient to use during test authoring.

Use TypeScript and the VSCode Extension API, building on QuickFeed's existing tools and APIs. The project should work with the capabilities available when it begins.

### Core Scope

- Make local assignment test runs and course checks accessible from the editor, reusing `qcm` where appropriate.
- Present test results, scores, and diagnostic output so teachers can identify problems in their tests and configuration.
- Provide access to relevant server-side course logs through QuickFeed's existing API.
- Handle credentials securely and report setup, execution, and connection failures clearly.
- Deliver a maintainable, tested extension with instructions for setup, running, and packaging.

Reliable integration is important: local results should remain consistent with QuickFeed, and server feedback should stay useful when connections are interrupted. Students should define practical criteria for correctness, usability, and maintainability in consultation with the supervisor.

### Design Alternatives

Students should explore and justify how to integrate local tools and server feedback, and how best to present results in VSCode. For example, commands and output views offer a different interaction model from the VSCode Testing API. The interface and interaction design are open; prefer reusing existing QuickFeed functionality over duplicating it.

### Possible Extensions

Possible additions include configuration validation, assistance with scoring mistakes, navigation from failures to relevant code, or scaffolding new assignments. Select extensions according to group size, interests, and available time.

## Evaluation

Use automated tests and representative course repositories to check that local runs and checks agree with the underlying QuickFeed tools. Where possible, use a local QuickFeed instance to verify course-log integration, reconnection, and secure credential handling. Evaluate the extension against the agreed criteria and document findings and limitations. An informal usability check with teachers or teaching assistants may be useful, but a comparative user study is not required.

## Reading Material

- [VSCode Extension API][2], including the [Testing API guide][8]
- QuickFeed's [teacher documentation][9], `cmd/qcm`, and `ci` package
- QuickFeed's [course-log changes][5], API definitions in `qf`, and existing frontend under `public/src`
- QuickFeed's [`kit/score` documentation][7] and [issue tracker][3]
- [Get Started with Docker][10]

[1]: https://github.com/quickfeed/quickfeed
[2]: https://code.visualstudio.com/api
[3]: https://github.com/quickfeed/quickfeed/issues
[4]: https://github.com/quickfeed/quickfeed/pull/1623
[5]: https://github.com/quickfeed/quickfeed/pull/1665
[6]: https://github.com/relab/thesis-proposals/blob/master/2027/quickfeed-vscode-extension.md
[7]: https://github.com/quickfeed/quickfeed/blob/master/kit/score/doc.go
[8]: https://code.visualstudio.com/api/extension-guides/testing
[9]: https://github.com/quickfeed/quickfeed/blob/master/doc/teacher.md
[10]: https://www.docker.com/get-started
