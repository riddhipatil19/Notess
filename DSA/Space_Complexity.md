# 🧠 Space Complexity

---

## 📘 What is Space Complexity?

- Space complexity measures the **total memory** used by an algorithm as a function of input size `n`.
- It includes:
  - Input space
  - Auxiliary (extra) space
  - Recursive stack space

---

## 🧠 Why Space Complexity Matters

- Important in low-memory environments.
- Interviewers check whether you're **mutating in-place**.
- Helps determine scalability of your algorithm.

---

## 🧮 Common Space Complexities

| Space Complexity | Meaning                     | Examples                     |
|------------------|-----------------------------|------------------------------|
| O(1)             | Constant space              | Swapping, in-place sort      |
| O(log n)         | Logarithmic stack space     | Recursive binary search      |
| O(n)             | Linear                      | Arrays, HashMap, visited[]   |
| O(n²)            | 2D Matrix                   | Dynamic programming tables   |

---

## 📊 Examples

### 🔸 O(1) — Constant Space

```java
int sum = 0;
for (int num : arr) {
    sum += num;
}
```

---

### 🔸 O(n) — Linear Space

```java
int[] output = new int[n];
```

Or:

```java
HashMap<Integer, Integer> map = new HashMap<>();
```

---

### 🔸 O(n²) — Matrix

```java
int[][] dp = new int[n][n];  // space = O(n²)
```

---

## ⛏️ Recursion Stack Space

Each recursive call adds a new frame to the **call stack**.

```java
int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n - 1);
}
```

For `factorial(5)` → 5 stack frames → O(n) space

---

## 🧠 Space vs Auxiliary Space

- **Total space** = Input + Variables + Call Stack
- **Auxiliary space** = Extra space *excluding input*

---

## 💡 Optimization Tip: In-Place

Use **in-place algorithms** to reduce space:

| Task                   | Normal Space | In-Place (Optimized) |
|------------------------|--------------|-----------------------|
| Reverse array          | O(n)         | ✅ O(1)               |
| Merge sort             | O(n)         | ❌ Not in-place       |
| Quick sort             | O(log n)     | ✅ In-place           |
| Two-pointer problems   | O(n)         | ✅ O(1)               |

---

## ✅ Common Interview Examples

| Problem                          | Space Used     |
|----------------------------------|----------------|
| Merge Sort                       | O(n)           |
| Quick Sort                       | O(log n)       |
| HashMap frequency count          | O(n)           |
| In-place reversal of string      | O(1)           |
| DFS traversal of binary tree     | O(h) (h = height) |
| DP Fibonacci (tabulation)        | O(n)           |
| DP Fibonacci (space optimized)   | O(1)           |

---

## 🔗 Related Topics
- [Time Complexity](Time_Complexity.md)
- [Recursion](Recursion.md)
- [DP](DP.md)
