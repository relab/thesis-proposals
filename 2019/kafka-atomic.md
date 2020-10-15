# Strict Ordering Guarantees for Event-source Systems

### Supervisor: Leander Jehl

### Prerequisites:

- Distributed systems (DAT520)
- Good programming skills in Java or Scala

### Motivation

Event source systems such as [Kafka](http://kafka.apache.org) are an important
building block for modern, large scale applications.
Compared to other publish-subscribe systems, Kafka provides strong consistency
guarantees, such as reliable delivery and ordering guarantees for messages
within one topic.

However the existing system does not provide any ordering guarantees between
messages sent to different topics. This reduces the applicability of the system
and requires application developers to do complex reasoning to avoid
inconsistencies.

While stricter ordering guarantees may significantly simplify the development of
applications with strong correctness requirements, mechanisms to introduce such
orderings hold the potential to significantly impact performance of the system,
introducing both bottlenecks and a significant overhead due to control messages.

## Project Description

The goal of this project is to utilize atomic multicast algorithms [2,3], to allow
message in different Kafka topics to be received in a consistent order.
One challenge for the project will be, how such strategies can be implemented
without requiring a major change or introducing bottlenecks to the Kafka system.

The implemented mechanisms should be evaluated for different workloads and
possibly realistic applications.

### References

[1] [Kafka](http://kafka.apache.org)

[2] [Atomic multicast](https://www.researchgate.net/publication/221343227_Optimal_atomic_broadcast_and_multicast_algorithms_for_wide_area_networks)

[3] [Multi Ring Paxos](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6263916)
