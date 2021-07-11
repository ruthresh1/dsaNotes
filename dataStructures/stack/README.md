## Stack

* a restrictive data structure that emulates real life stacks
* eg. the way undo works
* follows LIFO (Last in First Out)
* used in DFS and expression evaluation algorithms
* operations - push, pop, peek (top)
* need to keep track of top to perform operations

```java
class Stack<G> {

    private int maxSize;
    private int top;
    private G arr[];

    // @SuppressWarnings("unchecked")
    public Stack(int maxSize) {
        this.maxSize = maxSize;
        this.top = -1;  // initially stack is empty
        this.arr = (G[]) new Object[maxSize];
    }
    public int getCapacity() {
        return maxSize;
    }
    public boolean isEmpty() {
        return top == -1;
    }
    public boolean isFull() {
        return top == maxSize-1;
    }
    public G top() {
        if(isEmpty()) {
            return null;
        }
        return arr[top];
    }

    public void push(G value) {
        if(isFull()) {
            System.out.println("Stack is full"); // or throw error
            return;
        }
        arr[++top] = value;
    }

    public G pop() {
        if(isEmpty()) {
            return;
        }
        return arr[top--];
    }
}
// All basic operations on Stack is O(1)
```

