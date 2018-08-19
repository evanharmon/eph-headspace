# ALGORITHMS - DIJKSTRA
uses greedy method: Always pick the next closest vertex to the source.
uses priority queue to store unvisited vertices by distance from s.
does not work with negative weights.

## Difference Between Unweighted Shortest Path and Dijkstra Algorithm
- To represent weights in the adjacency list, each vertex contains the weights
of the edges (in addition to their identifier)
- Instead of ordinary queue we use priority queue [distances are the priorities]
and the vertex with the smallest distance Is selected for processing
- The distance to a vertex is calculated by the sum of the weights of the edges
on the path from the source to that vertex
- We update the distances in case the newly computed distance is smaller than
the old distance which we have already computed

## Edge Cost
value between the two vertices is known as the edge cost between two vertices

## Efficiency
Depends on number of delete mins and updates for priority queue
