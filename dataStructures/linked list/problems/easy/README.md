### Easy problems

#### Q1. Find kth to last node in Linked list
#### Q2. Find the median of a given linked list

#### Q1. Find kth to last node in Linked list
#### Solution
```java
class Solution1 {

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

#### Q2. Find the median of a given linked list

### Solution
```java
class Solution2 {

    Node findMedian(Node head) {
        Node fast = head, slow = head;
        while(fast != null) {
            slow = slow.next;
            fast = fast.next;
            if(fast != null) {
                fast = fast.next;
            }
        }
        return slow;
    }
}
```