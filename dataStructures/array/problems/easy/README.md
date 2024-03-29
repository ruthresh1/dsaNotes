## Problems on Arrays

### Question 1
### Find the largest in the given array
### Question 2
### Check if a given number is present in the array
### Question 3
### Given an array of numbers, replace each even number with 2 of the same
### Question 4
### Find a sub-array that sums to a target


Question 1
Find the largest in the given array
```java
public int findLargest(int[] arr) {

    int max = Integer.MIN_VALUE;
    for(int num : arr) {
        if(num > max) {
            max = num;
        }
    }
    return max;
}
```

Question 2
Check if a given number is present in the array

Solution
```java
public int linearSearch(int[] arr, int key) {

    for(int i = 0; i < arr.length; i++) {
        if(arr[i] == key) {
            return i;
        }
    }
    return -1;
}
```

Question 3
Given an array of numbers, replace each even number with 2 of the same

Solution
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

Question 4
Find a sub-array that sums to a target

Solution
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