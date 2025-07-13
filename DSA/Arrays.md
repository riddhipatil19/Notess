## 🔍 Concept Overview
- **Definition**: A collection of elements stored at contiguous memory locations.
- **Fixed size**: Declared at creation and cannot be resized.
- **Indexing**: 0-based indexing.

```java
int[] arr = new int[5];
int[] arr2 = {1, 2, 3, 4};
```

---

## ⚙️ Operations and Complexities

| Operation        | Description              | Time Complexity |
|------------------|--------------------------|-----------------|
| Access           | Get element at index     | O(1)            |
| Insert (end)     | Add at last index        | O(1)            |
| Insert (middle)  | Add at index, shift      | O(n)            |
| Delete (end)     | Remove last element      | O(1)            |
| Delete (middle)  | Shift elements left      | O(n)            |
| Search           | Linear or binary search  | O(n) / O(log n) |

---

## 🛠️ Common Array Operations in Java (Syntax Only)

| Operation            | Syntax Example                                |
|----------------------|-----------------------------------------------|
| Create               | `int[] arr = new int[5];`                     |
| Initialize (inline)  | `int[] arr = {1, 2, 3};`                      |
| Access               | `int x = arr[2];`                             |
| Update               | `arr[0] = 10;`                                |
| Length               | `arr.length`                                  |
| Clone                | `int[] copy = arr.clone();`                   |
| Sort (asc)           | `Arrays.sort(arr);`                           |
| Sort (desc)          | `Arrays.sort(arr, Collections.reverseOrder());` *(for Integer[])* |
| Loop (for)           | `for (int i = 0; i < arr.length; i++)`        |
| Loop (for-each)      | `for (int num : arr)`                         |
| Convert to list      | `Arrays.asList(arr)` *(for Integer[])*       |
| Fill with value      | `Arrays.fill(arr, 7);`                        |
| Copy range           | `Arrays.copyOfRange(arr, 1, 4);`              |
| Binary search        | `Arrays.binarySearch(arr, 3);`               |

---

## 🔁 Common Patterns
- 🔹 Two Pointers
- 🔹 Sliding Window
- 🔹 Prefix Sum
- 🔹 Kadane’s Algorithm (Max Subarray Sum)

---

## 🚀 Important Problems & Patterns

### 🔸 1. Two Sum
```java
Map<Integer, Integer> map = new HashMap<>();
for (int i = 0; i < nums.length; i++) {
    int complement = target - nums[i];
    if (map.containsKey(complement)) return new int[]{map.get(complement), i};
    map.put(nums[i], i);
}
```

---

### 🔸 2. Kadane’s Algorithm (Max Subarray Sum)
```java
int max = arr[0], sum = arr[0];
for (int i = 1; i < arr.length; i++) {
    sum = Math.max(arr[i], sum + arr[i]);
    max = Math.max(max, sum);
}
return max;
```

---

### 🔸 3. Prefix Sum
```java
int[] prefix = new int[n + 1];
for (int i = 1; i <= n; i++) {
    prefix[i] = prefix[i - 1] + arr[i - 1];
}
```

---

### 🔸 4. Sliding Window (Fixed Size)
```java
int sum = 0;
for (int i = 0; i < k; i++) sum += arr[i];
int maxSum = sum;
for (int i = k; i < arr.length; i++) {
    sum += arr[i] - arr[i - k];
    maxSum = Math.max(maxSum, sum);
}
```

---

## 📌 Tips & Tricks
- Use `.length` for array size.
- Prefer `ArrayList` if size is dynamic.
- Watch for **IndexOutOfBoundsException**.
- Clone array: `arr.clone()`

---

## 💡 Interview Hints
- Be careful with index bounds.
- Always consider edge cases: empty array, 1 element, duplicates.
- Understand the difference between `array` vs `ArrayList`.

