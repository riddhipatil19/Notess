## 🔍 What is StringBuilder?
- A **mutable** sequence of characters — unlike `String`, it can be modified without creating new objects.
- Stored in heap memory.
- Faster for operations like appending, deleting, inserting, or reversing strings.

```java
StringBuilder sb = new StringBuilder("Hello");
```

---

## 🛠️ Common Operations with Syntax

| Operation           | Syntax Example                         | Result              |
|---------------------|-----------------------------------------|----------------------|
| Create empty        | `new StringBuilder();`                  | —                    |
| Create with value   | `new StringBuilder("abc");`             | "abc"                |
| Append              | `sb.append("xyz");`                     | "abcxyz"             |
| Insert              | `sb.insert(1, "X");`                    | "aXbc"               |
| Delete              | `sb.delete(1, 3);`                      | Removes index 1–2    |
| Delete char         | `sb.deleteCharAt(2);`                   | Removes char at index 2 |
| Replace             | `sb.replace(1, 3, "YZ");`               | Replaces index 1–2   |
| Reverse             | `sb.reverse();`                         | Reverses string      |
| Get char            | `sb.charAt(2);`                         | Returns char at 2    |
| Set char            | `sb.setCharAt(1, 'Z');`                 | Changes index 1      |
| Length              | `sb.length();`                          | Current length       |
| Convert to string   | `sb.toString();`                        | String version       |
| Capacity (initial)  | `new StringBuilder(50);`                | Pre-allocated size   |
| Ensure capacity     | `sb.ensureCapacity(100);`               | Avoids resizing      |
| Trim capacity       | `sb.trimToSize();`                      | Cuts unused space    |

---

## 🧪 Code Example
```java
StringBuilder sb = new StringBuilder("Java");
sb.append(" DSA");                  // "Java DSA"
sb.insert(4, " &");                 // "Java & DSA"
sb.delete(0, 5);                    // "DSA"
sb.reverse();                       // "ASD"
System.out.println(sb.toString());
```

---

## ⚠️ Notes
- Not **thread-safe** → use `StringBuffer` if multithreading is needed.
- Automatically resizes — initial capacity is **16**, then grows.
- Use `.toString()` when you want the final `String`.

---

## ✅ When to Use
- Repeated modifications to strings (append/delete/replace)
- Avoid performance cost of immutability in `String`

---

## 🔗 Related Topics
- `/Strings` – for immutability and string patterns
- `/DP` – when building results efficiently
