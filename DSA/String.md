## 🔍 Concept Overview
- A **String** in Java is an object that represents a sequence of characters.
- Strings are **immutable** — once created, their value cannot be changed.
- Stored in **string pool** for memory efficiency.

```java
String s1 = "hello";             // String literal (pooled)
String s2 = new String("hello"); // New object in heap
```

---

## 🛠️ Common Operations with Syntax

| Operation                | Syntax / Example                            |
|--------------------------|---------------------------------------------|
| Create                   | `String str = "hello";`                     |
| Length                   | `str.length();`                             |
| Concatenate              | `str + " world"`                            |
| char at index            | `str.charAt(2);`                            |
| Substring                | `str.substring(1, 4);`                      |
| Compare (equals)         | `str.equals("abc")`                         |
| Compare (ignore case)    | `str.equalsIgnoreCase("abc")`              |
| Compare lexicographically| `str.compareTo("xyz")`                     |
| Contains                 | `str.contains("ab")`                        |
| Replace                  | `str.replace("a", "b")`                     |
| Index of character       | `str.indexOf("a");`                         |
| Last index of character  | `str.lastIndexOf("a");`                     |
| To char array            | `str.toCharArray();`                        |
| Split                    | `str.split(" ");`                           |
| Trim spaces              | `str.trim();`                               |
| Convert to lower/upper   | `str.toLowerCase()`, `str.toUpperCase()`    |
| Convert int to string    | `String.valueOf(123);`                      |
| Convert string to int    | `Integer.parseInt("123");`                 |

---

## ⚙️ StringBuilder (for mutable strings)

```java
StringBuilder sb = new StringBuilder("abc");
sb.append("def");           // abcdef
sb.insert(1, "X");          // aXbcdef
sb.deleteCharAt(3);         // aXcdef
sb.reverse();               // fedcXa
```

➡️ Preferred for **modifying strings repeatedly**, as it is faster and memory-efficient.

---

## 🔁 Common Patterns in String Problems
- 🔹 Two Pointers (e.g., reverse string)
- 🔹 Sliding Window (longest substring with condition)
- 🔹 HashMap/Set for frequency or uniqueness
- 🔹 Palindrome checks
- 🔹 Prefix/Suffix Matching

---

## 🚀 Important Interview Problems

### 🔸 1. Reverse a String
```java
String str = "hello";
StringBuilder sb = new StringBuilder(str);
String reversed = sb.reverse().toString();
```

---

### 🔸 2. Check Palindrome
```java
public boolean isPalindrome(String s) {
    int i = 0, j = s.length() - 1;
    while (i < j) {
        if (s.charAt(i++) != s.charAt(j--)) return false;
    }
    return true;
}
```

---

### 🔸 3. Longest Substring Without Repeating Characters
```java
Set<Character> set = new HashSet<>();
int i = 0, j = 0, max = 0;
while (j < s.length()) {
    if (!set.contains(s.charAt(j))) {
        set.add(s.charAt(j++));
        max = Math.max(max, j - i);
    } else {
        set.remove(s.charAt(i++));
    }
}
return max;
```

---

## ⚠️ Common Pitfalls
- Avoid using `==` to compare strings → use `.equals()`
- Remember strings are **immutable**
- Be careful with substring indices → `[start, end)`

---

## ✅ Interview Tips
- Know when to use `StringBuilder` vs `String`
- Practice **sliding window** and **frequency maps**
- Always consider edge cases: empty string, single character, spaces

---

## 🔗 Related Topics
- `/Arrays` – for character manipulation
- `/Hashing` – for frequency counting
- `/Two Pointers` – for substring logic

