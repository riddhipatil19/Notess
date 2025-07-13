## 🔍 Concept Overview
- A `HashMap<K, V>` is a part of Java's `java.util` package.
- It stores **key-value pairs** using **hashing**.
- Keys are **unique**, values can be duplicated.
- Offers **constant-time** performance (O(1)) for get, put, and remove (on average).

```java
Map<String, Integer> map = new HashMap<>();
```

---

## 🛠️ Common Operations with Syntax

| Operation             | Syntax Example                                   |
|------------------------|--------------------------------------------------|
| Create a map           | `Map<String, Integer> map = new HashMap<>();`    |
| Add a key-value pair   | `map.put("apple", 3);`                           |
| Get value by key       | `map.get("apple");`                              |
| Update value           | `map.put("apple", 5);`                           |
| Remove a key           | `map.remove("apple");`                           |
| Check key exists       | `map.containsKey("apple");`                      |
| Check value exists     | `map.containsValue(3);`                          |
| Get size               | `map.size();`                                    |
| Is map empty           | `map.isEmpty();`                                 |
| Loop through keys      | `for (String key : map.keySet())`                |
| Loop through values    | `for (int val : map.values())`                   |
| Loop through entries   | `for (Map.Entry<String, Integer> e : map.entrySet())` |
| Clear map              | `map.clear();`                                   |
| Default value if absent| `map.getOrDefault("banana", 0);`                |

---

## ⚙️ Time Complexity

| Operation     | Average Case | Worst Case |
|---------------|--------------|-------------|
| put()         | O(1)         | O(n)        |
| get()         | O(1)         | O(n)        |
| remove()      | O(1)         | O(n)        |

> Worst case happens during **hash collisions** or poor hashing function.

---

## 🔁 When to Use
- Frequency counting
- Mapping values (index → value, char → count)
- Caching and memoization
- Grouping data by key

---

## 🚀 Common Interview Problems

### 🔸 1. Frequency Count of Characters
```java
Map<Character, Integer> freq = new HashMap<>();
for (char c : str.toCharArray()) {
    freq.put(c, freq.getOrDefault(c, 0) + 1);
}
```

---

### 🔸 2. Two Sum (LeetCode)
```java
Map<Integer, Integer> map = new HashMap<>();
for (int i = 0; i < nums.length; i++) {
    int diff = target - nums[i];
    if (map.containsKey(diff)) return new int[]{map.get(diff), i};
    map.put(nums[i], i);
}
```

---

### 🔸 3. Longest Substring Without Repeating Characters
```java
Map<Character, Integer> map = new HashMap<>();
int left = 0, max = 0;
for (int right = 0; right < s.length(); right++) {
    if (map.containsKey(s.charAt(right))) {
        left = Math.max(left, map.get(s.charAt(right)) + 1);
    }
    map.put(s.charAt(right), right);
    max = Math.max(max, right - left + 1);
}
```

---

## 🧠 Notes & Tips
- Key classes must implement `equals()` and `hashCode()`.
- HashMap does **not maintain order** — use `LinkedHashMap` or `TreeMap` for that.
- Avoid using mutable objects as keys.
- Use `TreeMap` if you need **sorted keys** (log n time).

---

## ✅ Related Classes

| Class          | Description                         |
|----------------|-------------------------------------|
| `HashMap`      | Fastest, no ordering                |
| `LinkedHashMap`| Maintains insertion order          |
| `TreeMap`      | Keys sorted by natural order        |
| `HashSet`      | Backed by HashMap (only keys)       |

---

## 🔗 Related Topics
- `/Hashing`
- [[Arrays]] → using maps for prefix/suffix
- `/DP` → memoization using map
