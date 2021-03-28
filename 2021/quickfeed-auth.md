# Quickfeed Security: Redesigned Authentication and Authorization Architecture

## Administrative

- Supervisor: Hein Meling (with assistance from Martin Jaatun and Magnus Book)
- Group Composition: 2 or 3 students

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT310 Web programming is recommended
- DAT250 Information and software security
- Proficient in the Go programming language

## Background on Quickfeed (also known as Autograder)

Quickfeed is a system developed at UiS to automatically evaluate student hand-ins.
Quickfeed is able to run a set of tests against any hand-in delivered by students and will provide a score and feedback for the students.
We have recently reimplemented both the Quickfeed backend and frontend to improve its robustness.
In particular, the backend is now based on a gRPC-based server, a SQL database, the backend interacts with GitHub (and GitLab).
The backend use the gRPC-web framework for handling client requests (with a few remaining REST interface calls).
We use Docker containers to run student code.
On the frontend, we used the Typescript language along with the React framework from Facebook to avoid many of the concerns with the Javascript language.

## Project description

In this project, the goal is to redesign the authentication and authorization architecture of Quickfeed taking advantage to gRPC interceptors, similar to our current [validation interceptors](https://github.com/autograde/quickfeed/blob/master/ag/validation.go#L32).

Currently, Quickfeed uses the OAuth2 protocol to authenticate GitHub users.
We envision to retain OAuth2, but to replace our existing implementation to better align with Quickfeed's gRPC-based implementation.
This could be implement as a proxy, or some other design to be discussed with the supervisors.

Further, Quickfeed currently checks for authorization on a per method basis (inside each method), rather than as part of an ingress check before methods are called.
We want to replace these per-method authorization checks with an interceptor-based approach, similar to the design shown [here](https://github.com/techschool/pcbook-go/tree/master/service) and in [this video](https://youtu.be/kVpB-uH6X-s).
One important requirement is that certain methods can only be invoked if a user (student or teacher) is associated (has signed up to) with a particular course.
Hence, it is not necessarily enough to discriminate users based on their roles are student and teacher.

In general, the Quickfeed server should also be validated more extensively for security vulnerabilities.

Implementation language is mainly Go.

## Reading material

- [OAuth Authentication Vulnerabilities](https://portswigger.net/web-security/oauth)
- [gRPC interceptors](https://www.blog.dsb.dev/2019/06/14/creating-grpc-interceptors-in-go.html)
- [Blog: Use gRPC interceptor for authorization with JWT](https://dev.to/techschoolguru/use-grpc-interceptor-for-authorization-with-jwt-1c5h)
- [gRPC OAuth2 support](https://github.com/grpc/grpc-go/blob/master/Documentation/grpc-auth-support.md)
- [Blog: Using OAuth authentication tokens for gRPC client and server communications in Golang](http://www.inanzzz.com/index.php/post/cvjx/using-oauth-authentication-tokens-for-grpc-client-and-server-communications-in-golang)
- [Package oauth2](https://pkg.go.dev/golang.org/x/oauth2)
- [An implementation of JOSE standards (JWE, JWS, JWT) in Go](https://github.com/square/go-jose)
- [Securing your gRPC Application, slides](https://talks.godoc.org/github.com/lpabon/go-slides/2019/nyc-meetup-july-18-2019.slide#1)
- [Summary of auth method](https://testdriven.io/blog/web-authentication-methods/)
