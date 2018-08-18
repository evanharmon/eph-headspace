# POST ORDER TRAVERSAL 2 STACK
[link](http://www.geeksforgeeks.org/iterative-postorder-traversal/)

## explanation
1. Push 1 to first stack.
     First stack: 1
     Second stack: Empty

2. Pop 1 from first stack and push it to second stack. Push left and right children of 1 to first stack
     First stack: 2, 3
     Second stack: 1

3. Pop 3 from first stack and push it to second stack. Push left and right children of 3 to first stack
     First stack: 2, 6, 7
     Second stack:1, 3

4. Pop 7 from first stack and push it to second stack.
     First stack: 2, 6
     Second stack:1, 3, 7

5. Pop 6 from first stack and push it to second stack.
     First stack: 2
     Second stack:1, 3, 7, 6

6. Pop 2 from first stack and push it to second stack. Push left and right children of 2 to first stack
     First stack: 4, 5
     Second stack:1, 3, 7, 6, 2

7. Pop 5 from first stack and push it to second stack.
     First stack: 4
     Second stack: 1, 3, 7, 6, 2, 5

8. Pop 4 from first stack and push it to second stack.
     First stack: Empty
     Second stack: 1, 3, 7, 6, 2, 5, 4

The algorithm stops since there is no more item in first stack.
Observe that content of second stack is in postorder fashion. Print them.

## Functions
CreateStack
IsFull
IsEmpty
Push
Pop
PostOrderIterative

### CreateStack
```
struct Stack *createStack(int size) {
   struct Stack *stack = malloc(sizeof(struct Stack));
   stack->size = size;
   stack->top = -1;
   stack->array = malloc(stack->size * sizeof(struct Node*));
   return stack;
}
```

### isFull
```
int isFull(struct Stack *stack)
{  return stack->top - 1 == stack->size; }
```

### isEmpty
```
int isEmpty(struct Stack *stack)
{  return stack->top == -1;  }
```

### Push
```
void push(struct Stack *stack, struct Node *node) {
   if (isFull(stack))
       return;
   stack->array[++stack->top] = node;
}
```
### Pop
```
struct Node *pop(struct Stack *stack) {
   if (isEmpty(stack))
       return NULL;
   return stack->array[stack->top--];
}
```

### postOrderIterative
```
void postOrderIterative(struct Node *root) {
   if (root == NULL)
       return;

   // Create two stacks
   struct Stack *s1 = createStack(MAX_SIZE);
   struct Stack *s2 = createStack(MAX_SIZE);

   // push root to first stack
   push(s1, root);
   struct Node *node;

   // Run while first stack is not empty
   while (!isEmpty(s1)) {
       // Pop an item from s1 and push it to s2
       node = pop(s1);
       push(s2, node);

       // Push left and right children of removed item to s1
       if (node->left)
           push(s1, node->left);
       if (node->right)
           push(s1, node->right);
   }

   // Print all elements of second stack
   while (!isEmpty(s2)) {
       node = pop(s2);
       printf("%d ", node->data);
   }
}
```
