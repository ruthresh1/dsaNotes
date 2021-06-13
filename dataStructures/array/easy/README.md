## Problems on Arrays

### Question 1
### Given an array of numbers, replace each even number with 2 of the same

### Solution
```java
public void cloneEvenNumbers(int[] arr) {
    int end = arr.length;
    int i = findLastNumber(arr);
    while(i >= 0) {
        if(arr[i] % 2 == 0) {
            end--;
            a[end] = a[i];
        }
        end--;
        a[end] = a[i];
        i--;
    }
}
```