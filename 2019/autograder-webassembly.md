# Reimplementing the Autograder Frontend in Go/Vecty and Compiled to WebAssembly

### Supervisor: Hein Meling

### Prerequisits:

- Web Programming (DAT310)
- Operating Systems and Systems Programming (DAT320)

### Languages and Technologies

- Go, WebAssembly, Vecty, Typescript, React

### Background on Autograder

Autograder is a system developed at UiS to automatically evaluate student hand-ins.
Autograder is able to run a set of tests against any hand-in delivered by
students and will provide a score and feedback for the students.

We have recently reimplemented both the Autograder backend and frontend to improve its robustness. In particular, the backend is now based on a SQL database, interaction with GitHub (and GitLab), and using the Echo framework for handling the REST interface calls. We use Docker containers to run student code. On the frontend, we used the Typescript langauge along with the React framework from Facebook to avoid many of the concerns with the Javascript langauge.

### Technology Background:

WebAssembly (WASM) is a new technology that all major web browser vendors have committed to support as a replacement for Javascript. Most browsers already support WASM. The idea is to allow web client code to be written in almost any langauge, which can then be compiled to WASM and executed in the browser. However, to be useful, different languages must also provide libraries for interacting with the browser user interface. For Go, Vecty is one such library that aims to emulate the features of React.

**Warning:** These technologies are still in their infancy and may cause problematic bugs. Possible workarounds may be to use GopherJS with Vecty, which transpiles to Javascript, instead of WASM. 

### Project Description

In this project, the goal is to study Autograder's current frontend written in React/Typescript and evaluate whether or not it can be rewritten in Go with Vecty and compiled to WASM (or Javascript in the case of GopherJS.) This shall be done through prototyping in a stepwise manner the different functionalities of Autograder's frontend. To objective of this rewrite is to understand if Go/Vecty is a suitable language/framework for writing frontend applications. As such, the evaluation criteria include (i) is the code written in Go simpler than Typescript (a subjective measure), (ii) the lines of code and other software engineering metrics, (iii) does it perform equally to Typescript, and (iv) is the Go/Vecty libraries mature enough to replace Typescript in production. In terms of code simplicity, a Go implementation may for example avoid tricky callbacks typical in Javascript/Typescript, and use Go's channels for communication.

### References

- https://github.com/gopherjs/vecty
- https://github.com/gowasm/vecty
- https://medium.zenika.com/go-1-11-webassembly-for-the-gophers-ae4bb8b1ee03


