Daily Note: [[2023-03-21]] -- [*created*:: 2023-03-21] #cs235 

## BST Performance Review

- The O($\log n$) performance of BST depends on the ==balance== of the tree

# Defining Balance:

The difference in height between the children of a node is always less than 2

$$\mathrm{height}(right) - \mathrm{height}(left)$$

and can also be negative, to indicate direction of imbalance
the height of `nulllptr` is 0

![[Pasted image 20230321141720.png|300]]

# Left-Left and Right-Right Imbalance

When the imbalanced side also is imbalanced:

![[drawing_2023-03-21]]

## Balancing:

### In the Right-Right Case:
![[drawing_2023-03-21_0|500]]

### how to calculate the height of a node:
*make a height function*
`max(left,right) + 1`

==update the height of each node as the recursion comes back up its layers==

### To rebalance left-left:

```cpp
//the handle_imbalance function
void promote_left_child(Node* &node) {
	Node* new_root = node->left;
	node->left = node->left->right;
	new_root->right = node;
		node = new_root;
}
//call an update_height function
```

# Left-Right and Right-Left Imbalance

1. Rotate the Heavy Child to create **Left-Left** or **Right-Right**
2. Rotate the original node

![[drawing_2023-03-21_1|700]]

```cpp
rebalance_negative(Node* &node) {
	if (node->left.balance > 0) {
		promote_right_child(node->left);
	}
	promote_lelft_child(node);
}

rebalance_positive(Node* &node) {
	if (node->left.balance < 0) {
		promote_left_child(node->right);
	}
	promote_right_child(node);
}
```


## When to call?

```cpp
if _insert(child, value) {
	update_height;
	rebalance_if_necessary;
	return true;
}
```