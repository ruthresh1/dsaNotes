## Medium Problems on Trees

### Question 1
### Remove all leaf nodes of a given binary Tree!

### Solution
```java
Node removeLeaves(Node node) {
    if(node == null ||
    (node.left == null && node.right == null)) { // leaf
        return null;
    }
    node.left = removeLeaves(node.left);
    node.right = removeLeaves(node.right);
    return node;
}

// Driver call
// Node root = ..
root = removeLeaves(root);
```

### Question 2
### Mirror a given binary tree

### Solution
```java
void mirrorTree(Node node) {
    if(node == null) {
        return;
    }
    mirrorTree(node.left);
    mirrorTree(node.right);
    Node temp = node.left;
    node.left = node.right;
    node.right = temp;
}

// Driver call
// Node root = ..
mirrorTree(root);
```