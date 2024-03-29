## Easy Problems on Trees

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

// Driver/Client call
sumOfNode(root);
```

### Question 3
### Given a binary tree perform a level order traversal?

### Solution
```java
public static void levelOrderTraversal(Node node) {

    List<Node> queue = new LinkedList<>();
    queue.add(node);
    while(!queue.isEmpty()) {
        Node curr = queue.removeFirst();
        System.out.print(curr.data+ " ");
        if(curr.left != null) {
            queue.addLast(curr.left);
        }
        if(curr.right != null) {
            queue.addLast(curr.right);
        }
    }
}

// Driver/Client call
levelOrderTraversal(root);
```

### Question 4
### Find the height of a given Binary tree?

### Solution
```java
public int height(Node node) {

    if(node == null) {
        return 0;
    }
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    return 1+ Math.max(leftHeight, rightHeight);
}

// Driver call
// initialize tree with 
// Node root = ...
int height = height(root);
```

### Question 5
### Find the number of leaf nodes in a given Binary tree?

### Solution
```java
int countLeafNodes(Node node) {
    if(node == null) {
        return 0;
    }
    if(node.left == null && node.right == null) {
        return 1; // is a leaf
    }
    return countLeafNodes(node.left) + countLeafNodes(node.right);
}

// Driver call
// initialize tree with 
// Node root = ...
int count = countLeafNodes(root);
```

### Question 6
### Print all the nodes at depth k in a given Binary tree?

### Solution
```java
void printNodesAtDepthK(Node node, int k) {

    if(node == null) {
        return;
    }
    if(k == 0) {
        System.out.print(node.data+ " ");
    }
    printNodesAtDepthK(node.left , k-1);
    printNodesAtDepthK(node.right, k-1);
}

// Driver call
// initialize tree with 
// Node root = ...in
printNodesAtDepthK(root, k);
```

### Question 7
### Search for a key in a given binary search tree!

### Solution
```java
boolean search(Node node, int key) {

    if(node == null) {
        return false;
    }
    if(node.data == key) {
        return true;
    } else if(node.data > key) {
        return search(node.left, key); 
    } else {
        return search(node.right, key);
    }
}

// Driver call
// initialize tree with 
// Node root = a BST
search(root, k);
```