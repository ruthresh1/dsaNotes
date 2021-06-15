## Sorting

#### rearrangement of elements in a decreasing or increasing order, usually used as a precussor for search

### Slow sorting algorithms

### Bubble sort
The simplest of the sorting algorithms
Basically its just comparing two numbers and changing their position based on their value
Lower value is pushed ahead or the higher value sinks down

```java
// Bubble sort in Java
import java.util.Arrays;

class Sort {

    static void bubbleSort(int arr[]) {
        int size = arr.length;
        for(int i = 0; i < size - 1; i++) {
            for(int j = 0; j < size - i - 1; j++) {
                if(arr[j] > arr[j+1]) {
                    // swaps if they are not in ascending order
                    int temp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = temp;
                }
            }
        }
    }

    public static void main(String args[]) {

        int[] data = { 4, 3, 1, 5 };
        Sort.bubbleSort(data);
        System.out.println(Arrays.toString(data));
    }
}
```


### Insertion sort


### Selection sort

### Fast sorting algorithms

### Merge sort

### Quick sort