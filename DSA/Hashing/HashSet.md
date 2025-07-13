## 🔍 Concept Overview
- `HashSet<E>` is a collection that contains **no duplicate elements**.
- Internally backed by a `HashMap<E, Object>`.
- **Order is not maintained** (unordered collection).
- Ideal for **fast lookup, uniqueness checks**, and **set operations**.

```java
Set<Integer> set = new HashSet<>();
```

---

## 🛠️ Common Operations with Syntax

| Operation            | Syntax Example                           |
|----------------------|-------------------------------------------|
| Create set           | `Set<String> set = new HashSet<>();`      |
| Add element          | `set.add("apple");`                       |
| Remove element       | `set.remove("apple");`                    |
| Check if exists      | `set.contains("apple");`                  |
| Get size             | `set.size();`                             |
| Check if empty       | `set.isEmpty();`                          |
| Clear set            | `set.clear();`                            |
| Loop through set     | `for (String s : set)`                    |
| Convert to array     | `set.toArray(new String[0]);`             |

---

## ⚙️ Time Complexity

| Operation    | Average Case |
|--------------|--------------|
| add()        | O(1)         |
| remove()     | O(1)         |
| contains()   | O(1)         |

> Like `HashMap`, worst-case is O(n) if too many hash collisions occur, but that's rare.

---

## 🔁 When to Use
- Remove duplicates from a list
- Fast membership checking
- Track visited elements
- Set-based logic (union, intersection, difference)

---

## 🚀 Common Interview Problems

### 🔸 1. Remove Duplicates from Array
```java
Set<Integer> set = new HashSet<>();
for (int num : nums) {
    set.add(num);
}
```

---

### 🔸 2. Check if Array Has Duplicates
```java
Set<Integer> seen = new HashSet<>();
for (int num : nums) {
    if (!seen.add(num)) return true; // duplicate found
}
return false;
```

---

### 🔸 3. Longest Consecutive Sequence (LeetCode)
```java
Set<Integer> set = new HashSet<>();
for (int num : nums) set.add(num);

int longest = 0;
for (int num : set) {
    if (!set.contains(num - 1)) {
        int current = num;
        int length = 1;
        while (set.contains(current + 1)) {
            current++;
            length++;
        }
        longest = Math.max(longest, length);
    }
}
return longest;
```

---

## ⚠️ Common Pitfalls
- **Order is not guaranteed** (use `LinkedHashSet` if needed).
- Only stores **unique values**.
- Backed by `HashMap` → hashing performance matters.

---

## ✅ Related Classes

| Class           | Description                         |
|------------------|-------------------------------------|
| `HashSet`        | Fast, no order                      |
| `LinkedHashSet`  | Maintains insertion order           |
| `TreeSet`        | Sorted set (based on `Comparable`)  |

---

## 🔗 Related Topics
- `/Hashing`
- [[Arrays]] – for duplicates and lookups
- `/Graphs` – track visited nodes
