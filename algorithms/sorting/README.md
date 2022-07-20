## Sorting

#### rearrangement of elements in a decreasing or increasing order, usually used as a precursor for search

### Slow sorting algorithms
* used for small set of input
* best for almost sorted input

### Bubble sort
The simplest of the sorting algorithms
Basically its just comparing two numbers and changing their position based on their value
Lower value is moved up or the higher value sinks down/to the bottom

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

    static void bubbleSort2(int arr[]) {
        int size = arr.length;
        int temp;
        for(int i = 0; i < size - 1; i++) {
            for(int j = size - 1; j >= i; j--) {
                if(arr[j] < arr[j-1]) {
                    // swaps if they are not in ascending order
                    temp = arr[j];
                    arr[j] = arr[j-1];
                    arr[j-1] = temp;
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
Eg.

| Particular | Value |
| --------- | ----- |
| Time Complexity    | O(n2)  |
| Space Complexity    | O(1)  |
| Stable  | Yes  |
| InPlace  | Yes  |

Optimized Bubble sort
* breaks the outer loop if there have been no swaps concluding that the array is sorted
* doesn't change the Time complexity, just optimal while running
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
Good for sorting smaller list of values
Best case running time is linear

```java
//Insertion sort example
static void insertionSort(int arr[]) {
    int size = arr.length;
    for(int step = 1; step < size; step++) {
        int key = arr[step];
        int j = step - 1;
        // shift biggers values to right find right place for key
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
| InPlace  | Yes  |

### Selection sort
on each pass find the min and swap it to the front

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

static void selectionSortWithValue(int arr[]) {
    int size = arr.length, minIndex, minValue;
    for(int step = 0; step < size - 1; step++) {
        minIndex = step;
        minValue = arr[step];
        // finding the min index
        for(int i = step + 1; i < size; i++) {
            if(arr[i] < minValue) {
                minValue = arr[i];
                minIndex = i;
            }
        }
        // swap min to the front
        arr[minIndex] = arr[step];
        arr[step] = minValue;
    }
}
```
| Particular | Value |
| --------- | ----- |
| Time Complexity    | O(n2)  |
| Space Complexity    | O(1)  |
| Stable  | No  |
| InPlace  | Yes  |

### Fast sorting algorithms

### Merge sort
* A faster sorting algorithm that uses Divide and Conquer
* It uses O(n) auxillary space

```java
static void mergeSort(int arr[]) {
    quickSort(arr, 0, arr.length);
}

static void mergeSort(int arr[], int start, int end) {
    if(start == end) 
        return;
    int mid = start + (end - start)/2;
    mergeSort(arr, start, mid);
    mergeSort(arr, mid+1, end);
    merge(arr, start, mid, end);
}

static void merge(int arr[], int start, int mid, int end) {

    int n1 = mid - start + 1;
    int n2 = end - mid;
    int L[] = new int[n1];
    int R[] = new int[n2];
    for(int i = 0; i < n1; i++)
        L[i] = arr[start + i];
    for(int j = 0; j < n2; j++)
        R[j] = arr[mid + 1 + j];
    int i = 0, j = 0, k = start;
    while(i < n1 && j < n2) {
        if(arr[i] <= arr[j]) {
            arr[k] = L[i];
            i++;
        } else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }
    while(i < n1) {
        arr[k] = L[i];
        i++; k++;
    }
    while(j < n2) {
        arr[k] = R[j];
        j++; k++;
    }
}
```
| Particular | Value |
| --------- | ----- |
| Time Complexity    | O(nlog n)  |
| Space Complexity    | O(n)  |
| Stable  | Yes  |
| InPlace  | No  |


### Quick sort
* the most widely used sorting algorithm (as a part of Tim sort)
* is not stable but is inplace
* there are different ways to partition (lomuto, hoare's)

```java
static void quickSort(int[] arr, int low, int high) {
    if(low < high) {
        int p = partition(arr, low, high);
        quickSort(arr, low, p - 1);
        quickSort(arr, p + 1, high);
    }
}
// lomuto's partition
int partition(int[] arr, int low, int high) {
    int pivot = arr[high];
    int i = low - 1;
    for(int j = low, j < high; j++) {
        if(arr[j] < pivot) {
            i++;
            swap(arr, i, j);
        }
    }
    swap(arr, i+1, high);
    return i+1;
}

//hoare's partition
```

| Particular | Value |
| --------- | ----- |
| Time Complexity    | O(n2)  | Average case O(nlogn)
| Space Complexity    | O(1)  |
| Stable  | No  |
| InPlace  | Yes  |

### Sorting algorithms that use transform and conquer
### Heap sort

### counting sort

### radix sort
