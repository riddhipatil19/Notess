# ⏱️ Time Complexity

---

## 🔍 What is Time Complexity?

- Time complexity describes **how the execution time of an algorithm grows** with the input size `n`.
- It is **not actual time**, but a **mathematical approximation** of how quickly the runtime grows.

---

## 🧠 Why It Matters

- Helps compare algorithms **independent of hardware or language**.
- You can predict performance on **large datasets**.
- Crucial for **coding interviews**, where efficiency matters.

---

## 🔠 Big-O Notation (Upper Bound)

Big-O gives the **worst-case** time complexity of an algorithm.

> **Ignore constants and low-order terms**, focus on growth rate.

---

## 📊 Common Time Complexities

| Time Complexity | Name            | Example                              |
|-----------------|------------------|--------------------------------------|
| O(1)            | Constant         | Accessing array index, hashmap.get() |
| O(log n)        | Logarithmic      | Binary Search                        |
| O(n)            | Linear           | Array traversal                      |
| O(n log n)      | Linearithmic     | Merge Sort, Quick Sort (avg case)    |
| O(n²)           | Quadratic        | Bubble Sort, 2D Matrix nested loops  |
| O(2ⁿ)           | Exponential      | Recursive Fibonacci, Subset Sum      |
| O(n!)           | Factorial        | Permutations, N-Queens brute force   |

---

## 🔁 Dry Run Examples

### 🔸 O(1): Constant Time

```java
int getFirstElement(int[] arr) {
    return arr[0];  // O(1)
}
```

---

### 🔸 O(n): Linear Time

```java
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);  // O(n)
}
```

---

### 🔸 O(n²): Quadratic Time

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        System.out.println(i + " " + j);  // O(n²)
    }
}
```

---

## 🧠 Nested Loops Rule

- Count how many **times the inner loop runs** relative to input size.

Example:

```java
for (int i = 0; i < n; i++) {        // O(n)
  for (int j = 0; j < n; j++) {      // O(n)
    // O(1) work
  }
}
// Total: O(n²)
```

---

## 📈 Graph Comparison (Intuition)

| Input Size (n) | O(1) | O(log n) | O(n) | O(n log n) | O(n²) |
|----------------|------|----------|------|------------|--------|
| 10             | 1    | 4        | 10   | 40         | 100    |
| 100            | 1    | 7        | 100  | 700        | 10,000 |
| 1,000,000      | 1    | 20       | 10⁶  | 20×10⁶     | 10¹²   |

> That's why you can't use O(n²) on arrays of size 10⁵ or more.

---

## 🪜 Best, Average & Worst Case

| Case Type  | Meaning                                  |
|------------|------------------------------------------|
| Best Case  | Least time to run (e.g. target at start) |
| Average    | Randomly spread input                    |
| Worst Case | Maximum time (e.g. sorted in reverse)    |

Example – **Linear Search**:
- Best: O(1)
- Worst: O(n)

---

## 🧩 Recursion Time Complexity

For recursive functions, define **T(n)** in terms of smaller inputs.

Example – Fibonacci:
```
T(n) = T(n-1) + T(n-2) + O(1)
Time = O(2ⁿ)
```

Example – Merge Sort:
```
T(n) = 2T(n/2) + O(n)
Time = O(n log n)
```

---

## 🧠 Tips to Determine Time Complexity

1. **Count total iterations of loops**
2. Ignore constant steps
3. If nested: multiply loops
4. For recursion: form recurrence relation
5. Sorting or searching in loops = log n or n log n
6. Hashing-based operations = O(1) average case

---

## ✅ Real-World Examples

| Operation                     | Time Complexity |
|------------------------------|-----------------|
| ArrayList get(index)         | O(1)            |
| LinkedList get(index)        | O(n)            |
| HashMap put/get              | O(1) avg        |
| TreeMap put/get              | O(log n)        |
| Binary Search                | O(log n)        |
| Merge Sort                   | O(n log n)      |
| Brute-force substring match  | O(n²)           |

---

## 🔗 Related Topics
- [Space Complexity](Space_Complexity.md)
- [Recursion](Recursion.md)
- [Sorting](Sorting.md)
