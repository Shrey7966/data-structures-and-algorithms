# Basic Array Problems — Quick Revision Notes

These problems build the **foundation of array manipulation** and are commonly asked in beginner DSA interviews.

---

# 1. Traverse and Print Array

### Idea

Use a loop to visit each element and print it.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int[] arr = {1,2,3,4,5};

for(int i = 0; i < arr.length; i++){
    System.out.println(arr[i]);
}
```

---

# 2. Find Sum of Array Elements

### Idea

Traverse the array and keep adding elements to a variable.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int sum = 0;

for(int num : arr){
    sum += num;
}

System.out.println("Sum = " + sum);
```

---

# 3. Find Average of Array

### Idea

Average = Sum of elements / Number of elements

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int sum = 0;

for(int num : arr){
    sum += num;
}

double avg = (double) sum / arr.length;

System.out.println("Average = " + avg);
```

---

# 4. Find Maximum Element

### Idea

Track the largest value while traversing.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int max = Integer.MIN_VALUE;

for(int num : arr){
    if(num > max){
        max = num;
    }
}

System.out.println("Max = " + max);
```

---

# 5. Find Minimum Element

### Idea

Track the smallest value while traversing.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int min = Integer.MAX_VALUE;

for(int num : arr){
    if(num < min){
        min = num;
    }
}

System.out.println("Min = " + min);
```

---

# 6. Linear Search

### Idea

Check each element until the target is found.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int target = 4;

for(int i = 0; i < arr.length; i++){
    if(arr[i] == target){
        System.out.println("Found at index " + i);
        break;
    }
}
```

---

# 7. Count Occurrences of an Element

### Idea

Traverse array and increment counter when element matches target.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int target = 3;
int count = 0;

for(int num : arr){
    if(num == target){
        count++;
    }
}

System.out.println("Occurrences = " + count);
```

---

# 8. Check if Array is Sorted

### Idea

Compare each element with the next one.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
boolean isSorted = true;

for(int i = 0; i < arr.length - 1; i++){
    if(arr[i] > arr[i+1]){
        isSorted = false;
        break;
    }
}

System.out.println(isSorted);
```

---

# 9. Reverse an Array

### Idea

Use two pointers from start and end.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int left = 0;
int right = arr.length - 1;

while(left < right){

    int temp = arr[left];
    arr[left] = arr[right];
    arr[right] = temp;

    left++;
    right--;
}
```

---

# 10. Find Second Largest Element

### Idea

Track both largest and second largest values.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int max = Integer.MIN_VALUE;
int secondMax = Integer.MIN_VALUE;

for(int num : arr){

    if(num > max){
        secondMax = max;
        max = num;
    }
    else if(num > secondMax && num != max){
        secondMax = num;
    }
}

System.out.println("Second Largest = " + secondMax);
```

---

# 11. Find Second Smallest Element

### Idea

Track smallest and second smallest values.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int min = Integer.MAX_VALUE;
int secondMin = Integer.MAX_VALUE;

for(int num : arr){

    if(num < min){
        secondMin = min;
        min = num;
    }
    else if(num < secondMin && num != min){
        secondMin = num;
    }
}

System.out.println("Second Smallest = " + secondMin);
```

---

# 12. Difference Between Max and Min

### Idea

Find both max and min and subtract them.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int max = Integer.MIN_VALUE;
int min = Integer.MAX_VALUE;

for(int num : arr){

    if(num > max)
        max = num;

    if(num < min)
        min = num;
}

System.out.println("Difference = " + (max - min));
```

---


# Key Patterns Learned

```
Array Traversal
Min / Max tracking
Linear Search
Two Pointer Technique
In-place swapping
```

These concepts are foundational for:

* Two Pointer problems
* Sliding Window
* Binary Search
* Sorting algorithms
