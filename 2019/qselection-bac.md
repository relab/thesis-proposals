# Finding a trusting click in suspect graphs

### Supervisor: Leander Jehl

### Prerequisites:
- Algorithms and Datastructures (DAT200)
- Go programming language

### Background
In a distributed system, subject to arbitrary failures, failure or misbehavior
of individual machines/nodes may not be detectable by all remaining processes.
For example, in a system with machines `a`, `b` and `c`, machine `a` could
systematically drop messages to machine `b`. Thus, while `b` will consider `a`
as faulty, machine `c` will consider `a` as correct.

In *Quorum-Selection* we are interested to select a group of machines (called Quorum), such that no
two machines in the group consider each other as faulty.
This problem can be modeled as a graph problem where machines correspond to nodes or
vertices and edges between node `a` and `b`, `(a,b)` represents a detected failure.
The Quorum is a set of vertices that are not connected by edges, i.e. an
[independent set](https://en.wikipedia.org/wiki/Independent_set_(graph_theory))
in the graph.

However, failure detection in the presence of arbitrary failures or malicious
actors can be challenging. For example, if node `b` is supposed to forward a message
from node `a` to node `c` but fails to do so, this could be caused by node `b`
denying to forward the message, or by node `a` that did not send the message to
begin with. In this case, `c` cannot detect the failure of `a` or `b` but knows
that either `a` or `b` is faulty. Such detections cannot be modeled by a normal
graph. To model such detections in a graph we require a novel edge construct,
namely an edge that connects three nodes, `a`, `b`, and `c` or `(a,b,c)` in our example.
We call such graphs *Triple-Graphs*.

Independent sets can be defined accordingly, i.e. `I` a set of nodes is independent
in a *Triple-Graph*, if there does not exist a Triple-Edge `(a,b,c)` such that
`a`, `b` and `c` all are part of `I`.

### Project Goal
The main goal for this project is to implement and evaluate datastructures for
both regular and triple-graphs and algorithms to efficiently find an independent
set in these graphs.

Especially, algorithms should be able to efficiently adjust the independent set
if one edge is added two the graph.

Optionally the project may also investigate algorithms to select an independent
tree of given size and depth, i.e. a tree where edges in the tree are not edges
in the suspect graph.

### References
- Draft on Quorum Selection: http://www.ux.uis.no/~ljehl/pdf/QSforDAT620.pdf
- Independent set (Wikipedia): https://en.wikipedia.org/wiki/Independent_set_(graph_theory)
