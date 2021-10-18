# Ensure the correctness of the Gorums/protocols via Coloured Petri Nets (CPNs) and Model-based Testing (MBT)

## Background on Gorums

Gorums is a novel framework for building fault tolerant distributed systems via group-RPCs (quorum calls) developed at UiS.
Gorums offers a flexible and simple quorum call abstraction, used to communicate with a set of processes, and to collect and process their responses.
Gorums provides separate abstractions for (a) selecting processes for a quorum call and (b) processing replies.
These abstractions simplify the main control flow of protocol implementations, especially for quorum-based systems, where only a subset of the replies to a quorum call need to be processed.
Gorums uses code generation to produce an RPC library that clients can use to invoke quorum calls.
Gorums is a wrapper around the gRPC library.
Services are defined using the protocol buffers interface definition language.

## Background on CPN

CPN is a graphical language for modeling and validation of systems where concurrency, communication, and synchronization constitute the key aspects.
CPNs combines Petri Nets and the factional programming language CPN which is based on Standard ML.
Construction and analysis of CPN models are supported by CPN Tools which has been widely used for modeling and verifying models of complex distributed systems.
CPNs has been applied to many domains including communication protocols, data networks, and distributed algorithms.
Recently, work has been focused on test case generation with CPNs and CPN Tools for testing Gorums framework and quorum-based distributed protocols.

## Project description/directions

A recent research has focused on Model-based software testing (MBT) using techniques from the software testing domain for the development of distributed systems and protocols implemented via the Gorums framework.
Such a MBT approach is based on modeling and automated test case generation via CPNs and CPN Tools.
However, it is also important to further expend the approach in following directions:

    1. A fully automated testing approach based on CPNs and CPN tools can be
       investigated in order to test Gorums framework and different distributed protocols.
       The recent technique on fully automated testing has been developed based on CPNs 
       to test a simple two-phase commit protocol implemented in GO, 
       but in order to further test different advanced distributed protocols implemented 
       via Gorums, the testing technique needs to be expended to a more generic
       approach so that it does not need to involve any manual process for test
       case generation and execution, and is suitable to test different
       protocols implemented vis Gorums. This might involve the investigation of
       mapping between the generated test cases from CPN Tools and the system
       under test (Gorums/protocols). This mapping usually can be achieved by 
       developing a test adapter for the test case execution, but how we can 
       provide a higher degree of automation and maybe also support online
       testing for this process to fit different protocols remains a question.
    
    2. When applying MBT based on CPNs to test Gorums and protocols, it is a
       challenge for MBT to obtain desired test adequacy criteria (coverage) by 
       generating a small test suite having few redundant test cases, especially
       when involving the test of concurrent execution and non-determinism. So,
       for testing distributed protocols implemented vis Gorums, we anticipate
       that this will motivate the work into the development of guided approaches 
       for test case selection and generation with heuristic search strategies 
    
    3. In order to increase coverage and consider more of the Gorums library's
       code path, we need to test distributed protocols implemented via Gorums
       under failure scenarios and adverse conditions, such as network errors, 
       partitions, server crashing and recovering. This might require the design
       of the CPN test models with respect to the different failure scenarios 
       so that we can test Gorums and protocols under such scenarios.

## Tasks / Milestones

- Learn to develop with Gorums.
- Learn modeling with CPNs and CPN Tools.
- Learn MBT and testing techniques.
- Design CPN test models.
- Develop tools and approaches based on CPNs to test Gorums and its distributed
  protocols.
- Investigate and compare simulation and state space test case generation approaches of CPNs.

## Reading material

- [Gorums paper](https://ieeexplore.ieee.org/document/7980198)
- [Gorums source code](https://github.com/relab/gorums)
- [Model-based testing (MBT) paper](https://onlinelibrary.wiley.com/doi/full/10.1002/stvr.456?casa_token=9NXWKvl25KgAAAAA%3AInKpX_WfG7qMrsLGzNLVyRxg4uvP1c0vtfLOoMtGhrSJlxQGs7xAwsOm80-ZrHBz_reWAi38HKbuCrA)
- [CPNs paper and CPN Tools paper](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.218.1998&rep=rep1&type=pdf)
- [MBT with CPNs paper](https://link.springer.com/chapter/10.1007/978-3-030-00359-3_7)
- MBT with CPNs for Gorums and distributed protocols:
  1. [Model-Based Testing of the Gorums Framework for Fault-Tolerant Distributed Systems](https://link.springer.com/chapter/10.1007/978-3-662-58381-4_8)
  2. [Automated test case generation for the Paxos single-decree protocol using a Coloured Petri Net model](https://www.sciencedirect.com/science/article/pii/S235222081830049X)
- (PhD thesis) [Model-based software testing for distributed systems and protocols - chapter 3 and 4](https://hvlopen.brage.unit.no/hvlopen-xmlui/handle/11250/2676335)
