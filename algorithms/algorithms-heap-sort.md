# HEAP SORT
(http://www.geeksforgeeks.org/binary-heap/)

## Functions
PercolateDown
PercolateUp
CreateHeap
Parent
LeftChild
RightChild
GetMax
DeleteMax
Insert
ResizeHeap
DestroyHeap
BuildHeap
HeapSort

## Parent(Heap, int)
Get parent node location in tree by int
- check if int parameter is less than or equal to 0 then return
- Check, if int parameter is greater than or equal to count of the Heap
parameter than return
- Calculate parent int by reducing int parameter by one, then dividing by two
for other side of binary tree
- Return calculated parent int

## Left(Heap, int)
Get left child node location in tree by int
- Calculate left child location by multiplying int parameter by two, then add
one to move down tree from parent node
- Check, if calculated left child location is greater than or equal to Heap
parameter count, then return
- Return calculated left child location

## Right(Heap, int)
Get right child node location in tree by int
- Calculate right child location by multiplying int parameter by two, then add
two to move down tree from parent and left child node
- Check, if calculated right child location is greater than or equal to Heap
parameter count, then return
- Return calculated right child location

## GetMax(Heap)
Get root node value, root node always max
- check, if Heap parameter is equal to 0, than return since Heap is empty
- Return Heap node value at array index 0

## PercolateDown(Heap, int)
recursively heapify an element at location
- Calculate left child of int parameter
- Calculate right child of int parameter
- Check, if left child exists AND Heap array item at left location is greater
than Heap array item at int parameter, then set MAX to left child location,
else set MAX to int paramater
- Check, if right child exists AND Heap array item at right location is greater
than Heap array item at int parameter, then set MAX to right child location
- Check, if MAX does not equal int parameter then swap. Save node at Heap array
item input parameter to TEMP. Set node at heap array item int parameter To node
at Heap array item MAX. Set node at Heap array item MAX equal to TEMP
- Call PercolateDown with parameters Heap and MAX

## DeleteMax(Heap)
Delete node at root, root node is always max
- Check, if Heap count equals 0, return early since Heap empty
- Set DATA equal to node at Heap array item 0
- Set node at Heap array item 0 TO Heap array item ( count - 1)
- Decrement Heap count
- Call PercolateDown(Heap, 0)
- Return DATA

# Insert(Heap, data)
insert item in to binary Heap
- Check, if Heap count equals Heap capacity, then call ResizeHeap(Heap)
- Increment Heap count
- Set i equal to Heap count minus 1
- While i is greater than or equal to 0 AND data parameter is greater than Heap
array item at parent(I) node location, set Heap array item at i equal to Heap
array item at parent(i) node location, set i equal to (i - 1) divided by two
- Set Heap array item at i equal to data on paramefer

## ResizeHeap(Heap)
- create pointer to old Heap array
- Set Heap array equal to malloc with a size of Heap capacity times 2
- Check, return error if new Heap array is empty
- Incrementing for loop i less than or equal to Heap capacity, set Heap array
item at location i to old Heap array item at location i
- Set and multiply Heap capacity times two
- Free old Heap array from memory

## DestroyHeap(Heap)
- Check, return if Heap doesn't exist
- Free hear array from memory
- Free Heap from memory

## BuildHeap(heap, array, num)
- Check, return if Heap doesn't exist
- While num parameter is greater than Heap capacity, call ResizeHeap(Heap)
- For loop, i is less than num parameter, set Heap array item at i to array
parameter item at i
- Set Heap count equal to num parameter
- For loop, set i equal to num parameter minus one divided by two, as long as i
is less than or equal to 0, call PercolateDown(Heap, i)

## HeapSort(array, num)
- Call CreateHeap(num)
- Call BuildHeap(Heap, array, num)
- Set oldSize to Heap count
- For loop, i equals num parameter minus one, as long as i greater than zero,
decrement
