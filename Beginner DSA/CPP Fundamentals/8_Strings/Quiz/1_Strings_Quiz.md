---
title: "Strings Quiz"
slug: "strings-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on string mutability, getline, concatenation, and character ASCII math."
---

# Strings Quiz

Test your understanding of C++ Strings and Character manipulation!

---

### 1. If a user types `John Doe` into the console, and you read it using `cin >> s;`, what will the string `s` contain?
A. `"John Doe"`  
B. `"John"`  
C. `"Doe"`  
D. A compilation error  

### 2. How do you correctly read an entire line of text, including the spaces, into a string `s`?
A. `cin.read(s);`  
B. `cin >> s >> spaces;`  
C. `getline(cin, s);`  
D. `scanf(s);`  

### 3. Which operator is used to concatenate (join) two strings together in C++?
A. `.`  
B. `&`  
C. `+`  
D. `||`  

### 4. Are strings in C++ mutable (modifiable)?
A. Yes, you can change individual characters directly (e.g., `s[0] = 'Z'`).  
B. No, strings are completely immutable like in Python or Java.  
C. Only if you use a special library.  
D. Yes, but only for lowercase letters.  

### 5. If you have `char ch = '5';`, what is a clever way to convert it into the actual integer `5` using ASCII math?
A. `int val = ch - '0';`  
B. `int val = to_int(ch);`  
C. `int val = ch / 10;`  
D. `int val = (int)ch;`

### 6. What does the `.length()` or `.size()` method return for a string?
A. The number of bytes the string occupies in memory.  
B. The number of characters currently inside the string.  
C. The maximum capacity of the string.  
D. The number of vowels in the string.  

### 7. What does the `#include <string>` library provide that standard C character arrays do not?
A. Faster execution times.  
B. Built-in dynamic resizing, easy assignment, and concatenation.  
C. The ability to store numbers.  
D. Nothing, they are exactly the same.  

### 8. How do you append a single character `'A'` to the end of a string `s`?
A. `s.add('A');`  
B. `s.push_back('A');`  
C. `s += 'A';`  
D. Both B and C work!  

### 9. Which method is used to extract a portion (substring) of a string?
A. `s.slice()`  
B. `s.substr()`  
C. `s.split()`  
D. `s.cut()`  

### 10. What does `s.find("apple")` return if the word "apple" is NOT found inside the string `s`?
A. `-1`  
B. `false`  
C. `0`  
D. `string::npos`  

---

## Answer Key

1. **B** (Standard `cin >>` stops reading the moment it hits any whitespace. It will only capture "John").
2. **C** (`getline(cin, s)` reads the entire stream until the user hits the Enter key. **Warning:** If you use `cin >>` right before `getline`, it leaves a newline `\n` in the buffer, causing `getline` to instantly read an empty string! Use `cin.ignore()` to clear it).
3. **C** (The `+` operator smoothly concatenates strings, e.g., `"Hello" + " World"`).
4. **A** (Unlike Java or Python, C++ strings are mutable. You can directly edit `s[i]` without creating a whole new string!).
5. **A** (Since `'0'` has an ASCII value of 48, subtracting `'0'` from any character digit gives you its actual integer value. Writing `ch - '0'` is standard CP practice because it is much more readable than hardcoding 48).
6. **B** (It simply returns the character count, operating in $O(1)$ time).
7. **B** (C++ strings handle their own memory, freeing you from dealing with `char[]` limits and null terminators).
8. **D** (Both `push_back()` and `+=` are highly efficient ways to append characters in $O(1)$ time).
9. **B** (`s.substr(start_index, length)` is the standard way to grab substrings).
10. **D** (`string::npos` represents "no position" and is typically the maximum possible value for `size_t`).
