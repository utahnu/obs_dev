Daily Note: [[2023-04-11]] -- [*created*:: 2023-04-11] #cs235 

A **Complete binary tree** is a binary tree where every row but the last must be completely filled
and the elements on the last row must be packed to the left

The **Heap Order Property** means that the value of any node is greater than its parent's value
(heavy things sink to the bottom)

## Inserting into a Heap

- Add an item into the next open slot
- Percolate up until the value is in the correct location

## Removing from a Heap

- Replace the top with the last item
- Percolate down until order is correct

## Big-O:

- Insertion: converges to O(1)
- Removal: O(log n)


(0 index)
- left index:
	- $2(i+1)-1$
- right index:
	- $2(i+1)$
- parent index:
	- $(i+1)//2-1$

(1 index)
- left index:
	- $2i$
- right index:
	- $2i + 1$
- parent index:
	- $i//2$

