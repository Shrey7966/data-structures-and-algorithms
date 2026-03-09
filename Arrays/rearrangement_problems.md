# Rearrangement Problems

These problems involve **modifying array positions**.

---

# 1. Move Zeros to End

### Idea

Use two pointers to move non-zero elements forward.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int j = 0;

for(int i = 0; i < arr.length; i++){

    if(arr[i] != 0){

        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;

        j++;
    }
}
```

---

# 2. Move Zeros to Beginning

### Idea

Traverse from end and move non-zero elements backwards.

### Time Complexity

```
O(n)
```

### Java Implementation

```java
int j = arr.length - 1;

for(int i = arr.length - 1; i >= 0; i--){

    if(arr[i] != 0){

        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;

        j--;
    }
}
```

---
