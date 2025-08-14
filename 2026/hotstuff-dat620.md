# Hotstuff DAT620 project

## Administrative

- Supervisor: Leander Jehl
- Contact: <leander.jehl@uis.no>


## Project Description

The [relab research group](https://relab.website/) maintains a implementation of the hotstuff algorithm: [https://github.com/relab/hotstuff/](https://github.com/relab/hotstuff/).
Recently, several bugs have been found in the implementation. 
This includes 2 potential weaknesses in the protocol implementation which can be exploited by attackers. 
Additionally it is suspected that there is a bug in the networking infrastructure. 

The goal for this project is to reproduce the bugs, propose and implement a fix, and test and benchmark the resulting version.
It is proposed to start with the protocol bugs and, if time allows move on to the bug in the networking infrastructure.
Since it is important that the fixes to protocol bugs do not introduce new weaknesses or affect protocol correctness, fixing these bugs will require to learn about the hotstuff protocol and how it is implemented in our system.

By completing this project, the student will gain significant insights both in the hotstuff protocol and its implementation. This will be a significant advantage if the student chooses to work on a master thesis in the related to the hotstuff implementation.
