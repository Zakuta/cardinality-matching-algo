cardinality-matching-algo
-------------------------
This is an implementation of Maximum Cardinality Matching Algorithm for finding matching with maximum cardinality given an undirected graph in rutime O( n m logn). It was written for an exercise assignment of the [Combinatorial Optimization lecture (WS 2016/17)](http://www.or.uni-bonn.de/lectures/ws16/cows16.html) held by Prof. Stefan Hougardy at Research Institute for Discrete Mathematics, University of Bonn.

The algorithm is in tandem with the implementation outlined in Combinatorial Optimization book (Fifth Edition) by Prof. Korte and Prof. Vygen and further uses some of the suggested optimizations, including:

* A Union-Find datastructure for odd-cycle mapping. The implmentation uses path compression to achieve nearly constant amortized costs for FIND operations.

* Resetting the only affected part of the tree structure in each augment operation.

Auxiliary heuristics applied that is not explicitly mentioned in the book:

* As an extra speed-up, starting with a greedy matching until it is maximal (can be found in linear time).

It would be a fun exercise to find other heuristics and optimizations that are suited for our use case.


Compile with cmake
-------------------------
```
mkdir build
cd build
cmake ..
make
```

Usage
-----
`./programming_task --graph file1.dmx [--hint file2.dmx]`

Graph must be provided in DIMACS format.

Tests
-----
Some unit tests using the Boost testing framework are provided.
Run via: 

`./tests`
