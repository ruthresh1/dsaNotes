## Queue

* another restrictive DS, that follows the FIFO principle
* eg. a queue of people waiting for an icecream
* they are trickier to implement because we have to keep track of both ends (front and back)
* os process scheduling, cache implementations
* primary operations include enqueue, dequeue

### Types of priority queues
* Linear queue
* Circular queue
* Priority queue

```java
// Circular Queue implementation with array, because they are simpler
// normal queues don't have the modulus operation to circle back hence is unusable once front catches up to back
public class Queue<T> {

    private int maxSize;
    private G[] arr;
    private int front;
    private int back;
    private int currentSize;

    // @SuppressWarnings("unchecked")
    public Queue(int maxSize) {
        this.maxSize = maxSize;
        arr = (T[]) new Object[maxSize];
        front = 0;
        back = -1;
        currentSize = 0;
    }
    public int getMaxSize() {
        return maxSize;
    }
    public int getCurrentSize() {
        return currentSize;
    }
    public boolean isEmpty() {
        return back == -1;
    }
    public boolean isFull() {
        return currentSize == maxSize;
    }
    public T top() {
        return arr[front];
    }

    public void enqueue(T val) {
        if(isFull()) {
            return; // or throw error
        }
        back = (back + 1) % maxSize;
        arr[back] = val;
        currentSize++;
    }
    public T dequeue() {
        if(isEmpty()) {
            return; //or throw error
        }
        T temp = arr[front];
        front = (front + 1) % maxSize;
        currentSize--;
        return temp;
    }
}
```