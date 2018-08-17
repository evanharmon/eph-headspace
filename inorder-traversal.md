# INORDER TRAVERSAL
(http://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/)

## Order
Inorder (Left, Root, Right) : 4 2 5 1 3

## Recursive function
void printInorder(struct node* node) {
    if (node == NULL)
          return;

    /* first recur on left child */
    printInorder(node->left);

    /* then print the data of node */
    printf("%d ", node->data);

    /* now recur on right child */
    printInorder(node->right);
}
