# PRE ORDER TRAVERSAL
[link](http://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/)

## Order
Preorder (Root, Left, Right) : 1 2 4 5 3

## Recursive function
```
void printPreorder(struct node* node) {
    if (node == NULL)
          return;

    /* first print data of node */
    printf("%d ", node->data);

    /* then recur on left sutree */
    printPreorder(node->left);

    /* now recur on right subtree */
    printPreorder(node->right);
}
```
