# A Teaching Operating System based on Simulation for Third Semester Students

## Administrative

- Supervisor: Hein Meling
- Group Composition: 3-4 students

## Prerequisites

- DAT320 Operating systems and systems programming is required.
- Strong interest in Go programming.
- Strong interest in learning operating systems in more depth.

## Expected Learning Outcomes

Become proficient in Go programming.
Students are expected to review textbook material and various sources to get inspiration for developing the student assignments in this project.

## Project description

The current assignments in the OS course simulate various aspects of an operating system.
However, the different assignments have been built in an ad hoc manner without a unifying framework.

The goal in this project is to design a teaching operating system based on simulating a real OS.
The idea is to build the assignment framework such that the full OS can be built incrementally by the students of the OS course, one component at a time.
Each component must be tested sufficiently to be usable throughout the semester, as more components are added to the system.

The tasks of the project include:

- study the literature of existing teaching operating systems (see linked resources below)
- take learnings from these existing systems and design an architecture suitable for third semester students following [textbook](http://pages.cs.wisc.edu/~remzi/OSTEP/)
- implement the full OS architecture (simulated) in the Go programming language
- write tests with scoring for all parts of the OS that can be checked via Quickfeed (Autograder)
- evaluate the performance of various aspects of the OS
- write assignments based on the implementation, selecting which parts the students must implement themselves

The project is open to a fair bit of flexibility, but the assignments should focus on the topics covered in the lectures and be related to the textbook that we currently use.
In particular, the students should examine all the exercises in the most relevant chapters, and also the Systems Labs in Appendix G, for inspiration.

## Expectations

The project is expected to produce high-quality Go code, following established design principles (SOLID) and idiomatic Go and should follow the guidelines linked below.
Furthermore, the project should describe the tasks (the `README.md` files), following the template of the existing labs, and the project is also expected to produce a solution, student skeleton and tests for students and Quickfeed tests.
The assignments may also include multiple choice or other similar types of evaluations.
Alternative evaluation types could also involve some integration with Quickfeed's frontend or a plugin for VSCode.

## Some Idea Sketches

Below are some ideas based on our current assignments.
However, we are open to other ideas and designs as well, e.g. based on Xv6 or some other teaching OS.

- The first component could be the `Process` simulating a real process, which could be executed one-by-one.
  Initially, this could be done with a batch-like system, where processes arrive and runs until completion, perhaps following a trivial FIFO ordering.
  Different processes could be initiated with different workloads as part of our tests, which could reveal some weakness in student implementations of their scheduler or something.
- A second component could be a `Scheduler` component that can schedule the processes in SJF ordering.
  The students could implement preemption and allow the OS scheduler to deschedule a process and let another process run, e.g. in round robin fashion.
  And perhaps, RR is not a good choice for some workloads, and we want to give a better allocation of the resources using a stride scheduler.
  Finally, they could implement a multi-level feedback queue scheduler.
- A third component could be to implement `Memory Management` (similar to the paging assignment), but building on the same framework as for the `Process` and `Scheduler`.
  We could have an assignment with a simulated TLB and cache replacement algorithms.
- Other ideas could be to add virtual memory with disk access using present and dirty bits.
- And a final assignment could be a remote file system based on gRPC.
- It would be cool if the process abstraction could be used to implement a terminal shell, or some other interesting applications, inside their own OS.

## Reading material

- [Operating Systems: Three Easy Pieces](http://pages.cs.wisc.edu/~remzi/OSTEP/)
- [Xv6, a simple Unix-like teaching operating system](https://pdos.csail.mit.edu/6.828/2012/xv6.html)
- [Nachos Instructional Operating System](https://homes.cs.washington.edu/~tom/nachos/)
- [Pintos](https://pintos-os.org)
- [Go Wiki about Test Comments](https://github.com/golang/go/wiki/TestComments)
- [Go Wiki about Code Review](https://github.com/golang/go/wiki/CodeReviewComments)
- [SOLID Principles in Go](https://dave.cheney.net/2016/08/20/solid-go-design) (see also YouTube video linked herein)
