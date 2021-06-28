### Easy problems

#### Q1. Find kth to last node in Linked list

#### Solution
```java
class Qustion1 {

    Node findKthLastNode(Node head, int k) {
        Node first = head, second = head;
        for(int i = 0; i < k; i++) {
            first = first.next;
        }
        while(first != null) {
            first = first.next;
            second = second.next;
        }
        return second;
    }
}
```
