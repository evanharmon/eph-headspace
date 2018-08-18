# LEVEL ORDER TRAVERSAL QUEUE
Same as breadth first
(http://www.geeksforgeeks.org/level-order-tree-traversal/)

## Functions
- PrintLevelOrder
- CreateQueue
- EnQueue
- DeQueue

## CreateQueue
```
struct node** createQueue(int *front, int *rear) {
   struct node **queue = malloc(sizeof(struct node*)*MAX_Q_SIZE);

   *front = *rear = 0;
   return queue;
}
```

## EnQueue
```
void enQueue(struct node **queue, int *rear, struct node *new_node) {
   queue[*rear] = new_node;
   (*rear)++;
}
```

## DeQueue
```
struct node *deQueue(struct node **queue, int *front) {
   (*front)++;
   return queue[*front - 1];
}
```

## PrintLevelOrder
```
void printLevelOrder(struct node* root) {
   int rear, front;
   struct node **queue = createQueue(&front, &rear);
   struct node *temp_node = root;

   while (temp_node){
       printf("%d ", temp_node->data);

       /*Enqueue left child */
       if (temp_node->left)
           enQueue(queue, &rear, temp_node->left);

       /*Enqueue right child */
       if (temp_node->right)
           enQueue(queue, &rear, temp_node->right);

       /*Dequeue node and make it temp_node*/
       temp_node = deQueue(queue, &front);
   }
}
```
