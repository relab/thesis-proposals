# Evaluating Design Patterns for Event Handlers

## Supervisor: Leander Jehl and Hein Meling

## Group Composition: 2 or 3 students

## Prerequisites: 
DAT320 Operating systems

### Distributed Event-based Applications

Distributed applications running on multiple machines are inherently event-driven systems.
Besides user input and timeout events, messages received from different processes, located on the same or different machines, are usually handled as events.
This event-driven approach is also used in graphical user interfaces, to handle events such as button clicks and so forth.

### Static Event Handlers

A classic pattern to process such events are static event handlers, where one method or function is registered for each event type. 
However, static event handlers hold several pitfalls, when implementing more complex distributed algorithms.
These often require to filter out irrelevant messages, and aggregate multiple messages to be processed together.

### Thesis goal

In this thesis you will *review and evaluate* several open source systems commonly used in industry, to identify their use of event handlers in various forms.
The idea is to collect statistics and examples on the use of static event handlers.
Interesting metrics include 

- the extent to which different open source systems use event handlers, 
- the number of event handlers used,
- the lines of code per event handler,
- the extent to which filtering and aggregation is done in event handlers, and
- whether concurrency control, e.g. locks and condition variables, are being used in event handlers.

We expect that the students that work on this project, will be able to

- identify additional interesting metrics,
- identify examples of both good and bad use of event handlers, and
- identify design patterns, abstractions, or primitives that alleviate the problems discovered.

As a background for this thesis you will also be expected to give a review of relevant or alternative design patterns and primitives, such as CSP and channel-based communication, the actor model and the async-await pattern.

The supervision team have significant experience implementing systems based on event handlers, and will be able to provide guidance and references to relevant systems and literature.
