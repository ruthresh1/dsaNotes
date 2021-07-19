## Problems on Trees

### Question 1
### Find the number of nodes in a given binary tree?

### Solution
```java
class Node {
    int data;
    Node left, right;
}

public int numberOfNodes(Node root) {
    if(root == null) {
        return 0;
    }
    int leftCount = numberOfNodes(root.left);
    int rightCount = numberOfNodes(root.right);
    return 1+ leftCount+ rightCount;
}
```

