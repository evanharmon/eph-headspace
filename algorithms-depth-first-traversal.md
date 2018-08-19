# ALGORITHMS - DEPTH FIRST TRAVERSAL# link
(http://www.geeksforgeeks.org/depth-first-traversal-for-a-graph/)

## General
- Uses stacks
- Similar to preorder traversal
- Uses less memory than bfs because it doesn't have to maintain the child
pointers at each level
- Better at bottom of the tree

## Edges
Tree edge: new vertex
Back edge: from descendent to ancestor
Forward edge: from ancestor to descendant
Cross edge: between a tree and sub trees

## Traversal
Boolean often good enough: visited / not visited
All vertex initially marked unvisited
