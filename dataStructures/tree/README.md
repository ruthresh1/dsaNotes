## Tree

* a non-linear, hierachical data structure (not linear like array)
* has one root node and some children depending on type
* used to represent a family tree (relationships), file systems
* a balance between memory and speed of access O(log n)

### Types of Trees
* Generic Tree
* Binary Tree
  * each node can have at most 2 children
  * Types
    * Complete binary tree - the way a tree should be filled left to right, all levels complete, excepting the last one
    * Full binary tree - all nodes should have 0 or 2 children, may not be complete binary tree
    * Perfect binary tree - should be both complete and full binary tree
  * Binary Search Tree (BST)

### Defenitions
* path − refers to the sequence of nodes along the edges of a tree.
* root − the node at the top of the tree is called root. There is only one root per tree and one path from the root node to any node.
* parent − all the nodes except the root node has one edge upward to a node called parent.
* child − the node below a given node connected by its edge downward is called its child node.
* leaf − the node which does not have any child node is called the leaf node.
* subtree − represents the descendants of a node. (subset)
* visiting − refers to checking the value of a node when control is on the node.
* traversing − refers passing through nodes in a specific order.
* levels − Level of a node represents the generation of a node. If the root node is at level 0, then its next child node is at level 1, its grandchild is at level 2, and so on.
* keys − refer to the value of a node based on which a search operation is to be carried out for a node.
* height - is the number of edges from the root to the node
* siblings - nodes that have the same parent
* ancestor - parent and grandparent nodes and so on

### Types of Traversal
* InOrder
  * left subTree
  * current node
  * right subTree
* PreOrder
  * current node
  * left subTree
  * right subTree
* PostOrder
  * left subTree
  * right subTree
  * current node
* Level order traversal
  * use a queue - enqueue root to queue
  * as long as queue is not empty
  * dequeue and print value, enqueue left and right to queue