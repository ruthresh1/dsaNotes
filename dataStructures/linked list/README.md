## Linked List

* linked list are node based structres which are not contiguous
* that are like distributed arrays boxes
* they take up more space than arrays
* but insertion and deletion are faster in linked lists
* yet there is no random access, access has to be sequentially
* every node has data and reference to the next node


### Types
1. Linked List
2. Doubly linked list
3. Circularly linked list

```java
// Singly linked list
class Node {
    int data;
    Node next;
}


Node first = new Node();
first.data = 1;
Node second = new Node();
second.data = 2;
first.next = second;
Node third = new Node();
third.data = 3;
second.next = third;
Node head = first;
// 1 -> 2 -> 3 -> null

// Doubly linked list
class DNode {
    int data;
    Node prev;
    Node next;
}

Node first = new Node();
first.data = 1;
Node second = new Node();
second.data = 2;
second.prev = first;
first.next = second;
Node third = new Node();
third.data = 3;
third.prev = second;
second.next = third;
Node head = first;
// null <- 1 <-> 2 <-> 3 -> null
```

### Questions