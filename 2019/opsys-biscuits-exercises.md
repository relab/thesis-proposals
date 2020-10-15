# Biscuit Research OS as a Teaching OS

### Supervisor: Hein Meling

### Prerequisits:

- Operating Systems and Systems Programming (DAT320)
- Should preferably know some x86 assembly

### Background

At many universities around the world, students get to build parts of a real operating system, which is a wonderful learning experience. Whereas other universities only teach the principles in theory lectures based on books. At UiS, we are considering two options: (i) develop the lab to focus purely on using operating system APIs to build systems, or to (ii) develop the lab towards implementing parts of a real OS using a teaching OS.

Biscuit is a research operating system written in Go as a proof of concept to demonstrate that Go (or Higher-Level Languages in general) can be used for writing an operating system.  While this is a research prototype, it seems like a pretty nice match for a teaching operating system as well. 

### Project Description

In this project the goal is to develop several lab exercises for the OS course, so that we can gain more experience with implementing actual OS components, such as virtual memory, scheduler, filesystems, graphics drivers etc. There are several existing teaching operating systems, including xv6, pintos, nachos etc that can serve as inspiration. However, the specific assignment is aimed at using the Biscuit OS to gain experience with using Go to build OS components.

The motivation for using Go to build an operating system is that:

- Biscuit showed that the performance overhead compared to C-based Linux is less than 15 %
- Go is easier to program
- Go provides simpler concurrency due to built in garbage collector
- Go can prevent a large class of kernel bugs because it offers better memory protection.

As much as possible, the exercises developed should be amenable to unit (or integration) testing using the Autograder.

### Tasks/Milestones

- Study existing teaching operating systems
- Study Biscuit code base and write Biscuit tutorial
- Adapt a selection of exercises from xv6 or other teaching OS to Biscuit
- Develop solutions for the exercises
- Write test cases for the exercises so that they can be tested with Autograder

### References

- https://github.com/mit-pdos/biscuit
- https://pdos.csail.mit.edu/papers/biscuit.pdf
- https://pdos.csail.mit.edu/papers/biscuit:osdi18-slides.pdf
- https://github.com/mit-pdos/xv6-public
- https://pdos.csail.mit.edu/6.828/2018/schedule.html


