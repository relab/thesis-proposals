# Bachelor: Quickfeed's Database Revisited

## Administrative

- Supervisor: Hein Meling and Jostein Hagen Lindhom
- Group Composition: 1-3 students (the scope can be adjusted based to the number of students)
- Bachelor thesis

The project involves working with a moderately complex codebase, but is mainly restricted to the database layer.

### Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT220 Databases
- DAT310 Web programming is recommended
- Proficient in the Go programming language
- Proficiency in use of AI tools (e.g., ChatGPT, GitHub Copilot)

### AI Tools

You are expected to use AI tools in this project.
However, you are responsible for the correctness and quality of the code and the report.
Verify AI-generated code and statements with tests, measurements, and appropriate citations in the report.
Be prepared to explain and justify design decisions and any non-trivial generated code during code reviews.
Inaccuracies, misleading content, or design and stylistic similarities that indicate significant reliance on AI without critical review may negatively affect the grade.
Briefly document significant AI assistance (usage log and citations) to make provenance clear.

## Background on Quickfeed

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

This project takes a scientific, comparative approach to the database layer of Quickfeed: design and evaluate multiple database variants, measure their performance and robustness, and document their strengths and weaknesses with clear methodology and reproducible benchmarks.
The outcome should be a well-argued recommendation for the technology stack that best matches Quickfeed’s requirements.

Currently, Quickfeed uses a SQLite (sqlite3) database stored in a single file.
This has been a good choice in that we have not experienced database inconsistencies.
Quickfeed interacts with the database via [GORM][3], a popular ORM for Go.
While GORM has been a decent pragmatic choice, it suffers from poor documentation, heavy use of reflection, requires manipulating struct tags, and it has been at the core of several hard-to-find bugs.
These observations motivate a careful reassessment of the database stack.
Others have also raised concerns about the use of ORMs, see for example [Wozniak’s critique of ORMs][4] and [Alan Illing’s discussion of dropping the ORM][9].

QuickFeed's database schema is defined using [Protocol Buffers][14] (protobuf) message types, which allows us to reuse the same data structures (types) across the entire QuickFeed system.
That is, same struct types are used for interacting with the database, in the QuickFeed server _business logic_, and on the Typescript-based frontend.
This has many benefits, among them avoiding to translate between different types manually.

However, we want to make database operations even more robust with improved transaction support and stronger guarantees.
To that end, the project is split into two concise parts, each with clear deliverables and measurements.

### Part A: Developer experience, safety, and maintainability

- Conduct a literature review to identify key concerns and criteria for evaluating ORMs versus SQL-first approaches.
- Review and simplify the current ER model/schema and stabilize the database API surface.
  - This includes reviewing known [database-related issues][15] in the Quickfeed issue tracker.
- Evaluate programmability and type safety, including compatibility with protobuf-generated types, avoidance of reflection, and compile-time guarantees.
- Assess tool maturity and maintenance: documentation quality, ecosystem health, release cadence, and migration workflows.
- Technologies to consider for comparison: improved [GORM][3] baseline, [ent][7] with [gRPC/protobuf integration][8], hand-written SQL, [Gel][13], [sqlc][12] ([sqlc docs][10]), ([SQLBoiler][6]), [bob][11], and [dbtpl][5].
  - Selected variants should implement the same Quickfeed database API [database.go][2] to enable apples-to-apples comparisons.
  - Note that the [ent framework][7] has native support for interacting with protobuf types; see [ent’s gRPC/protobuf integration documentation][8].
- Document migration tooling and operational procedures per stack (e.g., ent migrations, GORM auto-migrate or third-party tools, sqlc migrations, and native engine tools).
- Summarize strengths and weaknesses with short code artifacts that illustrate typical Quickfeed operations.

### Part B: Performance and robustness under realistic workloads

- Establish a baseline by benchmarking the current GORM+SQLite module with representative Quickfeed scenarios.
- Ensure transactional correctness and add concurrency tests (e.g., multiple simultaneous submissions and grading) that verify invariants.
- Execute cross-variant benchmarks: latency and throughput under concurrency, sensitivity to N+1 patterns, and cold versus warm cache behavior.
- Compare alternative engines while keeping the same schema and API: SQLite, MySQL/MariaDB, PostgreSQL, and CockroachDB.
- Produce a reproducible benchmark harness and an evidence-based recommendation for the preferred stack.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/autograde/quickfeed/blob/master/database/database.go
[3]: https://gorm.io
[4]: https://wozniak.ca/blog/2014/08/03/What-ORMs-have-taught-me-just-learn-SQL/
[5]: https://github.com/xo/dbtpl
[6]: https://github.com/aarondl/sqlboiler
[7]: https://entgo.io
[8]: https://entgo.io/docs/grpc-intro
[9]: https://alanilling.com/exiting-the-vietnam-of-programming-our-journey-in-dropping-the-orm-in-golang-3ce7dff24a0f
[10]: https://docs.sqlc.dev/en/stable/index.html
[11]: https://github.com/stephenafamo/bob
[12]: https://github.com/sqlc-dev/sqlc
[13]: https://docs.geldata.com
[14]: https://protobuf.dev
[15]: https://github.com/quickfeed/quickfeed/issues?q=is%3Aissue%20state%3Aopen%20label%3Adatabase
