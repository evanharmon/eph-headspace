# ALGORITHMS - DOUBLY LINKED LIST

## Advantages
Can move in both directions
Can delete current node without knowing previous node

## Disadvantages
Each node requires an extra pointer, requiring more space.
The insertion or deletion of a node takes a bit longer (more pointer operations)

## Struct
```
struct DLLNode {
  int data;
  struct DLLNode *next;
  struct DLLNode *prev;
}
```

## Insert At Head
Update new node->next pointer to point to current head node
Set new node->prev pointer to NULL
Update current head->prev pointer to new node
