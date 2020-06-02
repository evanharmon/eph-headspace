# POST ORDER TRAVERSAL
[Link](http://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/)

## Order
Postorder (Left, Right, Root) : 4 5 2 3 1

## Recursive function
```
void printPostorder(struct node* node) {
    if (node == NULL)
        return;

    // first recur on left subtree
    printPostorder(node->left);

    // then recur on right subtree
    printPostorder(node->right);

    // now deal with the node
    printf("%d ", node->data);
}
```
