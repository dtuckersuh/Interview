# [From Theory to Practice: Representing Graphs](https://medium.com/basecs/from-theory-to-practice-representing-graphs-cfd782c5be38)

![Different Graph Types](https://dist.neo4j.com/wp-content/uploads/20181121091034/graph-properties-graph-algorithms-2.png)

## Graph Definitions
- A graph is a data structure consisting of two distinct parts: a finite set of **vertices** (nodes) and **edges**.
    - Edges are represented as ordered or unordered pairs, depending on whether the graph is directed or undirected
- A graph is **dense** when there are as many edges as compared to nodes
- Likewise, a graph is **sparse** when there is a smaller edge-to-node ratio
- An **edge list** is a representation of all the edges (|E|) in the graph
    - One of the simplest representations of a graph
    - To iterate through the list would take linear, **O(E) time and space**

## Adjacency Matrix
- An adjacency matrix is a matrix that represents exactly which vertices in a graph have edges between them. The matrix serves as a lookup table, where a value of 1 represents an existing edge, and 0 represents otherwise.
- If values of both sides on the main diagonal are the same, the matrix is **symmetric**
    - In other words, values on row x, column y would equal values on row y, column x
![Symmetric Matrices](https://hadrienj.github.io/assets/images/2.6/diagonal-and-symmetric-matrices.png)
- Pros
    - Easy to follow and represent
    - Looking up, inserting, and removing and edge can be done in **O(1)** or constant time
- Cons
    - Consumes **O(V^2)** space
    - If graph is sparse, 0s will take most the space
