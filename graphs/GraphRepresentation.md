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

## Adjacency lists: the hybrid choice
- The combination of an edge list and adjacency matrix, an adjacency list is an array of linked lists that represents a graph
    - Makes it easy to see which other vertices are adjacent to other vertices
- Each vertex is given an index in a list, and has its neighboring vertices stored as an array/linked list, adjacent to it

![Adjacency List](http://lagodiuk.github.io/images/adj_lists/img_2.png)

- Retrieving one node's neighbors takes constant **O(1)** time, since all we need to do is find the correct node's index and pull its list of adjacent vertices
- To find a specific edge **(x, y)**, we need to find vertex **x**'s adjacency list and look to see if **y** is in that list
    - In worst case, this takes **O(d)** time, where d is the degree of vertex x
    - The **degree** of a vertex is the number of edges it has
    - Max value for d: **(|V| - 1)**, the case that a vertex has edges to every other vertex except for itself
    - Min value for d: 0, graph has one isolated vertex
- Space:
    - An adjacency list will require |V| amount of space because every vertex needs its own index
    - Linked list space depends on whether graph is **directed** or **undirected**
        - Undirected
            - Considering that every single node connected to a neighboring node in an undirected graph has its edge mirrored in it's neighboring node, **an undirected graph will always have a symmetric adjacency matrix**
            - Therefore, each edge is represented twice. Total space for linked list portion of adjacency list is **2(|E|)**
        - Directed
            - Simpler because not every node has bi-directional link, so not **symmetric**
            - Thus, space is **|E|**

