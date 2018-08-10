# Graphs

## Data Shape
```
struct Graph {
 int V;
 int E;
 int **Adj; // 2d matrix
}
```

## Vertices and Edges
Vertices and edges are positions and store elements

### V
A set of nodes, called vertices

### E
Edges, collection of pairs of vertices

### Directed Edge
ex: one way traffic
Ordered pair of vertices (u, v)
First vertex u is the origin
Second vertex v is the destination

### Undirected Edge
ex: railway lines
Unordered pair of vertices (u, v)
Vertex u to v

### Directed Graph
ex: route network
All edges are directed

### Undirected Graph
ex: flight network
All edges are undirected

### Cycles
A graph with no cycles is called a tree

### Adjacent
An edge connecting two vertices

### Tree
Acyclic connected graph

### Self Loop
Edge that connects a vertex to itself

### Degree
Number of edges incident on it

### path
A sequence of adjacent vertices

### Connected
There is a path for every vertex to every other vertex

### forest
Disjoint set of trees

### Spanning Tree of Connected Graph
A sub graph that contains all of that graphs vertices and is a single tree

### bipartite graph
Graph whose vertices can be divided into two sets such that all edges connect a
vertex to one set with a vertex in the other set

### Traversal Algorithms
Depth first
Breadth first

# relax an edge
Instead of s to v, try going s to u to v and see if that's shorter
s ~~~~~~~> v
 \         ^
  \        |
   \~~~~~> u
