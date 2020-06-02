# ALGORITHMS - DIRECTED ACYCLIC GRAPH

## Path
A path in a graph is a sequence of vertices and edges that allow you to get
from one vertex to another (or back to itself); we say that the path contains
both the vertices on it and the edges traversed

## Topological
topological sort of a dag produces a linear order such that if (u, v) is an
edge in the dag, then u appears before v in the linear order

The linear order produced by a topological sort is not necessarily unique

## In Degree
The number of edges entering a vertex is the vertex’s in-degree

## Out Degree
Every dag must have at least one vertex with in-degree 0 and at least one
vertex with out-degree 0 (no edges leaving the vertex), for otherwise there
would be a cycle

## U Edge Removal
Every dag must have at least one vertex with in-degree 0 and at least one
vertex with out-degree 0 (no edges leaving the vertex), for otherwise there
would be a cycle
