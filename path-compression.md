# PATH COMPRESSION
## Definition
- Make paths point to the root
- The effect of path compression is that every node on the path from X to the
root has its parent changed to the root

## Unions
Path compression is compatible with UNION by size but not with UNION by height
as there is no efficient way to change the height of the tree
