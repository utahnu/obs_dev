Daily Note: [[2023-03-14]] -- [*created*:: 2023-03-14] #cs235 

Like a list, but each node can have more nodes

# Parts of a tree

- Root:
	- Node with no parent
- Leaf:
	- Node with no child
- Depth:
	- Distance of a node to the root
- Height:
	- Distance of a node to it's lowest leaf
	- Height of a tree is the height of its root

	Trees are recursive in nature

# Searching a Tree

## Depth-First-Search (DFS)

Before moving on to the second child, you explore the children of the first child

	Completed with a Stack structure

Example print function:
```cpp
template<class T>
void dfs_recurse(Node<T>*& node) {
	std::cout << node->value << std::endl;
	for(auto child:node->children) {
		dfs_recurse(child)
	}
}
```

==In general, it doesn't matter in what order we access the children==

## Breadth-First-Search (BFS)

Visit all children of a node before exploring their children

	Completed with a Queue structure 

---

> [!Traversal]
> The process of listing nodes inn a tree is called **Traversal**
> DFS and BFS are two strategies. There is another question, however:
> *Do you process the current node before or after you process the children?*
> - **Preorder traversal** - process a node before the children 
> - **Postorder traversal** - process a node after the children 

### Preorder DFS:
```cpp
template<class T>
void dfs_recurse(Node<T>*& node) {

	std::cout << node->value << std::endl;
	
	for(auto child:node->children) {
		dfs_recurse(child)
	}
	
}
```
### Postorder DFS:
```cpp
template<class T>
void dfs_recurse(Node<T>*& node) {

	for(auto child:node->children) {
		dfs_recurse(child)
	}
	
	std::cout << node->value << std::endl;
	
}
```

# Binary Search Trees
(BST)

**Extra Qualities:**
- No Duplicate Values
- Each node has at least two children:
	- a `left` subtree whose max value is ==smaller== than the current value
	- a `right` subtree whose min value is ==larger== than the current value

## Traversing through a BST:

For generic trees, traversal order is undefined
For BST, you always iterate from `left` to `right`

inorder traversal:
`left`,`this`,`right`
always a sorted list ^^