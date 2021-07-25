## Medium Problems on Trees

### Question 1
### Remove all leaf nodes of a given binary Tree!

### Solution
```java
Node removeLeaves(Node node) {
    if(root == null ||
    (root.left == null && root.right == null)) { // leaf
        return null;
    }
    root.left = removeLeaves(node.left);
    root.right = removeLeaves(node.right);
    return root;
}

// Driver call
// Node root = ..
root = removeLeaves(root);
```

