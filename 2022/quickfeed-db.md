# Quickfeed Database Revisited

## Administrative

- Supervisor: Hein Meling and Erlend Tøssebro
- Group Composition: 2-3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT220 Databases
- DAT310 Web programming is recommended
- Proficient in the Go programming language

## Background on Quickfeed (also known as Autograder)

[Quickfeed][1] is a system developed at UiS to evaluate student hand-ins automatically.
Quickfeed can run a set of tests against any hand-in delivered by students and provide a score and feedback.
We have reimplemented both the Quickfeed backend and frontend to improve its robustness.
The backend is a gRPC-based server with a SQL database, which interacts with GitHub.
The backend uses the gRPC-web framework for handling client requests.
We use Docker containers to run student code.
On the frontend, we used the Typescript language and the React framework from Facebook.

## Project description

In this project, the goal is to review, conduct robustness and performance tests, and revise the database module of Quickfeed.

Currently, Quickfeed uses a sqlite3 database stored in a single file.
This has been a good choice in that we have not experienced any database inconsistencies.
Quickfeed interacts with the database via [GORM][3], a popular Object-Relational Mapping library.
This library has served us well so far.

QuickFeed's database schema is defined using [protobuf][9] message types, which allows us to reuse the same data structures (types) across the entire QuickFeed system.
That is, same struct types are used for interacting with the database, in the QuickFeed server _business logic_, and on the Typescript-based frontend.
This has many benefits, among them avoiding to translate between different types manually.

However, we want to make the database transactions needed by Quickfeed even more robust with added tests and improved transaction support.
To that end, this project has these milestones:

- Review and revise the current database ER model/schema and database API for simplification and performance
- Benchmark the database module in its current state
- Ensure that all database accesses use transactions to prevent inconsistencies
- Implement additional integration and robustness tests, e.g., ability to handle multiple concurrent transactions without compromising consistency
- Benchmark the performance of the different variants of the database
- Implement the revised database design using the new [ent.][7] entity framework for Go.
- Benchmark and compare the performance of both GORM and ent.

Note that the [ent. framework][7] has native support for interacting with protobuf types; [see here][8].
The implementation language is mainly Go.

### Extended project

Depending on the project team's size (more than 3 students), the project can be expanded in different directions, e.g., testing with different databases such as MySQL, PostgreSQL, or CockroachDB.
Another direction could be implementing a NoSQL variant of the database schema and comparing it against the SQL variants.
This extension would entail the following additional milestones:

- Implement the same [database API][2] using hand-written SQL statements
- Discuss pro/con with ORM vs pure SQL queries, e.g., [see here][4], [here][5], [here][6], [here][9], and [here][10].
- Discuss ideas for a generics-based ORM framework

The project should also review the database schema and API from a security perspective to ensure that it does not leak sensitive information.
Further, the project should also define policies, procedures, and mechanisms to handle database migration/schema changes.

The implementation language is mainly Go and SQL.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/autograde/quickfeed/blob/master/database/database.go
[3]: https://gorm.io
[4]: https://wozniak.ca/blog/2014/08/03/What-ORMs-have-taught-me-just-learn-SQL/
[5]: https://github.com/xo/xo
[6]: https://github.com/volatiletech/sqlboiler
[9]: https://alanilling.com/exiting-the-vietnam-of-programming-our-journey-in-dropping-the-orm-in-golang-3ce7dff24a0f
[10]: https://docs.sqlc.dev/en/stable/index.html
[7]: https://entgo.io
[8]: https://entgo.io/docs/grpc-intro
