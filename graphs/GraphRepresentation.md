# [From Theory to Practice: Representing Graphs](https://medium.com/basecs/from-theory-to-practice-representing-graphs-cfd782c5be38)

![Different Graph Types](www.google.com/imgres?imgurl=https%3A%2F%2Fdist.neo4j.com%2Fwp-content%2Fuploads%2F20181121091034%2Fgraph-properties-graph-algorithms-2.png&imgrefurl=https%3A%2F%2Fneo4j.com%2Fblog%2Fgraph-algorithms-neo4j-graph-algorithm-concepts%2F&tbnid=G9QxX3o_XhgPrM&vet=12ahUKEwi6hObd2uzrAhVuAjQIHSZRDKkQMygAegUIARCgAQ..i&docid=RrKuhCyHCGnN2M&w=650&h=358&q=dense%20and%20sparse%20graphs&ved=2ahUKEwi6hObd2uzrAhVuAjQIHSZRDKkQMygAegUIARCg)

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
![Symmetric Matrices](https://www.google.com/imgres?imgurl=https%3A%2F%2Fhadrienj.github.io%2Fassets%2Fimages%2F2.6%2Fdiagonal-and-symmetric-matrices.png&imgrefurl=https%3A%2F%2Fhadrienj.github.io%2Fposts%2FDeep-Learning-Book-Series-2.6-Special-Kinds-of-Matrices-and-Vectors%2F&tbnid=ArBu2WiKagpv6M&vet=12ahUKEwiU8cz82uzrAhV_AjQIHWD-CngQMygGegUIARDJAQ..i&docid=loYiiSLrg5EUdM&w=660&h=320&q=symmetric%20matrices&ved=2ahUKEwiU8cz82uzrAhV_AjQIHWD-CngQMygGegUIARDJAQ)
- Pros
    - Easy to follow and represent
    - Looking up, inserting, and removing and edge can be done in **O(1)** or constant time
- Cons
    - Consumes **O(V^2)** space
    - If graph is sparse, 0s will take most the space
