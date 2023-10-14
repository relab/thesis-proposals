# Implement and Evaluate Minimal Perfect Hash Functions for Randomized Datasets

## Administrative

- Supervisor: Hein Meling
- Prof Meling is currently on sabbatical, but will be available for physical meetings from November 27, 2023.
- Before that I will be happy to answer questions by email, or set up a Zoom call to discuss the project with prospective students.
- Contact: <hein.meling@uis.no>
- Several students can work on this project.

## Prerequisites

- Data structures and algorithms
- Proficient in the Go programming language

## Background

A minimal perfect hash function (MPHF) is a special type of hash function that maps a set of keys to a set of consecutive integers.
Minimal perfect hash functions are useful in a variety of applications, including search engines, databases, compilers, and pattern-matching algorithms.

The supervisor for this project have implemented a minimal perfect hash function, called [relab/bbhash][1] ([BBHash paper][2]), that we have used to implement a synchronization algorithm for decentralized storage systems.

### Detailed Description of MPHF

A minimal perfect hash function is a bijective map from a set of _N_ keys (elements) to the integers [0,..., _N_-1] (index values).
Each key of the set is mapped to exactly one value, and each value is paired with exactly one key.
MPHF offers a space-efficient, collision-free mapping of large datasets.
While the theoretical minimum is 1.44 bits per key, practical implementations typically require a few bits per key.
The MPHF is intended for static datasets and has no add, update, or delete operations.
Lookup time is constant O(1), and a mapping can be constructed in linear time O(_N_).
Querying the map for a key that was part of the original set always returns the corresponding value in the range 𝑣 ∈ [0, _N_-1].
However, if the key used to query the MPHF was not part of the original set, the MPHF may return any value in the range 𝑣 ∈ [0, _N_-1], which is considered a false-positive.
Thus, an application using an MPHF must be able to handle false-positives.

## Project Description

The goal of this project is to implement and evaluate one or more other MPHF algorithms in Go.
These are some possible algorithms that may be implemented:
[LeMonHash][3], [PTHash][4], [CHD][5] and [RecSplit][6].
There is also C++ code for the algorithms available online that can be used as a reference implementation.

The algorithms should be implemented in Go along with suitable test cases and benchmarks.
The implementations should be evaluated using the same datasets as in the papers.
Additionally, the algorithms should be evaluated using randomized datasets, which is a unique requirement for our synchronization algorithm.

The goal is to evaluate the algorithms for very large datasets, typically fetching the data blocks from a database or disk.
The data blocks are then hashed to get a unique identifier (a key) for the block.
The keys are then used to construct a minimal perfect hash function.
Part of the evaluation will be to decide whether or not Go's benchmarking framework is suitable for this type of evaluation.

The supervisor can provide detailed guidance on the implementation and evaluation of the selected algorithms.

## Tasks

- Review the literature on minimal perfect hash functions
  - Write background section discussing the state of the art
- Review C++ code for the algorithm(s) to be implemented
- Implement the selected algorithm(s) in Go
  - The implementation should be well documented
  - Each algorithm must include suitable test cases and benchmarks
- Evaluate implementation performance using
  - The same datasets as in the papers
  - Randomized datasets
  - Compare the Go implementations with the C++ implementations
- Report on findings and lesson learned from the implementations

[1]: https://github.com/relab/bbhash
[2]: https://arxiv.org/abs/1702.03154
[3]: https://arxiv.org/abs/2304.11012
[4]: https://jermp.github.io/assets/pdf/papers/SIGIR2021.pdf
[5]: https://cmph.sourceforge.net/papers/esa09.pdf
[6]: https://arxiv.org/abs/2212.09562
