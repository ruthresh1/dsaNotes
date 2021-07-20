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

### Question 2
### Find the sum of the nodes in a given binary tree?

### Solution
```java
public static int sumOfNode(Node node) {
    if(node == null) {
        return 0;
    }
    int leftCount = sumOfNode(node.left);
    int rightCount = sumOfNode(node.right);
    return node.data+ leftCount+ rightCount;
}

// Driver/Client calls
sumOfNode(root);
```