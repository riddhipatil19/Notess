## 📘 Concept Overview

Searching is the process of finding an element in a collection like an array, matrix, or tree.  
There are two major types:
- **Linear Search**: Brute-force scan
- **Binary Search**: Divide and conquer (sorted data only)

---

## 🧠 1. Linear Search

- Works on unsorted or sorted data
- Time: O(n), Space: O(1)

```java
int linearSearch(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}
```

---

## ⚡ 2. Binary Search (Iterative)

- Works on **sorted arrays**
- Time: O(log n), Space: O(1)

```java
int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

---

## 🌀 3. Binary Search (Recursive)

```java
int binarySearch(int[] arr, int low, int high, int target) {
    if (low > high) return -1;
    int mid = low + (high - low) / 2;
    if (arr[mid] == target) return mid;
    else if (arr[mid] > target) return binarySearch(arr, low, mid - 1, target);
    else return binarySearch(arr, mid + 1, high, target);
}
```

---

## 🎯 4. Lower Bound & Upper Bound

> **Only in sorted arrays**

- **Lower Bound**: First index `≥ target`
- **Upper Bound**: First index `> target`

```java
// Lower Bound
int lowerBound(int[] arr, int target) {
    int low = 0, high = arr.length;
    while (low < high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] < target) low = mid + 1;
        else high = mid;
    }
    return low;
}
```

---

## 🧪 5. Search in Rotated Sorted Array

```java
int searchRotated(int[] nums, int target) {
    int low = 0, high = nums.length - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (nums[mid] == target) return mid;

        if (nums[low] <= nums[mid]) {
            if (target >= nums[low] && target < nums[mid]) high = mid - 1;
            else low = mid + 1;
        } else {
            if (target > nums[mid] && target <= nums[high]) low = mid + 1;
            else high = mid - 1;
        }
    }
    return -1;
}
```

---

## 🔲 6. Search in 2D Matrix (Sorted)

```java
boolean searchMatrix(int[][] matrix, int target) {
    int row = 0, col = matrix[0].length - 1;
    while (row < matrix.length && col >= 0) {
        if (matrix[row][col] == target) return true;
        else if (matrix[row][col] > target) col--;
        else row++;
    }
    return false;
}
```

---

## 💡 Tips

- Always check if the array is **sorted** before using binary search.
- Handle edge cases: empty array, single element, out of bounds.
- Use binary search for **min/max value problems** ("search on answer" pattern).

---

## ✅ Common Problems

- Binary Search (basic)
- First and Last Position of Target (Leetcode 34)
- Search in Rotated Array
- Find Peak Element
- Matrix Search
- Koko Eating Bananas (binary search on answer)
- Minimum in Rotated Sorted Array

---

## 🔗 Related Topics
- `/Arrays`
- `/Sorting` (often needed before binary search)
- `/Heap` (for top-k style problems)
