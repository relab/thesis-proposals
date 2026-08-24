# Bachelor: A VSCode Extension for Authoring QuickFeed Tests

## Administrative

- Supervisor: Hein Meling
- Group Composition: 1-3 students (the scope can be adjusted based on the number of students)
- Project period: Spring 2027
- Bachelor thesis

This project is a sibling of the [student-facing QuickFeed extension][6], and the two can be taken by separate groups.
Both build a VSCode extension for QuickFeed, but they target different users and different problems.

### Prerequisites

- DAT320 Operating systems and systems programming is recommended
- Proficient in Go, since QuickFeed and most course tests are written in Go
- Proficient in TypeScript, or willing to become proficient quickly
- Comfortable with Docker and containers

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Briefly document significant AI assistance to make provenance clear.

## Background on QuickFeed

[QuickFeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
QuickFeed runs a set of tests against any hand-in delivered by students and provides a score and feedback.
The backend is a Go server that builds and runs each submission inside a Docker container.

A teacher configures a course through a *tests repository*, which QuickFeed clones and walks.
Per assignment, it contains:

- A `run.sh` script naming the Docker image and the commands to execute, with a course-wide default under `scripts/`.
  The script sees the environment variables `TESTS`, `ASSIGNMENTS`, `SUBMITTED`, and `CURRENT`, which point at the cloned repositories and the current assignment; see `ci/parse_script.go`.
- A `Dockerfile` at the repository root, defining the course image.
- An `assignment.json` file with the assignment order, deadline, group flag, auto-approve limit, and container timeout.
- An optional `criteria.json` file describing the grading criteria used for manual review.
- The test code itself, which registers each test with QuickFeed's [`kit/score`][7] package to report points and weights.

## Motivation and Research Question

Writing the tests for an assignment is the most error-prone part of running a QuickFeed course, and the feedback loop for the teacher is far worse than the one for the student.
To find out whether a run script works, whether the image builds, or whether the scores come out as intended, the teacher must commit to the tests repository, wait for QuickFeed to pick it up, trigger a run against some submission, and read the resulting build log.
Scoring mistakes are especially costly: a test that is never registered, or a weight that is not what the teacher believed, produces a plausible-looking but wrong score, and is often discovered only after students have submitted.

The container that QuickFeed runs is not magic; it is a Docker image, a bind-mounted directory, and a shell script.
The teacher's own machine can run the same thing.

> How much does a local, editor-integrated test-authoring environment reduce the number of commit–run–inspect round trips, and the time, needed to develop a working QuickFeed assignment, compared to the current workflow of committing to the tests repository?

A positive result is plausible because the entire execution environment is already reproducible from the tests repository, and because the errors this targets are exactly the kind a fast local loop catches.
The main risk is fidelity: a local run that does not behave like the server is worse than no local run at all, since it produces false confidence.
Part A therefore treats fidelity as the primary requirement, and Part C measures it directly.

## Project Description

### Part A: Local Test Execution

- Reproduce a QuickFeed test run on the teacher's machine: build the course image from the `Dockerfile`, mount the tests, assignments, and submitted code the way the server does, run the assignment's `run.sh`, and capture the output.
- Investigate reusing QuickFeed's own `ci` package through a small helper binary, rather than reimplementing container setup in TypeScript.
  Argue the trade-off: a helper binary keeps local and server behaviour from drifting apart, but adds a build step and a platform-specific artifact to ship with the extension.
- Run against a chosen input: a reference solution, an empty skeleton, or a real student repository, selected from the editor.
- Parse the resulting score records and compute the total the way QuickFeed does, so the teacher sees the score a student would receive.

### Part B: The Extension

- Commands to run the current assignment's tests locally and to stream the container output into the editor.
- **Catch scoring mistakes before students do**, which is the core of the project.
  Analyse the assignment's Go test code and report, as diagnostics in the editor: tests that are registered but do not exist, scored tests that were never registered, a missing call to print the test information, and the resulting distribution of maximum points and weights.
- Validation and completion for `assignment.json` and `criteria.json`, so that a malformed deadline or a misspelled field is reported while editing rather than when QuickFeed next syncs the repository.
- A score preview: the per-test maximum and weight, and the total a partially passing submission would receive.
- Packaging: extension manifest, tests running in the VSCode test host, and a documented path to the Marketplace.

Optional, if time allows: a command that scaffolds a new assignment folder with a valid configuration, run script, and a skeleton scored test.

### Part C: Evaluation

- **Fidelity.**
  For a set of existing assignments and submissions, check that the scores computed by a local run match those the QuickFeed server computes.
  This is the correctness result the rest of the project depends on, and it should be reported as a table, not a claim.
- **Retrospective baseline.**
  Mine the commit history of existing course tests repositories, which the supervisor can provide, and count how many commits are fixes to run scripts, Dockerfiles, or scoring.
  These are the round trips the extension is meant to remove, and they can be counted without involving human subjects.
- **Round-trip time.**
  Measure the wall-clock time of a local run against the time from commit to visible feedback under the current workflow.
- Optionally, a small study with teachers or teaching assistants authoring an assignment with and without the extension.
  A bachelor-scale study will not support strong significance claims; report the sample size honestly and treat the results as qualitative.

### Scope

- Core: Part A, local test execution and the run command in Part B, and the fidelity and round-trip measurements in Part C.
- Optional: the scoring diagnostics, configuration validation, score preview, scaffolding command, and the user study.

## Reading Material

- [VSCode Extension API][2] and the [diagnostics API][8]
- QuickFeed's `ci` package, and the [`kit/score` documentation][7]
- QuickFeed's [issue tracker][3]
- [Get Started with Docker][9]
- Paiva, Leal, and Figueira, [*Automated Assessment in Computer Science Education: A State-of-the-Art Review*][4], ACM Transactions on Computing Education, 2022
- Keuning, Jeuring, and Heeren, [*A Systematic Literature Review of Automated Feedback Generation for Programming Exercises*][5], ACM Transactions on Computing Education, 2018

[1]: https://github.com/quickfeed/quickfeed
[2]: https://code.visualstudio.com/api
[3]: https://github.com/quickfeed/quickfeed/issues
[4]: https://dl.acm.org/doi/10.1145/3513140
[5]: https://dl.acm.org/doi/10.1145/3231711
[6]: https://github.com/relab/thesis-proposals/blob/master/2027/quickfeed-vscode-extension.md
[7]: https://github.com/quickfeed/quickfeed/blob/master/kit/score/doc.go
[8]: https://code.visualstudio.com/api/references/vscode-api#Diagnostic
[9]: https://www.docker.com/get-started
