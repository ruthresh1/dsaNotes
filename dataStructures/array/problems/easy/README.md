## Problems on Arrays

### Question 1
### Given an array of numbers, replace each even number with 2 of the same
### Question 2
### Find a sub-array that sums to a target
### Question 3
### 

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

### Question 2
### Find a sub-array that sums to a target

### Solution
```java
class Pair {
    int first;
    int second;
}

Pair subArraySum(int arr[], int target) {
    int start = 0, end = 0, sum = arr[0];
    while(start < arr.length) {
        if(start > end) {
            end = start;
            sum = arr[start];
        }
        if(sum < target) {
            if(end == arr.length - 1) {
                break;
            }
            end++;
            sum += arr[end];
        } else if(sum > target) {
            sum -= arr[start];
            start++;
        } else {
            return new Pair(start, end);
        }
    }
    return null;
}
```