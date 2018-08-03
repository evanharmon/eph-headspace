# POST ORDER TRAVERSAL 1 STACK
[link](http://www.geeksforgeeks.org/iterative-postorder-traversal-using-stack/)

## Explanation
1. Right child of 1 exists.
  Push 3 to stack. Push 1 to stack. Move to left child.
       Stack: 3, 1

2. Right child of 2 exists.
  Push 5 to stack. Push 2 to stack. Move to left child.
       Stack: 3, 1, 5, 2

3. Right child of 4 doesn't exist. '
  Push 4 to stack. Move to left child.
       Stack: 3, 1, 5, 2, 4

4. Current node is NULL.
  Pop 4 from stack. Right child of 4 doesn't exist.
  Print 4. Set current node to NULL.
       Stack: 3, 1, 5, 2

5. Current node is NULL.
   Pop 2 from stack. Since right child of 2 equals stack top element,
   pop 5 from stack. Now push 2 to stack.
   Move current node to right child of 2 i.e. 5
       Stack: 3, 1, 2

6. Right child of 5 doesn't exist. Push 5 to stack. Move to left child.
       Stack: 3, 1, 2, 5

7. Current node is NULL. Pop 5 from stack. Right child of 5 doesn't exist.
  Print 5. Set current node to NULL.
       Stack: 3, 1, 2

8. Current node is NULL. Pop 2 from stack.
  Right child of 2 is not equal to stack top element.
  Print 2. Set current node to NULL.
       Stack: 3, 1

9. Current node is NULL. Pop 1 from stack.
  Since right child of 1 equals stack top element, pop 3 from stack.
  Now push 1 to stack. Move current node to right child of 1 i.e. 3
       Stack: 1

10. Repeat the same as above steps and Print 6, 7 and 3.
   Pop 1 and Print 1.

## Functions
CreateStack
IsFull
IsEmpty
Push
Pop
Peek

## CreateStack
```
struct Stack* createStack(int size) {
   struct Stack* stack = malloc(sizeof(struct Stack));
   stack->size = size;
   stack->top = -1;
   stack->array = malloc(stack->size * sizeof(struct Node*));
   return stack;
}
```

## isFull
```
int isFull(struct Stack* stack)
{  return stack->top - 1 == stack->size; }
```

## isEmpty
```
int isEmpty(struct Stack* stack)
{  return stack->top == -1; }
```

## Push
```
void push(struct Stack* stack, struct Node* node) {
   if (isFull(stack))
       return;
   stack->array[++stack->top] = node;
}
```

# Pop
```
struct Node* pop(struct Stack* stack) {
   if (isEmpty(stack))
       return NULL;
   return stack->array[stack->top--];
}
```

# Peek
```
struct Node* peek(struct Stack* stack) {
   if (isEmpty(stack))
       return NULL;
   return stack->array[stack->top];
}
```

# postOrderIterative
```
void postOrderIterative(struct Node* root) {
   // Check for empty tree
   if (root == NULL)
       return;

   struct Stack* stack = createStack(MAX_SIZE);
   do {
       // Move to leftmost node
       while (root) {
           // Push root's right child and then root to stack.
           if (root->right)
               push(stack, root->right);
           push(stack, root);

           // Set root as root's left child
           root = root->left;
       }

       // Pop an item from stack and set it as root
       root = pop(stack);

       // If the popped item has a right child and the right child is not
       // processed yet, then make sure right child is processed before root
       if (root->right && peek(stack) == root->right) {
           pop(stack);  // remove right child from stack
           push(stack, root);  // push root back to stack
           root = root->right; // change root so that the right
                               // child is processed next
       }
       else { // Else print root's data and set root as NULL
           printf("%d ", root->data);
           root = NULL;
       }
   } while (!isEmpty(stack));
}
```
