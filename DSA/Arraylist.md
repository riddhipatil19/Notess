# 📚 ArrayList (Java Collections)

---

## 🔍 Concept Overview
- **ArrayList** is a resizable array from Java's `java.util` package.
- It **automatically grows** as elements are added.
- **Index-based access** just like arrays.
- Stores **objects only** (use wrapper types like `Integer`, `String`, etc.).

```java
import java.util.ArrayList;
ArrayList<Integer> list = new ArrayList<>();
```

---

## ⚙️ Internal Working
- Backed by an array.
- When capacity is exceeded, it **creates a new array**, copies old elements, and resizes.
- **Default initial capacity** is 10.
- Resize logic: usually grows by ~1.5x current size.

---

## 🛠️ Common Operations with Syntax

| Operation          | Syntax                                      |
|--------------------|---------------------------------------------|
| Create             | `ArrayList<Integer> list = new ArrayList<>();` |
| Add element        | `list.add(10);`                             |
| Add at index       | `list.add(1, 99);`                          |
| Get element        | `int x = list.get(0);`                      |
| Set element        | `list.set(0, 50);`                          |
| Remove by index    | `list.remove(1);`                           |
| Remove by value    | `list.remove(Integer.valueOf(50));`         |
| Size               | `list.size();`                              |
| Check if empty     | `list.isEmpty();`                           |
| Contains element   | `list.contains(30);`                        |
| Clear list         | `list.clear();`                             |
| Loop (for-each)    | `for (int num : list)`                      |
| Convert to array   | `list.toArray(new Integer[0]);`             |
| Sort               | `Collections.sort(list);`                   |
| Reverse            | `Collections.reverse(list);`                |

---

## ⚡ Time Complexity

| Operation     | Complexity |
|---------------|------------|
| Add (end)     | O(1) amortized |
| Add (middle)  | O(n) |
| Remove (index)| O(n) |
| Get / Set     | O(1) |
| Search        | O(n) |

---

## 🔁 When to Use
- When you need **random access**.
- When the **size is dynamic**.
- When **insertions/deletions happen mostly at the end**.

---

## ⚠️ Limitations
- **Not thread-safe** → use `Vector` or `Collections.synchronizedList()`
- **Shifting elements is costly** when inserting/deleting in the middle

---

## 🧪 Example Usage

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        fruits.set(1, "Blueberry");

        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

---

## 🧠 Interview Tips
- Use `ArrayList` when size is unknown but access is frequent.
- Avoid using `==` to compare values; use `.equals()`.
- Don’t remove while iterating (unless using iterator’s `remove()`).

---

## ✅ Related Topics
- `LinkedList` – for frequent insert/delete
- `HashMap` – for key-value pairs
- [[Arrays]] – for fixed-size structures