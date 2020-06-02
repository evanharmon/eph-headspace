# ALGORITHMS - BINARY TREES

## Order
Order does not matter. They are non linear

## Levels
Root node is at level 0

## Three Ways To Traverse
L left node
D current node
R right node
6 possibilities: LDR, LRD, DLR, DRL, RDL, RLD

## Traversal
Stops after search item found

## Traversal Methods
depth first traversals
## Only three bc left vs right does not matter
Preorder DLR
Inorder LDR
postorder RDL

## Separate Traversal Method
Level order

## Basic Operations
Insert, delete, search, traverse

## Auxiliary Operations
Find size of tree
Find the height of tree
Find level with maximum sum
Find the least common ancestor

## Height Of Tree
```
int height(struct node* node) {
    if (node==NULL)
        return 0;
    else {
        /* compute the height of each subtree */
        int lheight = height(node->left);
        int rheight = height(node->right);


        /* use the larger one */
        if (lheight > rheight)
            return(lheight+1);
        else return(rheight+1);
    }
}
```

## Size Of Tree
```
int size(struct node* node)
{
  if (node==NULL)
    return 0;
  else
    return(size(node->left) + 1 + size(node->right));
}
```
