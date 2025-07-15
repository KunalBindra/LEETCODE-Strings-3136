# LEETCODE-Strings-3136
---

### ✅ **Problem Summary (from LeetCode 3136 – Valid Word):**

A word is **valid** if:

1. It has **at least 3 characters**.
2. It contains **only letters or digits**.
3. It has **at least one vowel** (a, e, i, o, u).
4. It has **at least one consonant** (alphabetic but not a vowel).

---

### 🔍 Dry Run Example

Let's test it with the input:

```java
isValid("abc")
```

---

### ➤ Step-by-Step Execution:

```java
word.length() >= 3
```

* `"abc"` → length = 3 → ✅ Pass

```java
word.chars().allMatch(Character::isLetterOrDigit)
```

* `"abc"` → all characters are letters → ✅ Pass

```java
word.chars().anyMatch(c -> isVowel((char)c))
```

* Check each character:

  * 'a' → ✅ is a vowel → ✅ Pass

```java
word.chars().anyMatch(c -> isConso((char)c))
```

* Check each character:

  * 'a' → vowel ❌
  * 'b' → letter ✅, not vowel ✅ → consonant → ✅ Pass

---

✅ **Final Result**: Returns `true`.

---

### 🔄 One More Example

```java
isValid("1aE")
```

* Length = 3 → ✅
* All characters are letters or digits → ✅
* Vowels: 'a', 'E' → ✅
* Consonants: '1' → not a letter ❌, 'a' → vowel ❌, 'E' → vowel ❌ → ❌ No consonants

🟥 **Returns**: `false`

---

### 🔁 Explanation of Helper Methods

#### `isVowel(char c)`

```java
return "aeiouAEIOU".indexOf(c) != -1;
```

Checks if the character is in the string of vowels (case-insensitive).

#### `isConso(char c)`

```java
return Character.isLetter(c) && !isVowel(c);
```

Checks if it's a letter but not a vowel → hence a **consonant**.

---

### ✅ Summary of Logic

```java
word.length() >= 3
&&
all characters are letters or digits
&&
at least one vowel
&&
at least one consonant
```
