## 📘 Concept Overview

Sorting is the process of arranging data in a particular order — commonly ascending or descending.

### 🔸 Types:
- **Comparison-Based**: Bubble, Selection, Insertion, Merge, Quick, Heap
- **Non-Comparison-Based**: Counting, Radix, Bucket (used for integers)

---

## 📊 Time & Space Complexity

| Algorithm       | Best       | Average     | Worst       | Space | Stable |
|----------------|------------|-------------|-------------|-------|--------|
| Bubble Sort    | O(n)       | O(n²)       | O(n²)       | O(1)  | ✅     |
| Selection Sort | O(n²)      | O(n²)       | O(n²)       | O(1)  | ❌     |
| Insertion Sort | O(n)       | O(n²)       | O(n²)       | O(1)  | ✅     |
| Merge Sort     | O(n log n) | O(n log n)  | O(n log n)  | O(n)  | ✅     |
| Quick Sort     | O(n log n) | O(n log n)  | O(n²)       | O(log n) | ❌  |
| Heap Sort      | O(n log n) | O(n log n)  | O(n log n)  | O(1)  | ❌     |
| Counting Sort  | O(n + k)   | O(n + k)    | O(n + k)    | O(k)  | ✅     |
| Radix Sort     | O(nk)      | O(nk)       | O(nk)       | O(n+k)| ✅     |

---

## 🛠 Java Built-in Sorting

```java
// Array
Arrays.sort(arr); // ascending
Arrays.sort(arr, Collections.reverseOrder()); // descending (Integer[] only)

// ArrayList
Collections.sort(list); // ascending
Collections.sort(list, Collections.reverseOrder()); // descending
```

---

## 🔢 Sorting Algorithms

---

### 🔸 Bubble Sort

```java
for (int i = 0; i < arr.length - 1; i++) {
    for (int j = 0; j < arr.length - i - 1; j++) {
        if (arr[j] > arr[j + 1]) {
            int temp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = temp;
        }
    }
}
```

---

### 🔸 Selection Sort

```java
for (int i = 0; i < arr.length - 1; i++) {
    int minIndex = i;
    for (int j = i + 1; j < arr.length; j++) {
        if (arr[j] < arr[minIndex]) minIndex = j;
    }
    int temp = arr[i];
    arr[i] = arr[minIndex];
    arr[minIndex] = temp;
}
```

---

### 🔸 Insertion Sort

```java
for (int i = 1; i < arr.length; i++) {
    int key = arr[i];
    int j = i - 1;
    while (j >= 0 && arr[j] > key) {
        arr[j + 1] = arr[j];
        j--;
    }
    arr[j + 1] = key;
}
```

---

### 🔸 Merge Sort

```java
void mergeSort(int[] arr, int left, int right) {
    if (left < right) {
        int mid = (left + right) / 2;
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);
        merge(arr, left, mid, right);
    }
}

void merge(int[] arr, int l, int m, int r) {
    int[] left = Arrays.copyOfRange(arr, l, m + 1);
    int[] right = Arrays.copyOfRange(arr, m + 1, r + 1);
    int i = 0, j = 0, k = l;

    while (i < left.length && j < right.length) {
        arr[k++] = left[i] <= right[j] ? left[i++] : right[j++];
    }
    while (i < left.length) arr[k++] = left[i++];
    while (j < right.length) arr[k++] = right[j++];
}
```

---

### 🔸 Quick Sort

```java
void quickSort(int[] arr, int low, int high) {
    if (low < high) {
        int pivot = partition(arr, low, high);
        quickSort(arr, low, pivot - 1);
        quickSort(arr, pivot + 1, high);
    }
}

int partition(int[] arr, int low, int high) {
    int pivot = arr[high];
    int i = low - 1;
    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            int temp = arr[i]; arr[i] = arr[j]; arr[j] = temp;
        }
    }
    int temp = arr[i + 1]; arr[i + 1] = arr[high]; arr[high] = temp;
    return i + 1;
}
```

---

## ✅ When to Use Which?

| Situation                        | Use This       |
|----------------------------------|----------------|
| Small, nearly sorted             | Insertion Sort |
| Large dataset                    | Merge / Quick  |
| Need stable sorting              | Merge / Counting |
| Memory efficient                 | Quick / Heap   |
| Integer range known              | Counting / Radix |

---

## 🔗 Related Topics

- `/Searching.md`
- `/Arrays.md`
- `/Heap.md` (Heap Sort)
- `/DP.md` (for LIS/Sorting-based DP)
