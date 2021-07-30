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

### Question 3
### Check if a given binary tree is balanced!

### Solution
```java
boolean isBalanced(Node node) {
    if(node == null) {
        return true;
    }
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    if(Math.abs(leftHeight - rightHeight) > 1) {
        return false;
    }
    boolean isLeftBalanced = isBalanced(node.left);
    boolean isRightBalanced = isBalanced(node.right);
    return isLeftBalanced && isRightBalanced;
}

int height(Node node) {
    if(node == null) {
        return 0;
    }
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    return 1+ Math.max(leftHeight, rightHeight);
}

// Driver call
// Node root = ...
boolean balanced = isBalanced(root);
```

### Question 4
### Measure the diameter of a given binary tree!

### Solution
```java
int measureDiameter(Node node) {
    if(node == null) {
        return 0;
    }
    int option1 = height(node.left) + height(node.right);
    int option2 = measureDiameter(node.left);
    int option3 = measureDiameter(node.right);
    return Math.max(option1, Math.max(option2, option3));
}

int height(Node node) {
    if(node == null) {
        return 0;
    }
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    return 1+ Math.max(leftHeight, rightHeight);
}

// Driver call
// Node root = ...
int diameter = measureDiameter(root);
```
