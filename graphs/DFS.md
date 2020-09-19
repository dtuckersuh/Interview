#![DFS Traversal](https://medium.com/basecs/deep-dive-through-a-graph-dfs-traversal-8177df5d0f13)

## A primer, before going deep
- Definition
    - In **depth-first search**, we can determine whether two nodes x and y have a path between them by looking at the children of the starting node and recursively determining if a path exists
    - DFS search will traverse graph in a single path, one child node at a time
    - Tells us if a path **exists**
- Like a maze, you go down one path until you hit a dead end. Then you backtrack until another path is found, and repeat
- Process of backtracking and repeating walk down path is just **recursion**

## Depth-first, in action
- Two things to keep in mind when initiating graph traversal
    1. We can pick any arbitrary node to start with
    2. We don't want to repeated "visited" nodes
- Keep trail of "breadcrumbs" as we traverse
- Employ a **stack data structure** to keep track of current search node
    - Push visited node to stack and set parent pointer to vertex we came from
- When we've gone as deep as possible, backtrack one vertex at a time, and check for other paths
    - Pop vertex off stack when no other vertices reachable from it
- Repeat process, remembering not to visit children already visited
- Every time we reached new node:
    1. We added node to top of "visited" stack
    2. Marked node as "visited"
    3. Checked if node has children -- if so, ensure it hasn't already been visited, then visit it. If not, pop off the stack

## Real-life recursion and runtime
- The recursion in DFS stems from the fact we don't finish checking a node until we reach dead end and pop off children from the stack
- **DFS Runtime**
    - Visit every vertex once => **Constant time, V,** even with recursive call
    - Check every outgoing edge from each vertex we visit => Depends on size of length of adjacency list, **linear time**
    - In an undirected graph, DFS would check each edge twice
    - DFS requires **O(V + E)** runtime
            - For a directed graph, |E| edges to check
            - For undirected graph, 2|E| edges
- DFS great in **determining whether path exists** between two nodes, and doesn't require lot of memory
- DFS not helpful in finding shortest paths -- could end up following longest path from x to y
