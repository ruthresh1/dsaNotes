## Sorting

#### rearrangement of elements in a decreasing or increasing order, usually used as a precussor for search

### Slow sorting algorithms
* used for small set of input
* best for almost sorted input

### Bubble sort
The simplest of the sorting algorithms
Basically its just comparing two numbers and changing their position based on their value
Lower value is moved front or the higher value sinks down/to the end

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

Optimized Bubble sort
* breaks the outer loop if there have been no swaps concluding that the array is sorted
* doesn't change the Time complexity, just 
```java
// Optimized Bubble sort in Java
static void optimizedBubbleSort(int arr[]) {
    int size = arr.length;
    for(int i = 0; i < size - 1; i++) {
        boolean swapped = false;
        for(int j = 0; j < size - i - 1; j++) {
            if(arr[j] > arr[j+1]) {
                // swaps if they are not in ascending order
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
                swapped = true;
            }
        }
        if(!swapped) {
            break;
        }
    }
}
```

### Insertion sort
Just like sorting a bunch of playing cards with your hand

```java
//Insertion sort example
static void insertionSort(int arr[]) {
    int size = arr.length;
    for(int step = 1; step < size; step++) {
        int key = arr[step];
        int j = step - 1;
        // TODO find the right comment
        while( j >= 0 && key < arr[j]) {
            arr[j + 1] = arr[j];
            j--;
        }
        // place key after element smaller than it
        arr[j + 1] = key;
    }
}
```
| Particular | Value |
| --------- | ----- |
| Time Complexity    | O(n2)  |
| Space Complexity    | O(1)  |
| Stable  | Yes  |

### Selection sort
on each pass find the min and pull it to the front

```java
static void selectionSort(int arr[]) {
    int size = arr.length;
    for(int step = 0; step < size - 1; step++) {
        int minIndex = step;
        // finding the min index
        for(int i = step + 1; i < size; i++) {
            if(arr[i] < arr[minIndex]) {
                minIndex = i;
            }
        }
        // swap min to the front
        int temp = arr[step];
        arr[step] = arr[minIndex];
        arr[minIndex] = temp;
    }
}
```
| Particular | Value |
| --------- | ----- |
| Time Complexity    | O(n2)  |
| Space Complexity    | O(1)  |
| Stable  | No  |

### Fast sorting algorithms

### Merge sort

### Quick sort