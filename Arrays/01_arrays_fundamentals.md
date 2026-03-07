# Arrays — Fundamentals (DSA)

## 1. What is an Array?

An **array** is a data structure that stores **multiple elements of the same type in contiguous memory locations**.

Arrays allow **fast access to elements using an index**.

Example:

```java
int[] arr = {10, 20, 30, 40, 50};
```

Visualization:

| Index | Value |
| ----- | ----- |
| 0     | 10    |
| 1     | 20    |
| 2     | 30    |
| 3     | 40    |
| 4     | 50    |

### Key Characteristics

* Stores elements of the **same data type**
* Elements are stored in **contiguous memory**
* Size is usually **fixed**
* **Index-based access**

---

# 2. Memory Representation of Arrays

Arrays are stored in **continuous memory locations**.

Example:

```
arr = {10,20,30,40}
```

Memory representation:

| Address | Value |
| ------- | ----- |
| 1000    | 10    |
| 1004    | 20    |
| 1008    | 30    |
| 1012    | 40    |

### Address Calculation

Address of an element:

```
Address = Base Address + (Index × Size of Data Type)
```

Example:

```
Base Address = 1000
Index = 2
Size of int = 4 bytes

Address = 1000 + (2 × 4)
        = 1008
```

This direct calculation makes **array access very fast (O(1))**.

---

# 3. Indexing (0-Based Indexing)

Array indexing starts at **0**.

Example:

```
arr = {10,20,30,40}
```

| Index | Value |
| ----- | ----- |
| 0     | 10    |
| 1     | 20    |
| 2     | 30    |
| 3     | 40    |

Accessing elements:

```java
System.out.println(arr[0]); // 10
System.out.println(arr[2]); // 30
```

### Why 0-based indexing?

Because address calculation becomes simpler:

```
Address = Base + (Index × Size)
```

---

# 4. Traversing an Array

**Traversing** means visiting each element in the array.

### Method 1 — Using a For Loop

```java
int[] arr = {10,20,30,40};

for(int i = 0; i < arr.length; i++){
    System.out.println(arr[i]);
}
```

### Method 2 — Enhanced For Loop

```java
for(int num : arr){
    System.out.println(num);
}
```

### Time Complexity

```
O(n)
```

because every element must be visited once.

---

# 5. Time Complexity of Array Operations

| Operation                       | Time Complexity  | Explanation                                                                                                                               |
| ------------------------------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Access / Read by Index          | O(1)             | The memory address of any element can be directly calculated from its index, so access happens in constant time regardless of array size. |
| Search (Unsorted)               | O(N)             | In the worst case (element at the end or not present), a linear search checks every element in the array.                                 |
| Search (Sorted – Binary Search) | O(log N)         | For a sorted array, binary search repeatedly halves the search space to locate the element.                                               |
| Insertion at End                | O(1) (Amortized) | Dynamic arrays usually append elements in constant time, though occasional resizing may take O(N).                                        |
| Insertion at Beginning / Middle | O(N)             | All elements after the insertion point must shift one position to the right to create space.                                              |
| Deletion at End                 | O(1)             | Removing the last element does not affect any other element’s position.                                                                   |
| Deletion at Beginning / Middle  | O(N)             | All elements after the deleted element must shift left to fill the gap.                                                                   |


### Example — Searching

```java
for(int i = 0; i < arr.length; i++){
    if(arr[i] == target){
        return i;
    }
}
```

Worst case:

```
O(n)
```

---

# 6. Static vs Dynamic Arrays

## Static Array

Size is fixed at creation.

Example:

```java
int[] arr = new int[5];
```

Characteristics:

* Fixed size
* Cannot grow or shrink
* May waste memory if not fully used

---

## Dynamic Array

Dynamic arrays can **resize automatically**.

Example in Java:

```java
ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);
```

Dynamic arrays internally:

1. Create array
2. When full → create larger array
3. Copy old elements

Typical resizing strategy:

```
New Size = Old Size × 2
```

Amortized insertion complexity:

```
O(1)
```

---

# 7. In-Place vs Extra Space Operations

## In-Place Algorithm

An algorithm that **does not use additional memory** beyond a few variables.

Example: reversing an array.

```
Input:  [1,2,3,4]
Output: [4,3,2,1]
```

Java implementation:

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

Space complexity:

```
O(1)
```

---

## Extra Space Algorithm

Uses an additional data structure.

Example:

```java
int[] newArr = new int[arr.length];

for(int i = 0; i < arr.length; i++){
    newArr[i] = arr[arr.length - 1 - i];
}
```

Space complexity:

```
O(n)
```

---

# End of Topic
