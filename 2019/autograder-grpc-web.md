# Replacing Autograder's REST API with gRPC Methods

### Supervisor: Hein Meling

### Prerequisits:

- Web Programming (DAT310)
- Operating Systems and Systems Programming (DAT320)

### Languages and Technologies

- Go, Typescript, gRPC, gRPC-web

### Background on Autograder

Autograder is a system developed at UiS to automatically evaluate student hand-ins.
Autograder is able to run a set of tests against any hand-in delivered by
students and will provide a score and feedback for the students.

We have recently reimplemented both the Autograder backend and frontend to improve its robustness. In particular, the backend is now based on a SQL database, interaction with GitHub (and GitLab), and using the Echo framework for handling the REST interface calls. We use Docker containers to run student code. On the frontend, we used the Typescript langauge along with the React framework from Facebook to avoid many of the concerns with the Javascript langauge.

### Project Description

[gRPC-web](https://github.com/grpc/grpc-web) is a technology that can reduce complexity for web applications such as Autograder by defining specific interfaces that clients can query to obtain data. A new Javascript/Typescript client-side library is now available that can enable web clients to access gRPC-based web servers. 

In this project, the goal is to replace the REST API of the new Autograder with gRPC, so as to reduce the complexity due to the REST interface. When reimplementing Autograder we learned several problematic issues with Autograder's REST API:

1. Developing REST-based webservers are errorprone. Even when using the Echo middleware the developer must explicitly extract, parse and interpret information from HTTP requests and session cookies etc.
2. Writing test cases for a REST-based webserver requires complex setup to populate HTTP requests, session information, and corresponding HTTP responses.
3. We avoid declaring REST-endpoints and their routes.
4. We avoid exposing multiple endpoints to web clients, effectively reducing Autograder's attack surface.

In a previous evaluation study [1], we implemented a prototype using gRPC-web, demonstrating the feasability of replacing most REST endpoints. In this study we found that we can significantly simplify code complexity since we can avoid extracting and parsing JSON objects manually (also called marshalling or serialization). This basically allows implementing each endpoint as an RPC method that only needs to interpret information from the client directly and generate the expected reply. We can also significantly simplify the setup for our test cases, which will make it easier to implement more tests to expand our test coverage.

The goal in this project is to continue developing the existing gRPC-based Autograder prototype to replace the remaining REST endpoints, update the test cases, and bring it up to date with the current REST-based Autograder that is currently deployed, and expand the test coverage by adding more tests. Since we already have two different implementations of the Autograder platform, it will be possible to evaluate the reduction in code complexity, readability for new users, ease of maintenance and other criteria. 

### Advanced:

If time allows, the project can be expanded to support more sophisticated topics, such as:

1. GitHub/OAuth2 login over gRPC-web (or some other approach) and
2. Addressing an [issue with the proto format](https://github.com/golang/protobuf/issues/52) to allow custom Go tags, which will allow using proto message types to generate Go types that are compatible with the database.

### References

- [1] Reimplementing Autograder with gRPC, Junaid Alam
- https://github.com/grpc/grpc-web
- https://github.com/golang/protobuf/issues/52
