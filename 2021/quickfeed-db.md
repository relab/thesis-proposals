# Quickfeed Database Revisited

## Administrative

- Supervisor: Hein Meling and Erlend Tøssebro
- Group Composition: 2 or 3 students

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

However, we want to make the database transactions needed by Quickfeed even more robust with added tests and improved transaction support.
To that end, this project has these milestones:

- Benchmark the database module in its current state
- Upgrade to the most recent GORM version
- Ensure that all database accesses use transactions to prevent inconsistencies
- Implement the same [database API][2] using hand-written SQL statements
- Discuss pro/con with ORM vs pure SQL queries, e.g., [see here][4]
- Review and revise the current database ER model/schema and database API for simplification and performance
- Implement additional integration and robustness tests, e.g., ability to handle multiple concurrent transactions without compromising consistency
- Benchmark the performance of the different variants of the database

Depending on the project team's size, the project can be expanded in different directions, e.g., testing with different databases such as MySQL, PostgreSQL, or CockroachDB.
Another direction could be implementing a NoSQL variant of the database schema and comparing it against the SQL variants.

The project should also review the database schema and API from a security perspective to ensure that it does not leak sensitive information.
Further, the project should also define policies, procedures, and mechanisms to handle database migration/schema changes.

The implementation language is mainly Go and SQL.

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/autograde/quickfeed/blob/master/database/database.go
[3]: https://gorm.io
[4]: https://wozniak.ca/blog/2014/08/03/What-ORMs-have-taught-me-just-learn-SQL/
