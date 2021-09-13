## Medium Problems on Arrays

### Question 1
### Given 2 arrays that represents numbers find their sum (Big integer addition)

Question 1
Given 2 arrays that represents numbers find their sum (Big integer addition)
```java
public int[] add(int[] a, int[] b) {

    int [] larger = a.length > b.length ? a : b;
    int[] smaller = a == larger ? b : a;
    int[] result = new int[larger.length + 1];
    smaller = resize(smaller, larger.length);
    int carry = 0;
    for(int i = larger.length - 1; i >= 0; i++) {
        int sum = larger[i] + smaller[i]+ carry;
        carry = sum/10;
        result[i+1] = sum % 10;
    }
    result[0] = carry;
    return result;
}