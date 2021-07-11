## Array

* Contiguous blocks of memory that can store data of same type (homogenous data)
Eg. A tie box
* it has a fixed size
* we access elements of an array using its index, which starts from 0
* arrays are of two types - static and dynamic

### Static arrays
### Properties
* Fixed size (not dynamic)
* indexed 
* quick access

### Big O
| Operation | Big O |
| --------- | ----- |
| Access    | O(1)  |
| Search    | O(1)  |
| Insertion | O(n)  |
| Deletion  | O(n)  |
---------------------

### Why Array?
Usually while programming we deal with a list/set of common data for which we need them to be stored some where. 
Instead of using individual variables, we use an array.

### Array Types
1. 1-D Array
2. Multidimensional arrays

### 2D Arrays
* A two dimensional array is essentially a matrix of information, essentially a table
* It is a row of 1d arrays
--------------------------------------
### Java

Arrays in Java are awesome
Creation
```java
// 1d array
int arr[] = new int[10];
arr[0] = 1;
arr[0];     // 1
arr[1];     // 0
arr.length; // 10
// Traversing array using loops
for(int i = 0; i < arr.length; i++) {
    arr[i] = i+1;
}
// for each loop
for(int a : arr) {
    System.out.println(a);
}

// 2d arrays
int subject = 6;
int students = 50;
int[][] marks = new int[subject][students];
int marks = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 0, 1, 2}
}
// access
a[2][0];  // 9
// Traversing a 2d array
for(int i = 0; i < marks.length; i++) {
    for(int j = 0; j < marks[i].length; j++) {
        System.out.println(marks[i][j]);
    }
}
```

### Dynamic arrays
* Arrays in programming languages like Python and Javascript are dynamic and usually referred to as lists
* These are arrays that aren't fixed in size
* Through amortized analysis we can prove that insertion into dynamic array is O(n)

### Python
* Arrays in Python are called lists, unlike in Java they are mutable and not fixed.
* A tuple is fixed size immutable list

```python
arr = []
```


