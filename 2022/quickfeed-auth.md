# Quickfeed Security: Redesigned Authentication and Authorization Architecture

## Administrative

- Supervisor: Hein Meling (with assistance from Martin Jaatun and Magnus Book)
- Group Composition: 2 or 3 students (or 1 for master's thesis)

## Prerequisites

- DAT320 Operating systems and systems programming is recommended
- DAT310 Web programming is recommended
- DAT250 Information and software security
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

In this project, the goal is to redesign the authentication and authorization architecture of Quickfeed, taking advantage of gRPC interceptors, similar to our current [validation interceptors][5].

Currently, Quickfeed uses the OAuth2 protocol to authenticate GitHub users.
We envision retaining OAuth2 but replacing our existing implementation to better align with Quickfeed's gRPC-based implementation.
Several blog posts describe possible solutions to this problem; see the reading material section.

Further, Quickfeed currently checks for authorization on a per-method basis (inside each method) rather than as part of an ingress check before the methods are called.
We want to replace these per-method authorization checks with an interceptor-based approach, similar to the design shown [here][2] and in [this video][3].
One crucial requirement is that specific methods can only be invoked if a user (student or teacher) is associated with (has signed up to) a particular course.
Hence, it is not necessarily enough to distinguish users based on their roles as students and teachers.

Finally, Quickfeed relies on an external Envoy proxy to handle `https` traffic, which must therefore handle certificate renewals via Let's encrypt.
If time allows, the project should also investigate if it is possible to replace the Envoy proxy currently used or run it in the same process as the quickfeed server, e.g., by borrowing code from the [grpc-web-proxy][4].
This should also allow implementing our own certificate renewal via the [Acme protocol][6] used by Let's encrypt.

[This blog][7] is also relevant for this project.

In general, the Quickfeed server should also be validated more extensively for security vulnerabilities.

There is currently a prototype demonstrating the feasability of the above authorization approach.
Hence, the project should build on the prototype and may be expanded to cover security pen-testing, if needed.

The implementation language is mainly Go.

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

[1]: https://github.com/autograde/quickfeed
[2]: https://github.com/techschool/pcbook-go/tree/master/service
[3]: https://youtu.be/kVpB-uH6X-s
[4]: https://github.com/improbable-eng/grpc-web/tree/master/go/grpcwebproxy
[5]: https://github.com/autograde/quickfeed/blob/master/ag/validation.go#L32
[6]: https://pkg.go.dev/golang.org/x/crypto/acme/autocert#example-Manager
[7]: https://blog.gopheracademy.com/advent-2019/go-grps-and-tls/
